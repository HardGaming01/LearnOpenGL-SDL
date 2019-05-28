set(SRC_FILES Texture.cpp)

file(COPY shader
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY Assets
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(3.Texture ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(3.Texture ${SDL2_LIBRARIES} GLAD)
endif ()

if (MSVC)
    target_link_libraries(3.Texture PRIVATE SDL2::SDL2 SDL2::SDL2main GLAD)
endif ()
