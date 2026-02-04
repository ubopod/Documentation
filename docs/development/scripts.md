# Scripts

**Development**  
Scripts

This page summarizes the main scripts and **poe** tasks used for building, code generation, and running Ubo App in development.

## What you see

- **Entry point** — Run the app: `uv run ubo` (or `HEADLESS_KIVY_DEBUG=true uv run ubo` for debug). System: `ubo-bootstrap`, `ubo-system`, `ubo-hotspot-config`, `ubo-redirect-server` (see `pyproject.toml` `[project.scripts]`).
- **Proto** — Generate action/event protos from Python and compile to Python bindings:
  - `uv run poe proto` — runs `proto:generate` and `proto:compile`.
  - `proto:generate` — runs `ubo_app/rpc/generator/generate_proto.py`, then `buf format`.
  - `proto:compile` — runs `grpc_tools.protoc` for `store.proto`, `secrets.proto`, etc., into `ubo_app/rpc/ubo_bindings/`.
  - Requires [buf](https://github.com/bufbuild/buf) (e.g. `brew install bufbuild/buf/buf`).
- **Web app** — In `ubo_app/services/090-web-ui/web-app/`: `npm install` (first time), `npm run proto:compile`, `npm run build` (or `npm run build:watch`). Top-level: `uv run poe build-web-app`.
- **Docker images** — `uv run poe build-docker-images` builds `Dockerfile.dev` (ubo-app-dev) and `Dockerfile.test` (ubo-app-test) from `scripts/`.
- **Deploy to device** — `scripts/deploy.sh`: build wheels, copy to pod, install; options: `--deps`, `--bootstrap`, `--restart`, `--kill`, `--env`, `--offline`, `--index`. Invoked via `poe device:deploy`, `poe device:deploy:complete`, etc.
- **Test on device** — `scripts/test_on_device.sh`: copy tests, install deps, run pytest, fetch results. Invoked via `poe device:test`, `poe device:test:copy`, etc.
- **Consume** — `scripts/consume.sh` (if used for message/queue consumption in your workflow).

## Navigation

- [Development → Testing](testing.md)
- [Development → Deployment](deployment.md)
- [Reference → Proto](../reference/proto.md)
- [Getting Started](../getting-started.md)
