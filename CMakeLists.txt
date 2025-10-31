cmake_minimum_required(VERSION 3.27)
project(CPukan C)

set(CMAKE_C_STANDARD 17)

#!_____________APP____________________________
add_executable(CPukan
        src/main.c
        src/backend/glfw_backend.cpp
        src/logging/logger.cpp
        includes/logging/logger.h
        src/renderer/instance.cpp
        includes/renderer/instance.h
        src/renderer/renderer.cpp
        includes/renderer/renderer.h
        src/controller/Application.cpp
        includes/controller/Application.h
)
#!________________Vulkan_____________________
target_include_directories(CPukan
        PRIVATE
        dependencies
)

target_link_libraries(CPukan
        glfw
        Vulkan:Vulkan
)