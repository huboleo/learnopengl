add_executable(materials
    main.cpp
)

target_link_libraries(materials
    PRIVATE
        opengl_common
        glfw
        stb
        glm_headers
        OpenGL::GL
)
