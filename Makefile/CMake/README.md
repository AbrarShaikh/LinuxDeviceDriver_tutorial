# CMake
- CMake is an open-source, cross-platform family of tools designed to build, test, package and installation of software by using a compiler-independent method
- CMake is not a build system itself, It acts as a meta-build system, generating build configurations files specific to the native build environment.
- It can invoke native build environments such as Makefiles for Unix, project file in IDE Microsoft Visual Studio, Qt Creator, Ninja, Android Studio, and Apple's Xcode.
- CMake scripts ```CMakeLists.txt``` are platform-independent, enabling the same build instructions to be used across different systems.
```C
cmake_minimum_required(VERSION 3.10)
# Set the project name
project(MyProject)
# Add an executable
add_executable(myapp main.cpp)
```
