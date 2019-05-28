set(SRC_FILES Transform.cpp)

file(COPY shader
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY Assets
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(4.Transform ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(4.Transform ${SDL2_LIBRARIES} GLAD)
endif ()

if (MSVC)
    target_link_libraries(4.Transform PRIVATE SDL2::SDL2 SDL2::SDL2main GLAD)
endif ()
