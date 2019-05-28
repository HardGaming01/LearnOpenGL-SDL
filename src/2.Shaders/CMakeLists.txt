set(SRC_FILES Shader.cpp)

file(COPY shader
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(2.Shaders ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(2.Shaders ${SDL2_LIBRARIES} GLAD)
endif ()

if (MSVC)
    target_link_libraries(2.Shaders PRIVATE SDL2::SDL2 SDL2::SDL2main GLAD)
endif ()
