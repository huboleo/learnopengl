add_executable(transformation
    main.cpp
)

target_link_libraries(transformation
    PRIVATE
        glfw
        stb
        glm_headers
        OpenGL::GL
)
