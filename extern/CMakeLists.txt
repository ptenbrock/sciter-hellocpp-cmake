# ----- GLAD -----

add_library(sciter_js_sdk STATIC
    sciter-js-sdk/include/sciter-gtk-main.cpp
)

target_include_directories(sciter_js_sdk PUBLIC
    sciter-js-sdk/include
)
target_link_libraries(sciter_js_sdk PUBLIC
    gtk
    dl
)

add_custom_command(TARGET sciter_js_sdk
    POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_if_different ${PROJECT_SOURCE_DIR}/extern/sciter-js-sdk/bin/linux/x64/libsciter-gtk.so ${CMAKE_BINARY_DIR}
)
