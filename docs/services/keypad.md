# Keypad

**Services**  
Keypad

![Keypad](assets/images/services/keypad.png)

*Image: Keypad / physical buttons (placeholder).*

The **Keypad** service reads physical button input (e.g. AW9523 GPIO expander on Ubo Pod) and dispatches key press, hold, unhold, and release actions. These drive menu navigation and L1/L2/L3 shortcuts.

## What you see

- **State** (`KeypadState`) — Tracks key state as needed by the service.
- **Actions** — `KeypadKeyPressAction`, `KeypadKeyHoldAction`, `KeypadKeyUnholdAction`, `KeypadKeyReleaseAction` — carry key identity; the main reducer and menu app use them for navigation (UP, DOWN, L1, L2, L3, BACK, HOME).
- **Implementation** — `ubo_app/services/000-keypad/`: hardware abstraction in `ubo_handle.py`; on non-RPi, keypad may be emulated (e.g. keyboard or web UI).

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Ubo App → Menu](../home/menu.md) — Navigation with keypad
- [Services → Keyboard](keyboard.md) — Keyboard shortcuts
