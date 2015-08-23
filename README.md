## libb64
My own fork of http://libb64.sourceforge.net/

This library is a stripped-down version of the original libb64.

The build system is CMake (3.1+ only) and the only target being built is the `libb64` static library.
Code examples has been removed. If you really need them, you can still find them in the [original repository][repo].


### How to build

Let's assume you have a target `foo` and you want to link `libb64` to it.

1. Copy the whole repository in the root folder of your CMake-based project

2. Add the command `add_subdirectory(libb64)` to your root `CMakeLists.txt`, *before* you define your target `foo`.

3. Update the `CMakeLists.txt` file where you define `foo` with the following lines:

```CMake
include_directories(${CMAKE_SOURCE_DIR}/libb64/include)

add_executable(foo foo.cpp)    # you already have either this or add_library() if foo is a library

# Define the buffer size for libb64 (MANDATORY!)
# A larger size should be faster, but takes more runtime memory
# Example sizes: 4096, or 65536 or 16777216
target_compile_definitions(foo PRIVATE BUFFERSIZE=16777216)

target_link_libraries(foo b64)

```


[repo]: http://sourceforge.net/p/libb64/git/ci/master/tree/
