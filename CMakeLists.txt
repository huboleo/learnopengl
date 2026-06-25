cmake_minimum_required(VERSION 3.20)
project(opengl_learning LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include(FetchContent)

FetchContent_Declare(
    glfw
    GIT_REPOSITORY https://github.com/glfw/glfw.git
    GIT_TAG 3.4
)

FetchContent_Declare(
    stb
    GIT_REPOSITORY https://github.com/nothings/stb.git
    GIT_TAG master
)

FetchContent_Declare(
    glm
    GIT_REPOSITORY https://github.com/g-truc/glm.git
    GIT_TAG 1.0.1
)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

FetchContent_MakeAvailable(glfw stb glm)

add_library(stb INTERFACE)
target_include_directories(stb INTERFACE ${stb_SOURCE_DIR})

add_library(glm_headers INTERFACE)
target_include_directories(glm_headers INTERFACE ${glm_SOURCE_DIR})

find_package(OpenGL REQUIRED)

add_library(opengl_common INTERFACE)
target_sources(opengl_common
    INTERFACE
        ${CMAKE_CURRENT_SOURCE_DIR}/common/camera.h
        ${CMAKE_CURRENT_SOURCE_DIR}/common/shader.h
)
target_include_directories(opengl_common INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(opengl_common INTERFACE glfw glm_headers OpenGL::GL)

add_subdirectory(triangles)
add_subdirectory(shaders)
add_subdirectory(textures)
add_subdirectory(transformations)
add_subdirectory(coordinates)
add_subdirectory(camera)
add_subdirectory(colors)
add_subdirectory(basic-lighting)
add_subdirectory(materials)
