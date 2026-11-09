cmake_minimum_required(VERSION 3.21)

project(vkframework
        VERSION 0.0.1
        LANGUAGES CXX)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")


if(WIN32)
        set(BUILD_SHARED_LIBS OFF CACHE BOOL "Link to libs dynamically")
else()
        set(BUILD_SHARED_LIBS ON CACHE BOOL "Link to libs dynamically")
endif()

if(NOT EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/third_party/glfw/CMakeLists.txt")
        include(FetchSubmodules)
        fetch_submodules()
endif()

add_subdirectory(third_party)
add_subdirectory(src)