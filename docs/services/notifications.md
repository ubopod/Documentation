# Notifications

**Services**  
Notifications

![Notifications](assets/images/services/notifications.png)

*Image: Notifications list (placeholder).*

The **Notifications** service stores and displays alerts (title, content, importance, chime, progress, dismiss). The home screen shows a bell icon that opens the notifications list; notifications can be sticky, flash, or background.

## What you see

- **State** (`NotificationsState`) — List of notifications (id, title, content, display type, importance, color, icon, progress, etc.).
- **Actions** — `NotificationsAddAction`, `NotificationsDisplayAction`, `NotificationsClearAction`, `NotificationsClearByIdAction`, `NotificationsClearAllAction`. Other services dispatch `NotificationsAddAction` with optional `Chime` for sound feedback.
- **Implementation** — `ubo_app/services/010-notifications/`: reducer and ubo_handle; menu app shows notifications UI and handles dismiss.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Notifications](../home/notifications.md)
- [Services → Audio](audio.md) — Chimes
