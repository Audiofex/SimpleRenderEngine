

add_executable(SRE-Test-Spinning-Sphere-Cubemap spinning-sphere-cubemap.cpp)
add_executable(SRE-Test-Particle-Test particle-test.cpp)
add_executable(SRE-Test-PolygonOffset polygon-offset-example.cpp)
add_executable(SRE-Test-Multiple-Lights multiple-lights.cpp)
add_executable(SRE-Test-Particle-Sprite particle-sprite.cpp)

target_link_libraries(SRE-Test-Spinning-Sphere-Cubemap ${EXTRA_LIBS} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} SRE)
target_link_libraries(SRE-Test-Particle-Test ${EXTRA_LIBS} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} SRE)
target_link_libraries(SRE-Test-PolygonOffset ${EXTRA_LIBS} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} SRE)
target_link_libraries(SRE-Test-Multiple-Lights ${EXTRA_LIBS} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} SRE)
target_link_libraries(SRE-Test-Particle-Sprite ${EXTRA_LIBS} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} SRE)

file(COPY ../test_data DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/Debug)
file(COPY ../test_data DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/Debug)

IF (WIN32)
    SET(SDL2_dll "" CACHE STRING "Where the SDL2.dll can be found")
    SET(SDL2_image_lib_path "" CACHE PATH "Where the SDL2_image.dll can be found")
    SET(DLLFileList "${SDL2_image_lib_path}/SDL2_image.dll" "${SDL2_image_lib_path}/libjpeg-9.dll" "${SDL2_image_lib_path}/libpng16-16.dll" "${SDL2_image_lib_path}/libtiff-5.dll" "${SDL2_image_lib_path}/libwebp-4.dll" "${SDL2_image_lib_path}/zlib1.dll"  ${SDL2_dll})
    file(COPY ${DLLFileList} DESTINATION Debug)
    file(COPY ${DLLFileList} DESTINATION Release)
ENDIF(WIN32)
