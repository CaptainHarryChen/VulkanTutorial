cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

project(VulkanLearn LANGUAGES CXX)

set(Proj_Dir ${CMAKE_CURRENT_SOURCE_DIR})
set(Asset_Dir ${CMAKE_CURRENT_SOURCE_DIR}/asset)
set(Extern_Dir ${CMAKE_CURRENT_SOURCE_DIR}/extern)
set(Example_Dir ${CMAKE_CURRENT_SOURCE_DIR}/code)

add_compile_definitions($<$<CONFIG:Debug>:DEBUG>)
add_compile_definitions($<$<CONFIG:Release>:NDEBUG>)

find_package(vulkan REQUIRED)
message(STATUS "Vulkan version: ${Vulkan_VERSION}")

add_subdirectory(extern)
add_subdirectory(code)
