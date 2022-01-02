# ----- GLAD -----

add_library(sciter_js_sdk INTERFACE
)

target_include_directories(sciter_js_sdk
    INTERFACE
    sciter-js-sdk/include
)
target_link_libraries(sciter_js_sdk
    INTERFACE
    gtk
    dl
)
