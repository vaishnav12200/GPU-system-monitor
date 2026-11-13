# GPU Monitor

A native Linux GPU monitoring application written in modern C++20.

## Overview

GPU Monitor will collect telemetry from NVIDIA GPUs through NVML and present it in a desktop GUI.

## Goals and planned features

- Query NVIDIA GPU telemetry via NVML (utilization, memory, temperature, power, clocks, fan speed)
- Support multiple GPUs
- Periodic sampling with a history buffer
- Qt 6 desktop GUI with live views
- Clean separation between data collection, monitoring logic and UI

These are plans; none are implemented yet.

## Technology stack

- C++20
- CMake (>= 3.20)
- NVIDIA NVML (GPU telemetry, planned)
- Qt 6 (GUI, planned)
- GoogleTest (testing, optional, planned)

## Current status

**Project initialization only.** The repository contains the directory layout, a minimal CMake build and a stub `main.cpp`. No NVML, monitoring or GUI functionality exists yet.

## Build

```sh
cmake -S . -B build
cmake --build build
./build/gpu_monitor
```

## Planned architecture

See [docs/architecture.md](docs/architecture.md). In short:

- `core/` – shared utilities and common types
- `gpu/nvml/` – NVML backend; `gpu/models/` – GPU data models
- `monitoring/` – sampling and history
- `platform/linux/` – Linux-specific code
- GUI (Qt 6) – to be added later as a separate layer

## License

See [LICENSE](LICENSE).
