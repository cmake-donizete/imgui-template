find_package(OpenGL REQUIRED)

set(BACKEND_SOURCE
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_sdl3.cpp
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp)

set(BACKEND_HEADERS ${IMGUI_SOURCE_DIR}/backends)

add_library(sdl3-opengl STATIC ${BACKEND_SOURCE})
target_include_directories(sdl3-opengl PUBLIC ${BACKEND_HEADERS})
target_link_libraries(
    sdl3-opengl
    PUBLIC
    imgui
    SDL3::SDL3
    OpenGL::GL)