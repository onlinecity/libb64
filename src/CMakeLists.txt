add_library(b64
    STATIC
    cencode.c
    cdecode.c)

target_compile_options(b64
    PRIVATE
    -O3
    -Wall
    -Wextra
    -Werror
    -pedantic)

