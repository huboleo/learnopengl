add_executable(basic-lighting
    main.cpp
)

target_link_libraries(basic-lighting
    PRIVATE
        opengl_common
        glfw
        stb
        glm_headers
        OpenGL::GL
)
