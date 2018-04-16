cmake_minimum_required (VERSION 2.6)
project (leptjson_test C)

if (CMAKE_C_COMPILER_ID MATCHES "GNU|Clang")
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -ansi -pedantic -Wall")
endif()

aux_source_directory(. DIRSRCS)
include_directories(./ ./tutorial01)
#add_subdirectory(tutorial01)
add_library(leptjson ./tutorial01/leptjson.c)
add_executable(leptjson_test ./tutorial01/test.c)
target_link_libraries(leptjson_test leptjson)

