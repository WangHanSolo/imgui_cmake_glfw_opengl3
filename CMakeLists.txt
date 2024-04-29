cmake_minimum_required(VERSION 3.22)
project(view)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#------------------------------------------
# Prevent in-source builds.
#------------------------------------------
if(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})
    message( FATAL_ERROR "In-source build is not recommended. Choose an empty directory for build output." )
endif(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})

find_package(glfw3 REQUIRED)

add_subdirectory(imgui)

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} glfw imgui)

if (APPLE)
    target_link_libraries(${PROJECT_NAME} "-framework OpenGL")
endif()
