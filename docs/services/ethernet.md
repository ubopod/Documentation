# Ethernet

**Services**  
Ethernet

![Ethernet](assets/images/services/ethernet.png)

*Image: Ethernet / wired network (placeholder).*

The **Ethernet** service manages wired network connection state and configuration. It integrates with NetworkManager (on Raspberry Pi) and updates the store with link state.

## What you see

- **State** — Connection state (e.g. connected/disconnected), interface details. May be represented under network/status in the store.
- **Actions** — Update connection state; system manager may be used for some configuration.
- **Implementation** — `ubo_app/services/030-ethernet/`: `ethernet_manager.py`, `setup.py`, `reducer.py`, `ubo_handle.py`. Uses `sdbus-networkmanager` on aarch64.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → Network](../home/settings/network.md)
- [Services → IP](ip.md) — IP and interfaces
- [Services → Wi-Fi](wifi.md)
