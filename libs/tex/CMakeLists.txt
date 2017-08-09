file (GLOB HEADERS "*.h")
file (GLOB SOURCES "[^_]*.cpp")

set(LIBRARY tex)
add_library(${LIBRARY} STATIC ${SOURCES})
add_dependencies(${LIBRARY} mve ext_rayint ext_eigen)
target_link_libraries(${LIBRARY} mrf mve mve_util ${JPEG_LIBRARIES} ${PNG_LIBRARIES} ${TIFF_LIBRARIES})
install(TARGETS ${LIBRARY} ARCHIVE DESTINATION lib)
