# VS Code

**Services**  
VS Code

![VS Code](../assets/images/settings/vs-code.png)

*Image: VS Code tunnel (placeholder).*

The **VS Code** service manages the VS Code tunnel (code-server / tunnel) for remote development: download state, pending setup, and status. Users enable it from settings and may sign in via QR or web.

## What you see

- **State** (`VSCodeState`) — Downloading, pending, status (e.g. installed, running).
- **Actions** — `VSCodeStartDownloadingAction`, `VSCodeDoneDownloadingAction`, `VSCodeSetPendingAction`, `VSCodeSetStatusAction`.
- **Implementation** — `ubo_app/services/050-vscode/`: commands, login_page, vscode_qrcode_page, reducer, setup, ubo_handle.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → VS Code](../home/settings/vscode.md)
- [Home → Settings → Remote](../home/settings/remote.md)
