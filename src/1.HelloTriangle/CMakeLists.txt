set(SRC_FILES HelloTriangle.cpp)

add_executable(1.HelloTriangle ${SRC_FILES})

if (NOT MSVC)
    target_link_libraries(1.HelloTriangle ${SDL2_LIBRARIES} GLAD)
endif ()

if (MSVC)
    # Linking with vcpkg
    target_link_libraries(1.HelloTriangle PRIVATE SDL2::SDL2 SDL2::SDL2main GLAD)
endif ()
