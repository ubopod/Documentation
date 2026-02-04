# Audio

**Services**  
Audio

*Image: Audio service / volume UI (placeholder - no dedicated UI screen).*

The **Audio** service manages playback, recording, volume, and mute for input and output devices. It uses ALSA/PulseAudio on Raspberry Pi and can trigger driver installation via the system manager.

## What you see

- **State** (`AudioState`) — Volume and mute for input/output, recording state, current sample/chime playback.
- **Actions** — `AudioSetVolumeAction`, `AudioChangeVolumeAction`, `AudioSetMuteStatusAction`, `AudioToggleMuteStatusAction`; `AudioPlayChimeAction`, `AudioPlayAudioSampleAction`, `AudioPlayAudioSequenceAction`; `AudioStartRecordingAction`, `AudioStopRecordingAction`, `AudioPlayRecordingAction`; `AudioInstallDriverAction` (triggers system manager).
- **Events** — e.g. `AudioPlayChimeEvent`, `AudioPlaybackDoneEvent`, `AudioInstallDriverEvent`. Other services (e.g. notifications) use chimes for feedback.
- **Implementation** — `ubo_app/services/000-audio/`: `setup.py`, `reducer.py`, `ubo_handle.py`; uses `AudioManager` and optional system install flow.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Home → Settings → Display](../home/settings/display.md) — Volume on home screen
- [Home → Settings → Accessibility](../home/settings/accessibility.md) — Speech synthesis/recognition
