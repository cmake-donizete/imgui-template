cmake_minimum_required(VERSION 3.10.0)

project(img-gui-template VERSION 0.1.0 LANGUAGES C CXX)

set(BUILD_SHARED_LIBS OFF)
add_subdirectory(external)

add_executable(img-gui-template main.cpp)
target_link_libraries(img-gui-template imgui-sdl3-impl)