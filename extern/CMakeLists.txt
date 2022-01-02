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
