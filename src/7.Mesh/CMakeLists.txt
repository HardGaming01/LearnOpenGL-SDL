set(SRC_FILES Mesh.cpp)

file(COPY shader
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
file(COPY Assets
        DESTINATION ${CMAKE_CURRENT_BINARY_DIR})

add_executable(7.Mesh ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(7.Mesh ${SDL2_LIBRARIES} ${ASSIMP_LIBRARIES} GLAD)
endif ()

if (MSVC)
    target_link_libraries(7.Mesh PRIVATE SDL2::SDL2 SDL2::SDL2main ${ASSIMP_LIBRARIES} GLAD)

    set_property(TARGET 7.Mesh PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}")
endif ()
