set(IMGUI_SOURCE_DIR ${PROJECT_SOURCE_DIR}/external/imgui)

file(GLOB IMGUI_SOURCE ${IMGUI_SOURCE_DIR}/*.cpp)
set(IMGUI_HEADERS ${IMGUI_SOURCE_DIR})

add_library(imgui STATIC ${IMGUI_SOURCE})
target_include_directories(imgui PUBLIC ${IMGUI_HEADERS})

add_subdirectory(OpenGL)
target_link_libraries(imgui PUBLIC sdl3-opengl)