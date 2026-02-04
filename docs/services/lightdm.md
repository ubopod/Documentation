# LightDM

**Services**  
LightDM

*Image: LightDM / desktop session (placeholder - system service, no UI screen).*

The **LightDM** service tracks and controls the LightDM display manager state (e.g. whether the desktop session is active or enabled). Used for settings that depend on desktop login state.

## What you see

- **State** (`LightDMState`) — Active/enabled state of the LightDM session.
- **Actions** — `LightDMUpdateStateAction`, `LightDMClearEnabledStateAction`.
- **Implementation** — `ubo_app/services/050-lightdm/`: reducer, setup, ubo_handle. May interact with system manager or D-Bus for session state.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → Desktop](../home/settings/desktop.md)
