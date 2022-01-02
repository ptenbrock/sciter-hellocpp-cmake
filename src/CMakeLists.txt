# main executable

add_custom_target(packfolder_resources
    COMMAND extern/sciter-js-sdk/bin/linux/packfolder ui src/resources.cpp -v "resources"
    WORKING_DIRECTORY ${PROJECT_SOURCE_DIR}
    COMMENT "Generating resources.cpp"
)

add_executable(hellocpp
    main.cpp
)
add_dependencies(hellocpp packfolder_resources)
target_link_libraries(hellocpp
    PRIVATE
    sciter_js_sdk
)
set_target_properties(hellocpp PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
)
