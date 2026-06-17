add_executable(colors
    main.cpp
)

target_link_libraries(colors
    PRIVATE
        opengl_common
        glfw
        stb
        glm_headers
        OpenGL::GL
)
