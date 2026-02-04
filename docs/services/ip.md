# IP

**Services**  
IP

![IP](assets/images/services/ip.png)

*Image: IP / network interfaces (placeholder).*

The **IP** service tracks network interfaces and connection status (e.g. whether the device has an IP and is considered “connected”). Used by the status bar and network settings.

## What you see

- **State** (`IpState`) — Interfaces list, “is connected” flag.
- **Actions** — `IpUpdateInterfacesAction`, `IpSetIsConnectedAction`.
- **Events** — May emit when connection state changes.
- **Implementation** — `ubo_app/services/030-ip/`: constants, reducer, setup, ubo_handle; uses `netifaces` and/or NetworkManager.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → Network](../home/settings/network.md)
- [Services → Ethernet](ethernet.md)
- [Services → Wi-Fi](wifi.md)
