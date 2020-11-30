# so5-example-vcpkg

so5-example-vcpkg shows how to build a simple example of
[SObjectizer](https://github.com/stiffstream/sobjectizer).

# How to obtain and build

## Prerequisites

so5-example-vcpkg requires C++ compiler with C++17 support, vcpkg and CMake.

## Obtaining

Just clone so5-example-vcpkg from GitHub:

```sh
git clone https://github.com/stiffstream/so5-example-vcpkg
cd so5-example-vcpkg
```

## Building

### Obtaining the dependencies

so5-example-vcpkg uses SObjectizer so it should be obtained via vcpkg:

```sh
vcpkg install sobjectizer
```

### Building

The build of so5-example-vcpkg is performed via CMake. Please note the usage of vcpkg's toolchain file:

```sh
cd so5-example-vcpkg
mkdir cmake_build
cd cmake_build
cmake -DCMAKE_TOOLCHAIN_FILE=<path-to-your-vcpkg>/scripts/buildsystems/vcpkg.cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=target .
cmake --build .
cmake --build . --target install
```

Executable file(s) will be placed in `target/bin` subfolder.
