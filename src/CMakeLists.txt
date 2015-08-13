
add_executable(simple_demo simple_demo.cpp)

target_link_libraries(simple_demo ${SIMPLE_LIBS})

install(TARGETS simple_demo RUNTIME DESTINATION bin)
