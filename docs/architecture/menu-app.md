# Menu App

**Architecture**  
Menu App

```mermaid
flowchart TB
  subgraph Store["Store"]
    MainState[main.menu, apps, ...]
    DisplayState[display state]
  end

  subgraph MenuApp["MenuApp (Kivy)"]
    Header[menu_header.py]
    Central[menu_central.py\npages, apps, settings]
    Footer[menu_footer.py]
    Home[home_page.py / .kv]
    Notifications[notification_info]
  end

  subgraph Headless["headless-kivy"]
    Buffer[Off-screen buffer]
  end

  subgraph Output["Output"]
    LCD[Physical display]
    Web[Web UI stream]
  end

  MainState --> Central
  MainState --> Home
  DisplayState --> Header
  DisplayState --> Buffer
  Header --> Buffer
  Central --> Buffer
  Footer --> Buffer
  Home --> Buffer
  Notifications --> Buffer
  Buffer -->|render_on_display| LCD
  Buffer --> Web
```

The **Menu App** is the main Kivy-based GUI. It draws the home screen, menus, and app content on the device display (or headless buffer for the web UI). It lives in `ubo_app/menu_app/` and is started from `ubo_app/main.py`.

## What you see

- **Entry** — `MenuApp` in `menu_app/menu.py` extends `MenuAppCentral`, `MenuAppFooter`, `MenuAppHeader`, and `UboApp` (from `ubo_gui`). It subscribes to store state and reacts to actions/events (e.g. blank display, redraw).
- **Structure**:
  - **menu_central.py** — Central content (pages, apps, settings).
  - **menu_header.py** — Header (e.g. title, icons).
  - **menu_footer.py** — Footer (e.g. back/home, navigation hints).
  - **home_page.py** / **home_page.kv** — Home screen layout (gauges, volume, buttons).
  - **notification_info.py** / **notification_info.kv** — Notification UI.
  - **menu_notification_handler.py** — Handles notification display from the store.
- **Display** — The app uses **headless-kivy**: rendering is done off-screen; `ubo_app.display.render_on_display` sends the framebuffer to the physical display (or emulation). Display state (e.g. blanked) is in the store and the menu app shows a blank overlay when the display is blanked.
- **State** — Menus and open apps come from the store (e.g. `main.menu`, registered apps/settings). The menu app subscribes via autorun/selectors and updates the widget tree when state changes.
- **Input** — Keypad and keyboard input are handled by services; they dispatch actions that the store and menu app react to (e.g. menu navigation, L1/L2/L3 select).

## Navigation

- [Overview](overview.md) — Architecture summary.
- [Ubo App → Home screen](../index.md) — User-facing home screen.
- [Ubo App → Menu](../home/menu.md) — Menu and navigation.
- [Services → Display](../services/display.md) — Display service and redraw events.
