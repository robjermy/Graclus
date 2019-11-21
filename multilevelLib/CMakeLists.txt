
# list sources files
set(SRC 
  wkkm.c 
  mlkkm.c
)

add_library(multilevelLib
  ${SRC}
)

target_include_directories(multilevelLib PRIVATE "../metisLib")