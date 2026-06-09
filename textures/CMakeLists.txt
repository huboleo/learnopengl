add_executable(textures
    main.cpp
)

target_link_libraries(textures
    PRIVATE
        glfw
        stb
        OpenGL::GL
)
