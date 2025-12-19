cmake_minimum_required(VERSION 3.24)
project(VulkanRendererLib)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(Vulkan REQUIRED)
add_subdirectory(../third_party/SDL SDL3)

# lib (include is for templates)
add_library(lib STATIC
    vk_engine.cpp
    )

target_include_directories(lib PUBLIC 
    include 
    ../SDL/include
    )

target_link_libraries(lib
    Vulkan::Vulkan
    SDL3::SDL3
    vk-bootstrap::vk-bootstrap
    GPUOpen::VulkanMemoryAllocator
    )


