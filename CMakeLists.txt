cmake_minimum_required(VERSION 3.24)
project(VulkanRenderer)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(Vulkan REQUIRED)

add_subdirectory(lib lib)
add_subdirectory(third_party)

# executable
add_executable(renderer main.cpp)
target_link_libraries(renderer PRIVATE 
    lib
    SDL3::SDL3
    vk-bootstrap::vk-bootstrap
)

target_include_directories(renderer PUBLIC 
    lib/include
    SDL/include
)

# shaders
file(COPY shaders DESTINATION ${CMAKE_BINARY_DIR})
file(COPY assets DESTINATION ${CMAKE_BINARY_DIR})

