add_executable(coordinates
    main.cpp
)

target_link_libraries(coordinates
    PRIVATE
        glfw
        stb
        glm_headers
        OpenGL::GL
)
