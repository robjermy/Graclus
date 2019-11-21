cmake_minimum_required(VERSION 3.15)

project(graclus)

if(CMAKE_SIZEOF_VOID_P EQUAL 8)
	add_definitions(-DNUMBITS=64)
endif(CMAKE_SIZEOF_VOID_P EQUAL 8)

add_subdirectory(multilevelLib)
add_subdirectory(metisLib)

file(GLOB LIBRARY_FILES_C "metisLib/*.c")
file(GLOB LIBRARY_FILES_H "metisLib/*.h")

add_library(graclus
	${LIBRARY_FILES_C}
	${LIBRARY_FILES_H}
	./multilevelLib/wkkm.c
	./multilevelLib/mlkkm.c
)

target_include_directories(graclus PUBLIC "./metisLib")
target_include_directories(graclus PUBLIC "./multilevelLib")