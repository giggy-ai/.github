# Giggy speech APIs for developers

Build voice experiences using Giggy's REST API, JavaScript and Python SDKs, or speech integrations. Bring your own Giggy account and API key; keep credentials on your server.

[Create a Giggy account](https://giggy.ai/?login=1&utm_source=github&utm_medium=referral&utm_campaign=developer_onboarding&utm_content=org_readme) · [Read the speech API guide](https://giggy.ai/docs/speech-api?utm_source=github&utm_medium=referral&utm_campaign=developer_onboarding&utm_content=org_docs)

## Choose your starting point

| What you want to build | Start here | Status |
| --- | --- | --- |
| A browser voice agent | [Voice Agent Sandbox](https://github.com/giggy-ai/giggy-voice-agent) | Cloud demo; own Giggy + DeepSeek keys |
| A Pipecat pipeline | [pipecat-giggy](https://github.com/giggy-ai/pipecat-giggy) | Giggy-maintained STT/TTS; PyPI package; community integration |
| A Node.js / TypeScript app | [giggy-js](https://github.com/giggy-ai/giggy-js) | `npm install @giggy-ai/sdk`; Node 22+ |
| A Python app | [giggy-python](https://github.com/giggy-ai/giggy-python) | Source installation; SDK not yet on PyPI |
| LiveKit, Vapi or OpenAI-compatible speech | [giggy-examples](https://github.com/giggy-ai/giggy-examples) | Provider-specific compatibility examples |
| Speech tools in an AI client | [giggy-mcp](https://github.com/giggy-ai/giggy-mcp) | Remote MCP setup; durable speech results |

## Your first successful request

1. [Create an account and API key](https://giggy.ai/?login=1&utm_source=github&utm_medium=referral&utm_campaign=developer_onboarding&utm_content=org_readme).
2. Call `GET https://giggy.ai/v1/voices` with `Authorization: Bearer $GIGGY_API_KEY`; select a returned `voices[].voice_id`.
3. Follow the [Node SDK quickstart](https://github.com/giggy-ai/giggy-js#generate-your-first-mp3), [Python SDK quickstart](https://github.com/giggy-ai/giggy-python), or [dependency-free REST example](https://github.com/giggy-ai/giggy-examples#quick-start).
4. Confirm a nonempty `speech.mp3` file. For streaming, use the example's documented PCM format rather than treating raw PCM as MP3.

Requests may consume credits. Consult [current pricing](https://giggy.ai/pricing) and the API documentation for mode limits; latency and cost depend on the request and deployment.

## Integration status

Giggy maintains these SDKs and adapters. Pipecat lists the Giggy community integration; that does not make it maintained by the Pipecat team. The [native LiveKit plugin proposal](https://github.com/livekit/agents/pull/7659) is still under upstream review; use the existing OpenAI-compatible example today. Vapi uses its custom-provider contract. Forks are contribution staging areas, not separate Giggy frameworks.

Setup problem? Open an issue in the relevant repository with your runtime version, a minimal reproduction and sanitized errors. Never share keys, private recordings or account data.
