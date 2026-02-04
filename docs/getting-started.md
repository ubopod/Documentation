# Getting Started

**Getting Started**

This guide helps you set up and run Ubo App—the application that provides a unified interface and tools for hardware-integrated apps on Raspberry Pi (4 & 5) and compatible devices.

## What you need

- **Hardware**: Raspberry Pi 4 or 5 (recommended 8GB RAM for local LLM use). For audio, infrared, sensors, and LED ring, use an [Ubo Pod](https://getubo.com) or compatible HATs.
- **Setup**: Either a pre-packaged image (recommended) or an existing OS with the install script.

## Installation options

### Pre-packaged image

1. Download an image from the [release section](https://github.com/ubopod/ubo-app/releases).
2. Use [Raspberry Pi Imager](https://www.raspberrypi.com/software/) and choose **Custom image** to select the downloaded file.
3. Write the image to an SD card and boot your device.

This is the fastest way to get Ubo App running. For more detail, see [ubo-image](https://github.com/ubopod/ubo-image).

### Install on existing OS

On a supported Linux system (e.g. Raspberry Pi OS), run:

```bash
curl -sSL https://raw.githubusercontent.com/ubopod/ubo-app/main/ubo_app/system/scripts/install.sh | sudo bash
```

Optional environment variables:

- `WITHOUT_DOCKER=true` — skip Docker installation.
- `TARGET_VERSION=<version>` — install a specific version.

Installation uses `/opt/ubo` and installs required Debian packages (e.g. `accountsservice`, `hostapd`, `python3-picamera2`, `rpi-lgpio`). Review the [install script](https://raw.githubusercontent.com/ubopod/ubo-app/main/ubo_app/system/scripts/install.sh) before running.

## First run

After boot (or installation), the **home screen** appears. From there you can:

- Open the **Menu** (hamburger icon) for [Apps](home/apps.md), [Settings](home/settings.md), and [About](home/about.md).
- Use **Notifications** and **Power** from the home screen.
- Adjust volume and use **UP** / **DOWN** for navigation.

See [Ubo App → Home screen](index.md) and [Ubo interface](ubo-interface.md) for the full UI guide.

## Development

To contribute or run from source:

1. Install [uv](https://docs.astral.sh/uv/) and clone the repo (with [git-lfs](https://git-lfs.github.com/) for assets).
2. Run `uv sync --dev`, then generate protobufs and build the web app (see [Development → Scripts](development/scripts.md)).
3. Run with `HEADLESS_KIVY_DEBUG=true uv run ubo` for local/emulated UI.

See [Development](development/testing.md) for testing, scripts, and deployment.

## Navigation

- **[Ubo App](index.md)** — Home screen and device UI (menu, apps, settings).
- **[Architecture](architecture/overview.md)** — Store, services, RPC, engines, system, menu app.
- **[Services](services/audio.md)** — Technical docs for each service (audio, display, keypad, etc.).
- **[Development](development/testing.md)** — Testing, scripts, deployment.
- **[Reference](reference/proto.md)** — gRPC and Protocol Buffers.
