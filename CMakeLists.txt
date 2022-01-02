cmake_minimum_required(VERSION 3.2)


project(
    hellocpp
    VERSION 0.1
    DESCRIPTION "Simple Sciter integration"
    LANGUAGES CXX
)

# Only do these if this is the main project, and not if it is included through add_subdirectory
if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)

  # Optionally set things like CMAKE_CXX_STANDARD, CMAKE_POSITION_INDEPENDENT_CODE here

  # Let's ensure -std=c++xx instead of -std=g++xx
  set(CMAKE_CXX_EXTENSIONS OFF)

  # Let's nicely support folders in IDEs
  set_property(GLOBAL PROPERTY USE_FOLDERS ON)

  # Testing only available if this is the main app
  # Note this needs to be done in the main CMakeLists
  # since it calls enable_testing, which must be in the
  # main CMakeLists.
  #include(CTest)

  # Docs only available if this is the main app
  #find_package(Doxygen)
  #if(Doxygen_FOUND)
  #  add_subdirectory(docs)
  #else()
  #  message(STATUS "Doxygen not found, not building docs")
  #endif()
endif()



find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

# pseudo target for GTK
add_library(gtk INTERFACE)
target_include_directories(gtk INTERFACE ${GTK3_INCLUDE_DIRS})
target_link_directories(gtk INTERFACE ${GTK3_LIBRARY_DIRS})
target_compile_options(gtk INTERFACE ${GTK3_CFLAGS_OTHER})
target_link_libraries(gtk INTERFACE ${GTK3_LIBRARIES})


add_subdirectory(extern)


add_subdirectory(src)
