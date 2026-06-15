add_executable(shaders main.cpp)

target_link_libraries(shaders
    PRIVATE
        opengl_common
        glfw
        OpenGL::GL
)
