find_package(sobjectizer CONFIG REQUIRED)

set(EXAMPLE_S example_dispatchers)
add_executable(${EXAMPLE_S} main.cpp)
target_link_libraries(${EXAMPLE_S} sobjectizer::StaticLib)
install(TARGETS ${EXAMPLE_S} DESTINATION bin)

