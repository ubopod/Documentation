# Testing

**Development**  
Testing

![Testing](assets/images/development/testing.png)

*Image: Test run / CI (placeholder).*

Ubo App uses **pytest** for unit and integration tests. Tests can run on the desktop (optionally in Docker for consistent snapshots) or on the device.

## What you see

- **Test layout** — `tests/`: `conftest.py` (fixtures, snapshot prefix by RPi vs desktop), `fixtures/` (app, store, load_services, mock_camera, mock_environment, stability, menu helpers), `flows/` (e.g. WiFi flow with store/window snapshots), `integration/` (core and services integration), `store/`, `reproduction/`, `utils/`.
- **Fixtures** — `AppContext`, `LoadServices`, `MockCamera`, `Stability`, `store`, `store_monitor`, `store_snapshot`, `wait_for`, `wait_for_empty_menu`, `window_snapshot` (from headless-kivy-pytest and redux-pytest). Snapshots are compared against results under `tests/flows/results/` and `tests/integration/results/` (e.g. `store-*.jsonc`, `window-*.hash`).
- **Running locally** — `uv run poe test` (or `pytest`). For consistent DPI/snapshots, run in Docker: build images with `uv run poe build-docker-images`, then e.g. `docker run --rm -it -v .:/ubo-app -v ubo-app-dev-uv-cache:/root/.cache/uv ubo-app-test`. Pass pytest args after `--`, e.g. `-- -svv tests/integration/test_core.py`.
- **On device** — One-time: `uv run poe device:test:copy`, `uv run poe device:test:deps`. Then: `uv run poe device:test` (optionally with `--copy`, `--run`, `--results`, `--index`). Wrapper script: `scripts/test_on_device.sh`.
- **Lint and typecheck** — `uv run poe lint`, `uv run poe lint --fix`; `uv run poe typecheck` (may require stubs on non-RPi; see README).

## Navigation

- [Development → Scripts](scripts.md) — Proto, web app, Docker images
- [Development → Deployment](deployment.md) — Deploy and run on device
- [Getting Started](../getting-started.md) — Dev environment setup
