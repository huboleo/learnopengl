add_executable(transformation
    main.cpp
)

target_link_libraries(transformation
    PRIVATE
        opengl_common
        glfw
        stb
        glm_headers
        OpenGL::GL
)
