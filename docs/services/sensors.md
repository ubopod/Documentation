# Sensors

**Services**  
Sensors

![Sensors](assets/images/services/sensors.png)

*Image: Sensors (placeholder).*

The **Sensors** service reads onboard sensors (e.g. ambient light, temperature on Ubo Pod) and reports readings to the store. The home screen or other UI can show temperature and light level.

## What you see

- **State** (`SensorsState`) — List of `SensorState` (type, value, unit, etc.).
- **Actions** — `SensorsReportReadingAction` — updates sensor values in state.
- **Implementation** — `ubo_app/services/040-sensors/`: reducer, setup, ubo_handle; uses Adafruit CircuitPython drivers (e.g. PCT2075, VEML7700) on RPi. Non-RPi may have mocks or no sensors.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home screen](../index.md) — Temperature on status bar
- [Home → Settings → Hardware](../home/settings/hardware.md)
