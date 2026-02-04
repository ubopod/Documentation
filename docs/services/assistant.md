# Assistant

**Services**  
Assistant

![Assistant](assets/images/services/assistant.png)

*Image: Assistant / voice AI (placeholder).*

The **Assistant** service powers the voice AI pipeline: STT (speech-to-text), LLM (language model), TTS (text-to-speech), optional image generator, and MCP (Model Context Protocol) servers. Users choose engines and models in settings; the assistant listens, sends to the LLM, and speaks replies.

## What you see

- **State** (`AssistantState`) — Is active; selected STT, LLM, TTS, image generator; selected model; Ollama model download state; MCP servers list; providers list.
- **Actions** — `AssistantSetIsActiveAction`, `AssistantSetSelectedSTTAction`, `AssistantSetSelectedLLMAction`, `AssistantSetSelectedTTSAction`, `AssistantSetSelectedImageGeneratorAction`, `AssistantSetSelectedModelAction`, `AssistantDownloadOllamaModelAction`; `AssistantStartListeningAction`, `AssistantStopListeningAction`, `AssistantToggleListeningAction`; `AssistantUpdateProvidersAction`, `AssistantAddMcpServerAction`, `AssistantToggleMcpServerAction`, `AssistantDeleteMcpServerAction`, `AssistantSyncMcpServersAction`; `AssistantReportAction` for internal events.
- **Implementation** — `ubo_app/services/090-assistant/`: engines_registry, mcp_servers, reducer, setup, ubo_handle; subproject `ubo-service/` contains the voice pipeline (Piper, Vosk, LLM, tools). Uses engines from `ubo_app/engines/`.

## Navigation

- [Architecture → Services](../architecture/services.md)
- [Architecture → Engines](../architecture/engines.md)
- [Home → Settings → Assistant](../home/settings/assistant.md)
- [Services → Speech Recognition](speech-recognition.md)
- [Services → Speech Synthesis](speech-synthesis.md)
