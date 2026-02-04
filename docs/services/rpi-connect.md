# RPi Connect

**Services**  
RPi Connect

![RPi Connect](assets/images/services/rpi-connect.png)

*Image: RPi Connect (placeholder).*

The **RPi Connect** service manages Raspberry Pi Connect setup: download/install state, pending connection, and status. Users can enable remote access via the RPi Connect flow (e.g. QR or sign-in).

## What you see

- **State** (`RPiConnectState`) — Downloading, pending, status, service state.
- **Actions** — `RPiConnectStartDownloadingAction`, `RPiConnectDoneDownloadingAction`, `RPiConnectSetPendingAction`, `RPiConnectSetStatusAction`, `RPiConnectUpdateServiceStateAction`.
- **Implementation** — `ubo_app/services/050-rpi-connect/`: commands, sign_in_page, rpi_connect_qrcode_page, reducer, setup, ubo_handle.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → RPi Connect](../home/settings/rpi-connect.md)
- [Home → Settings → Remote](../home/settings/remote.md)
