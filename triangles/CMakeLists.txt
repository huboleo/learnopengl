add_executable(triangles main.cpp)

target_link_libraries(triangles
    PRIVATE
        glfw
        OpenGL::GL
)
