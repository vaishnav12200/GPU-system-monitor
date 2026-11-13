cmake_minimum_required(VERSION 3.20)

project(GpuMonitor
    VERSION 0.0.1
    DESCRIPTION "Native Linux GPU monitoring application"
    LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_executable(gpu_monitor src/main.cpp)
target_include_directories(gpu_monitor PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Future (not enabled yet): NVML, Qt 6, GoogleTest, tests/ subdirectory.
