# Giggy — Text-to-Speech API for Voice Agents

Giggy is a text-to-speech (TTS) API for developers building voice agents and voice-enabled products.

Generate speech through the official SDK, native REST API, OpenAI-compatible API, or Model Context Protocol (MCP).

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
POST https://giggy.ai/v1/text-to-speech
```

OpenAI-compatible speech:

```text
POST https://giggy.ai/v1/audio/speech
```

Account voice catalog (requires a Giggy API key):

```text
GET https://giggy.ai/v1/voices
```

Use the returned `voices[].voice_id` UUID as `voiceId`.

OpenAPI specification:

https://giggy.ai/v1/openapi.json

## Documentation

- [Speech API documentation](https://giggy.ai/docs/speech-api)
- [API pricing](https://giggy.ai/pricing)
- [JavaScript/TypeScript SDK](https://github.com/giggy-ai/giggy-js)
- [Integration examples](https://github.com/giggy-ai/giggy-examples)
- [MCP setup](https://github.com/giggy-ai/giggy-mcp)
