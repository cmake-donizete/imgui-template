find_package(OpenGL REQUIRED)

set(BACKEND_SOURCE
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_sdl3.cpp
    ${IMGUI_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp)

set(BACKEND_HEADERS ${IMGUI_SOURCE_DIR}/backends)

add_library(imgui-impl STATIC imgui-impl.cpp ${BACKEND_SOURCE})
target_include_directories(imgui-impl PUBLIC ${BACKEND_HEADERS})

target_link_libraries(
    imgui-impl
    PUBLIC
    imgui-source
    imgui-header
    SDL3::SDL3
    OpenGL::GL)