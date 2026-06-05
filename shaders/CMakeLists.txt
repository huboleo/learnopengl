add_executable(shaders main.cpp)

target_link_libraries(shaders
    PRIVATE
        glfw
        OpenGL::GL
)
