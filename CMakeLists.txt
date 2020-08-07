cmake_minimum_required(VERSION 3.15)
project(LearnVulkan)
set (CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED FATAL_ERROR) # error

add_subdirectory(contrib)

include_directories(${Vulkan_INCLUDE_DIR})
include_directories(contrib/glfw/include)
include_directories(contrib/glm)
add_executable(LearnVulkan source/main.cpp)
target_link_libraries(LearnVulkan glfw glm ${Vulkan_LIBRARIES})