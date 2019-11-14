cmake_minimum_required (VERSION 3.12.4)

file(GLOB_RECURSE ENGINE_SRC_FILES ${PROJECT_SOURCE_DIR}/engine/src/*.cpp)
file(GLOB_RECURSE ENGINE_INCLUDE_FILES ${PROJECT_SOURCE_DIR}/engine/include/*.h)

include_directories (include)

add_executable (engine ${ENGINE_SRC_FILES})

set_target_properties (engine PROPERTIES
	OUTPUT_NAME engine
	CXX_STANDARD 17
    CXX_EXTENSIONS OFF
)

if (WIN32)
	foreach(SRC_FILE ${ENGINE_SRC_FILES})
		source_group(src FILES SRC_FILE)
	endforeach()
	foreach(INCLUDE_FILE ${ENGINE_INCLUDE_FILES})
		source_group(include FILES INCLUDE_FILE)
	endforeach()
endif()