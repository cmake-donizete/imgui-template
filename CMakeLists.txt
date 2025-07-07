cmake_minimum_required(VERSION 3.10.0)

project(img-gui-template VERSION 0.1.0 LANGUAGES CXX)

add_subdirectory(external)

add_executable(img-gui-template main.cpp)
target_link_libraries(img-gui-template
    SDL3::SDL3
    imgui-sdl3-impl)