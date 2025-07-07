set(IMGUI_SOURCE_DIR ${PROJECT_SOURCE_DIR}/external/imgui)

# ImGui
file(GLOB IMGUI_SOURCE_FILES ${IMGUI_SOURCE_DIR}/*.cpp)
set(IMGUI_HEADER_FILES ${IMGUI_SOURCE_DIR})

# SDL3 + OpenGL
set(IMGUI_BACKEND_SOURCE_FILES
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_sdl3.cpp
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp)

set(IMGUI_BACKEND_HEADER_FILES
    ${IMGUI_SOURCE_DIR}/backends)

add_library(
    imgui-sdl3-impl
    STATIC
    ${IMGUI_SOURCE_FILES}
    ${IMGUI_BACKEND_SOURCE_FILES})

target_include_directories(
    imgui-sdl3-impl
    PUBLIC
    ${IMGUI_HEADER_FILES}
    ${IMGUI_BACKEND_HEADER_FILES})

find_package(OpenGL REQUIRED)

target_link_libraries(
    imgui-sdl3-impl
    PUBLIC
    SDL3::SDL3
    OpenGL::GL)