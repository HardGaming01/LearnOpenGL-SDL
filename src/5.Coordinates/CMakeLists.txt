set(SRC_FILES Coordinates.cpp)

file(COPY shader
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY Assets
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(5.Coordinates ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(5.Coordinates ${SDL2_LIBRARIES} GLAD)
endif ()

if (MSVC)
    target_link_libraries(5.Coordinates PRIVATE SDL2::SDL2 SDL2::SDL2main GLAD)
endif ()
