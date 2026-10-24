# Giggy — Speech-to-Text and Text-to-Speech Developer Tools

Giggy provides speech-to-text (STT) and text-to-speech (TTS) APIs, official Python and JavaScript/TypeScript SDKs, and integrations for developers building voice agents and voice-enabled products.

Transcribe recordings or submit short live PCM sessions through the SDKs. Generate speech through REST, SDKs, OpenAI-compatible TTS, or MCP. MCP also supports recorded-audio transcription.

## Choose your developer tool

| Build | Tool and quickstart | Current scope |
| --- | --- | --- |
| Python speech application | [giggy](https://github.com/giggy-ai/giggy-python) · [PyPI 0.1.3](https://pypi.org/project/giggy/0.1.3/) | Python 3.10+; TTS, recording STT and short live microphone sessions. |
| Node.js / TypeScript application | [@giggy-ai/sdk](https://github.com/giggy-ai/giggy-js) · [npm 0.1.1](https://www.npmjs.com/package/@giggy-ai/sdk) | Node.js 22+; TTS, recording STT and short live PCM sessions. Application owns capture. |
| Pipecat voice agent | [pipecat-giggy](https://github.com/giggy-ai/pipecat-giggy) | Source 0.3.0.dev0 adds current WebSocket STT; PyPI 0.2.0 uses its earlier transport. Python 3.11+, Pipecat 1.12.0. |
| n8n voiceover workflow | [n8n-nodes-giggy](https://github.com/giggy-ai/n8n-nodes-giggy#example-workflow) | Published 0.1.0; self-hosted TTS/voice discovery. Cloud verification not established. |
| Coding assistant | [Giggy MCP and agent skill](https://github.com/giggy-ai/giggy-mcp#install-for-ai-coding-agents) | Remote TTS/recorded STT tools; each user supplies a key. Plugin approvals are separate. |
| LiveKit integration | [Native Giggy source PR](https://github.com/livekit/agents/pull/7659) | Native TTS and streaming WebSocket STT; open upstream PR, not a released plugin. |
| Vapi or Jambonz integration | [Partner guide](https://github.com/giggy-ai/giggy-examples#partner-integrations) | Vapi custom TTS; Jambonz-compatible live STT WebSocket. No native provider listing is claimed. |

Start with the [developer tool guide](https://giggy.ai/docs/speech-api#api-developer-tools), [runnable examples](https://github.com/giggy-ai/giggy-examples), [API reference](https://giggy.ai/docs/api-reference), or [Voice AI Essentials course](https://giggy.ai/academy/voice-ai-essentials). Check [pricing](https://giggy.ai/pricing) before using paid modes. OpenAI compatibility here covers TTS, not STT.

New integrations use `https://api.giggy.ai/v1`. Live STT defaults to `wss://api.giggy.ai/v1/audio/transcriptions`, with authenticated start, binary PCM and stop on one socket. Existing `https://giggy.ai/v1` clients remain supported. SDK WebSocket changes require their source checkout until a new package release; MCP remains at `https://giggy.ai/mcp`.

## Start here

### 1. Generate speech with Node.js or TypeScript

Use the official Giggy SDK:

[giggy-js — JavaScript/TypeScript SDK](https://github.com/giggy-ai/giggy-js)

Install:

```bash
npm install @giggy-ai/sdk
```

Generate speech:

```js
import { writeFile } from 'node:fs/promises';
import { Giggy } from '@giggy-ai/sdk';

const giggy = new Giggy({
  apiKey: process.env.GIGGY_API_KEY,
});

const audio = await giggy.speech.create({
  text: 'Hello from Giggy.',
  voiceId: process.env.GIGGY_VOICE_ID,
});

await writeFile('speech.mp3', audio);
```

The SDK requires Node.js 22 or newer. Keep API keys server-side.

### 2. Integrate Giggy into a voice agent

[giggy-examples — Runnable integration examples](https://github.com/giggy-ai/giggy-examples)

Examples include:

- [LiveKit TTS](https://github.com/giggy-ai/giggy-examples/tree/main/livekit/python)
- [Pipecat TTS](https://github.com/giggy-ai/giggy-examples/tree/main/pipecat/python)
- [Vapi custom TTS](https://github.com/giggy-ai/giggy-examples/tree/main/vapi)
- [OpenAI-compatible TTS](https://github.com/giggy-ai/giggy-examples/tree/main/node/openai-compatible)
- [Native Node.js TTS](https://github.com/giggy-ai/giggy-examples/tree/main/node/basic-tts)
- [Native Python TTS](https://github.com/giggy-ai/giggy-examples/tree/main/python/basic-tts)

### 3. Connect Giggy to an AI agent

[giggy-mcp — Remote MCP speech tools](https://github.com/giggy-ai/giggy-mcp)

Giggy exposes a Streamable HTTP MCP endpoint:

```text
https://giggy.ai/mcp
```

Configuration examples are available for Codex, Claude Code, Cursor, VS Code, Cline, and supported MCP clients.

## Core APIs

Native Giggy text-to-speech:

```text
POST https://api.giggy.ai/v1/text-to-speech
```

OpenAI-compatible speech:

```text
POST https://api.giggy.ai/v1/audio/speech
```

Account voice catalog (requires a Giggy API key):

```text
GET https://api.giggy.ai/v1/voices
```

Use the returned `voices[].voice_id` UUID as `voiceId`.

OpenAPI specification:

https://api.giggy.ai/v1/openapi.json

## Documentation

- [Speech API documentation](https://giggy.ai/docs/speech-api)
- [API pricing](https://giggy.ai/pricing)
- [JavaScript/TypeScript SDK](https://github.com/giggy-ai/giggy-js)
- [Integration examples](https://github.com/giggy-ai/giggy-examples)
- [MCP setup](https://github.com/giggy-ai/giggy-mcp)
