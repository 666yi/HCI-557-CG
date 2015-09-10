# Main cmake file 
# Glfw Window

cmake_minimum_required(VERSION 2.6)

# Main project name is ARMaker
project(Glfw_Window)

set(CMAKE_LIBRARY_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/../SDK/cmake/")
set(LIBRARY_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/../SDK")
message(STATUS "Source directory ${CMAKE_SOURCE_DIR}")

set( glm_DIR ${LIBRARY_PATH} )
set( glfw3_DIR ${LIBRARY_PATH} )

# Find packages
FIND_PACKAGE(glew REQUIRED)
FIND_PACKAGE(glm NO_MODULE REQUIRED)
FIND_PACKAGE(glfw3 REQUIRED)
FIND_PACKAGE(OpenGL REQUIRED)


# Include dirs
include_directories(${GLEW_INCLUDE_DIR})
include_directories(${GLFW3_INCLUDE_DIR})
include_directories(${GLM_INCLUDE_DIR})
include_directories(${OPENGL_INCLUDE_DIR})

# Add all files to the configuration
file(GLOB Glfw_Window_SRC
    "main.cpp"
)

# Create an executable
add_executable(Glfw_Window ${Glfw_Window_SRC})


# Add link directories
# Note required for this project
# ink_directories(${NON})


# Add libraries
target_link_libraries(Glfw_Window ${GLEW_LIBRARY} ${GLFW3_LIBRARY} ${OPENGL_LIBRARIES} ${OPENGL_LIBRARIES} )