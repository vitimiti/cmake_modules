# CMake Modules

A simple repository that holds premade cmake modules to more easily kickstart projects.

## How to use

Download the project and start using the modules as they are automatically appended.

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
