# Speech Synthesis

**Services**  
Speech Synthesis

![Speech Synthesis](assets/images/services/speech-synthesis.png)

*Image: Speech synthesis / TTS (placeholder).*

The **Speech Synthesis** service handles text-to-speech: engine selection (e.g. Piper, Google, ElevenLabs), model download, and `ReadText` actions. Used by the assistant and accessibility TTS.

## What you see

- **State** (`SpeechSynthesisState`) — Selected engine, engine list, model download state, reading state.
- **Actions** — `SpeechSynthesisSetSelectedEngineAction`, `SpeechSynthesisReadTextAction`, plus engine/model setup actions. Reducer may emit events when playback starts/ends.
- **Implementation** — `ubo_app/services/010-speech-synthesis/`: setup, reducer, ubo_handle; uses engines from `ubo_app/engines/` (Piper, Google, etc.).

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Architecture → Engines](../architecture/engines.md)
- [Home → Settings → Accessibility → Speech Synthesis](../home/settings/accessibility-speech-synthesis.md)
- [Home → Settings → Assistant → Speech Synthesis](../home/settings/assistant-speech-synthesis.md)
