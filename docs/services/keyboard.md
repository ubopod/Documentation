# Keyboard

**Services**  
Keyboard

![Keyboard](../assets/images/buttons.png)

*Image: Keyboard shortcuts / buttons.*

The **Keyboard** service maps keyboard input (e.g. in development or over SSH) to the same actions as the keypad (navigation, L1/L2/L3, back, home). It allows using a physical keyboard or emulated keys instead of the device keypad.

## What you see

- **State** — No dedicated keyboard state slice; keyboard input is translated into keypad-like actions or direct menu actions.
- **Implementation** — `ubo_app/services/020-keyboard/`: `setup.py`, `ubo_handle.py`; `shortcuts.md` documents key bindings. Input is merged with keypad for a unified navigation model.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Services → Keypad](keypad.md)
- [Home → Settings → Accessibility](../home/settings/accessibility.md)
