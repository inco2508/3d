cmake_minimum_required(VERSION 3.10)

project(groscube VERSION 0.1.0)

add_subdirectory(vendor/glfw)
add_subdirectory(vendor/glad)

add_executable(groscube 
    src/main.cpp
    vendor/imgui/imgui.cpp
    vendor/imgui/imgui_draw.cpp
    vendor/imgui/imgui_tables.cpp
    vendor/imgui/imgui_widgets.cpp
    vendor/imgui/backends/imgui_impl_opengl3.cpp
    vendor/imgui/backends/imgui_impl_glfw.cpp
    vendor/imgui/imgui_demo.cpp
)

target_link_libraries(groscube PUBLIC glad glfw)

target_include_directories(groscube PUBLIC 
    ${CMAKE_CURRENT_SOURCE_DIR}
    vendor/imgui
    vendor/imgui/backends
)