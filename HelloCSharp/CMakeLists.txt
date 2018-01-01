# https://gitlab.kitware.com/cmake/cmake/commit/9a0d3e2ed66b740c3be9b98d4462929aadf40341
cmake_minimum_required(VERSION 3.10.1)
set(CMAKE_SUPPRESS_REGENERATION true)

# define a variable of project name
set(project_name HelloCSharp)

# define a variable of project name
project (${project_name})

# https://cmake.org/pipermail/cmake/2017-March/065160.html
# OK: CSharp
# NG: CSHARP
enable_language(CSharp)

# define a variable SRC with file GLOB
file(GLOB SRC main.cs)

add_executable(${project_name} ${SRC})

set_property(DIRECTORY PROPERTY VS_STARTUP_PROJECT ${project_name})
