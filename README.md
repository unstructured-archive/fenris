# FENRIS

[![Ubuntu Build and Test](https://github.com/std-fenris/fenris/actions/workflows/ubuntu.yml/badge.svg)](https://github.com/std-fenris/fenris/actions/workflows/ubuntu.yml)

Fast Encrypted Networked Robust Information Storage.

## Build

```bash
git clone --recurse-submodules https://github.com/unstructured-archive/fenris.git
cd fenris
cmake -S . -B build -DUNIT_TESTING=ON -DCMAKE_BUILD_TYPE=Debug
cmake --build build -j"$(nproc)"
```

## Run tests

```bash
ctest --test-dir build --output-on-failure --verbose
```

## Create package

```bash
cpack --config build/CPackConfig.cmake
```

See `/docs/BUILD.md` for dependency notes and CI details.
