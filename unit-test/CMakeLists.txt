add_executable(unit_test
    doctest.h
    hello_world.cpp
    collision_test.cpp
    joint_test.cpp
    math_test.cpp
    world_test.cpp
)

set_target_properties(unit_test PROPERTIES
	CXX_STANDARD 11
    CXX_STANDARD_REQUIRED YES
    CXX_EXTENSIONS NO
)
target_link_libraries(unit_test PUBLIC box2d)

if (${CMAKE_VERSION} VERSION_EQUAL "3.8.0" OR ${CMAKE_VERSION} VERSION_GREATER "3.8.0") 
	source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES doctest.h
		hello_world.cpp collision_test.cpp joint_test.cpp math_test.cpp world_test.cpp )
endif()
