cmake_minimum_required (VERSION 3.25)

set (CMAKE_CXX_STANDARD 20)
set (CMAKE_CXX_STANDARD_REQUIRED ON)

set (CMAKE_C_STANDARD 11)
set (CMAKE_C_STANDARD_REQUIRED ON)

set (CMAKE_CXX_SCAN_FOR_MODULES 0)
set (CMAKE_CONFIGURATION_TYPES Debug Release)

project (Nirvana CXX C)

add_compile_definitions (NIRVANA_NO_BAD_ALLOC)

if (NOT ${CMAKE_RUNTIME_OUTPUT_DIRECTORY})
	set (CMAKE_RUNTIME_OUTPUT_DIRECTORY, "${CMAKE_BINARY_DIR}/$<CONFIG>")
endif ()

include (NirvanaSDK)
include (CTest)

file (TO_CMAKE_PATH $ENV{NIRVANA_CORE_SDK} NIRVANA_CORE_SDK_DIR)

add_subdirectory (Core)
add_subdirectory (Port)
