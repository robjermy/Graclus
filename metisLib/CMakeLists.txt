# list sources files
file(GLOB LIBRARY_FILES_C "*.c")
file(GLOB LIBRARY_FILES_H "*.h")

add_library(metisLib
  ${LIBRARY_FILES_C}
  ${LIBRARY_FILES_H}
)

target_include_directories(metisLib PRIVATE "./")