# Deployment

**Development**  
Deployment

Deployment covers building Ubo App, installing it on a Raspberry Pi (or Ubo Pod), and running it as a service. For end users, see [Getting Started](../getting-started.md) (image or install script). For developers, this page describes the **deploy-to-device** workflow.

## What you see

- **Prerequisites** — SSH access to the device. Add a host in `~/.ssh/config`, e.g. `Host ubo-development-pod` / `Host ubo-development-pod-1` with `HostName` and `User pi`. The deploy script uses `ubo-development-pod-$index` (default index 1). Ensure the device has `ubo` user and `/opt/ubo` (e.g. from a prior image or install).
- **Build** — `uv build` produces a wheel in `dist/`; the RPC workspace member is built too. Deploy script copies the latest `ubo_app-*.whl` and `ubo_app_raw_bindings-*.whl` to the device.
- **Install on device** — Script installs wheels with `pip install --no-index --upgrade --force-reinstall` into the device’s venv (e.g. `/opt/ubo/env`). With `--deps`, also upgrades dependencies.
- **Bootstrap and env** — With `--bootstrap`, runs `ubo-bootstrap`, reloads systemd, restarts `ubo-system.service`. With `--env`, copies `.pod.dev.env` into the app package on the device for development env vars.
- **Run** — After deploy, run the app: `poe device:deploy:restart` (graceful restart via systemctl) or `poe device:deploy:kill` (kill process; systemd may restart if enabled). One-time full setup: `poe device:deploy:complete` (deps + bootstrap + restart).
- **Packer** — `scripts/packer/` contains Packer configs (`image.pkr.hcl`, `image-local.pkr.hcl`) for building OS images that include Ubo App.
- **CI** — `.github/workflows/` (e.g. `integration_delivery.yml`, `publish_to_pypi.yml`) run tests and publish; see repo for exact steps.

## Navigation

- [Development → Testing](testing.md)
- [Development → Scripts](scripts.md)
- [Getting Started](../getting-started.md)
- [Architecture → System](../architecture/system.md)
