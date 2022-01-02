# main executable

add_executable(hellocpp
    main.cpp
    sciter-gtk-main.cpp
)

target_link_libraries(hellocpp
    PRIVATE
    sciter_js_sdk
)
