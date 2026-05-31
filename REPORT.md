# Лабораторная работа №4 — CI/CD (GitHub Actions)

[![CMake CI](https://github.com/gest475/lab04/actions/workflows/cmake.yml/badge.svg)](https://github.com/gest475/lab04/actions/workflows/cmake.yml)

## Цель

Настроить непрерывную интеграцию (CI) для проекта из lab03:
- Linux (gcc) — GitHub Actions

> **Примечание:** Travis CI стал платным с 2020 года, поэтому использован **GitHub Actions** — бесплатный аналог с аналогичной функциональностью.

## Конфигурация

Файл `.github/workflows/cmake.yml`:

```yaml
name: CMake CI

on:
  push:
    branches: [ "main", "master" ]
  pull_request:
    branches: [ "main", "master" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v4

    - name: Configure CMake
      run: cmake -B build -DCMAKE_BUILD_TYPE=Release

    - name: Build
      run: cmake --build build --config Release

    - name: Run HelloWorld
      run: ./build/hello_world

    - name: Run Solver
      run: ./build/solver
```
## локальная сборка
```mkdir build && cd build
cmake ..
cmake --build .
./hello_world
./solver

```
