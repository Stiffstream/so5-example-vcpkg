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

so5-example-vcpkg uses SObjectizer in the form of a static library so it should be obtained via vcpkg. For Linux:

```sh
vcpkg install sobjectizer
```

and for Windows (in 64-bit mode):

```sh
vcpkg install sobjectizer:x64-windows-static-md
```

### Building

The build of so5-example-vcpkg is performed via CMake. Please note the usage of vcpkg's toolchain file.

Building for Linux:

```sh
cd so5-example-vcpkg
mkdir cmake_build
cd cmake_build
cmake -DCMAKE_TOOLCHAIN_FILE=<path-to-your-vcpkg>/scripts/buildsystems/vcpkg.cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=target .
cmake --build . --target install --config Release
```

Building for Windows (note the usage of VCPKG_TARGET_TRIPLET):

```sh
cd so5-example-vcpkg
mkdir cmake_build
cd cmake_build
cmake -DCMAKE_TOOLCHAIN_FILE=<path-to-your-vcpkg>/scripts/buildsystems/vcpkg.cmake -DVCPKG_TARGET_TRIPLET=x64-windows-static-md -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=target .
cmake --build . --target install --config Release
```

Executable file(s) will be placed in `target/bin` subfolder.
