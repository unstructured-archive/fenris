# Build and CI Notes

## Local prerequisites

- CMake
- C++ compiler (g++)
- `protobuf-compiler` (Protobuf 3.21 exactly, matching `find_package(Protobuf 3.21 EXACT ...)`)
- `libprotobuf-dev` (Protobuf 3.21 exactly)
- Git submodules initialized (`git submodule update --init --recursive`)

## Local debug build

```bash
cmake -S . -B build -DUNIT_TESTING=ON -DCMAKE_BUILD_TYPE=Debug
cmake --build build -j"$(nproc)"
ctest --test-dir build --output-on-failure --verbose
```

## Packaging

FENRIS exposes CPack configuration through the root `CMakeLists.txt`.

```bash
cpack --config build/CPackConfig.cmake
```

This produces a `.tar.gz` package.
