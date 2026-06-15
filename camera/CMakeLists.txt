add_executable(camera
    main.cpp
)

target_link_libraries(camera
    PRIVATE
        opengl_common
        glfw
        stb
        glm_headers
        OpenGL::GL
)
