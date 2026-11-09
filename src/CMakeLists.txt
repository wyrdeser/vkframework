add_executable(vkframework
    main.cpp)

set_target_properties(vkframework PROPERTIES
    CXX_STANDARD 20
    CXX_EXTENSIONS OFF)

# target_add_extra_warnings(vkframework)

target_include_directories(vkframework PRIVATE "${CMAKE_CURRENT_LIST_DIR}")

target_link_libraries(vkframework PRIVATE glfw::glfw)