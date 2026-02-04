# SSH

**Services**  
SSH

![SSH](assets/images/services/ssh.png)

*Image: SSH settings (placeholder).*

The **SSH** service manages SSH server state (enabled/disabled) and exposes it in the store. The settings UI reads this state and may trigger enable/disable via system manager or configuration.

## What you see

- **State** (`SSHState`) — Whether SSH is enabled (and any related flags).
- **Actions** — `SSHUpdateStateAction`, `SSHClearEnabledStateAction`.
- **Implementation** — `ubo_app/services/050-ssh/`: reducer, setup, ubo_handle.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → SSH](../home/settings/ssh.md)
- [Home → Settings → Remote](../home/settings/remote.md)
