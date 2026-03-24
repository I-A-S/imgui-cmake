cmake_minimum_required(VERSION 3.20)

project(DearImGui_CMake)

add_library(ImGui_Base STATIC
  imgui.cpp
  imgui_demo.cpp
  imgui_draw.cpp
  imgui_tables.cpp
  imgui_widgets.cpp
)
target_include_directories(ImGui_Base PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

add_library(ImGui_SDL3_GPU STATIC
  backends/imgui_impl_sdl3.cpp
  backends/imgui_impl_sdlgpu3.cpp
)
target_include_directories(ImGui_SDL3_GPU PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/backends)
target_link_libraries(ImGui_SDL3_GPU PUBLIC ImGui_Base)
