# Architecture (planned)

Status: design sketch only. Nothing here is implemented yet.

## Layers

1. **Platform** (`platform/linux`): Linux-specific functionality.
2. **GPU** (`gpu/nvml`, `gpu/models`): NVML-backed access to GPU telemetry and the data models describing it.
3. **Monitoring** (`monitoring`): periodic sampling and history built on the GPU layer.
4. **Core** (`core`): shared utilities used by all layers.
5. **GUI** (future): Qt 6 desktop UI consuming the monitoring layer. Not part of the initial scaffold.

## Layout

- `include/gpu_monitor/<module>/` – public headers
- `src/<module>/` – implementations
- `tests/` – future GoogleTest suites
- `resources/` – future assets (icons, etc.)

## Dependency direction

GUI -> monitoring -> gpu -> core; platform is used by gpu/monitoring where needed. Interfaces and APIs will be designed when each module is implemented.
