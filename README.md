# CMake Modules

A simple repository that holds premade cmake modules to more easily kickstart projects.

## How to use

Download the project and do
`list(APPEND CMAKE_MODULE_PATH ${path_to_project}/cmake)` to start using the modules.

For example, if you want to use `FetchContent`, you may do:

```cmake
# Project definition...

include(FetchContent REQUIRED)

FetchContent_Declare(
  vitimiti_cmake_modules
  GIT_REPOSITORY https://github.com/vitimiti/cmake_modules.git
  GIT_TAG main)

FetchContent_MakeAvailable(vitimiti_cmake_modules)

list(APPEND CMAKE_MODULE_PATH ${vitimiti_cmake_modules_SOURCE_DIR}/cmake)

# Rest of the project configuration...
```

## Current Modules

- DefaultCompilerOptions.cmake

### DefaultCompilerOptions.cmake

After you `include(DefaultCompilerOptions)` in your `CMakeLists.txt` file, you can then use the
function `target_set_default_compile_options(_TARGET _VISIBILITY _WARNINGS_AS_ERRORS)` to
automatically add compiler options with heavy warnings, custom visibility and whether warnings
should be treated as errors or not.

For example, for a project called `MyProject`, wanting errors as warnings and the visibility to be
`PRIVATE` as it is an executable, not a library, you may do:

```cmake
find(DefaultCompilerOptions REQUIRED)
target_set_default_compile_options(MyProject PRIVATE ON)
```
