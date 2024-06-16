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
1. ```CMakeLists.txt```: This is a text file placed at the root of your project source directory. It contains instructions written in CMake's own scripting language, specifying how to build your project.
2. ```Generators```: CMake acts as a frontend, generating native build system files based on the specified generator. Common generators include Unix Makefiles, Visual Studio project files, Xcode project files, and more.
3. ```Variables```: CMake allows defining and using variables to store project information, paths, compiler flags, etc. This simplifies managing configuration and makes your CMakeLists.txt more adaptable.
4. ```Commands```: CMake provides a rich set of commands for various build tasks. These include finding libraries, setting compiler flags, defining targets (executables, libraries), and more.
