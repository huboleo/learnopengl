add_executable(textures
    main.cpp
)

target_link_libraries(textures
    PRIVATE
        opengl_common
        glfw
        stb
        OpenGL::GL
)
