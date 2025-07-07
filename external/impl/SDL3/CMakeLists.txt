set(IMGUI_SOURCE_DIR ${PROJECT_SOURCE_DIR}/external/imgui)

file(GLOB IMGUI_SOURCE_FILES ${IMGUI_SOURCE_DIR}/*.cpp)
set(IMGUI_HEADER_FILES ${IMGUI_SOURCE_DIR})

add_library(imgui-sdl3-impl STATIC ${IMGUI_SOURCE_FILES} ${IMGUI_HEADER_FILES})
target_include_directories(imgui-sdl3-impl PUBLIC ${IMGUI_HEADER_FILES})