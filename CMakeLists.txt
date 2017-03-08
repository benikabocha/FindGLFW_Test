project (FindGLFW_Test)

cmake_minimum_required (VERSION 3.7)

set (CMAKE_MODULE_PATH "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

option (FindGLFW_Test_GLFW_ROOT "GLFW Directory" "")

set (GLFW_ROOT ${FindGLFW_Test_GLFW_ROOT})
find_package(GLFW REQUIRED)
find_package(OpenGL REQUIRED)

include_directories(${GLFW_INCLUDE_DIR})
add_executable(glfw_app main.cpp)
target_link_libraries(glfw_app
    ${GLFW_LIBRARIES}
    ${OPENGL_LIBRARY}
)
