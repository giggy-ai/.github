# Giggy — Text-to-Speech API for Voice Agents

Giggy is a text-to-speech (TTS) API for developers building voice agents and voice-enabled products.

Generate speech through the official SDK, native REST API, OpenAI-compatible API, or Model Context Protocol (MCP).

## Start here

### Generate speech with Node.js or TypeScript

Install the official [Giggy JavaScript/TypeScript SDK](https://github.com/giggy-ai/giggy-js):

```bash
npm install @giggy-ai/sdk
```

```js
import { writeFile } from 'node:fs/promises';
import { Giggy } from '@giggy-ai/sdk';

const giggy = new Giggy({ apiKey: process.env.GIGGY_API_KEY });
const audio = await giggy.speech.create({
  text: 'Hello from Giggy.',
  voiceId: process.env.GIGGY_VOICE_ID,
});
await writeFile('speech.mp3', audio);
```

Requires Node.js 22 or newer. Keep API keys server-side.

### Integrate Giggy into a voice agent

[runnable Giggy examples](https://github.com/GRQDigitalCapital/giggy-examples)

- [LiveKit TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/livekit/python)
- [Pipecat TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/pipecat/python)
- [Vapi custom TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/vapi)
- [OpenAI-compatible TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/node/openai-compatible)
- [Native Node.js TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/node/basic-tts)
- [Native Python TTS](https://github.com/GRQDigitalCapital/giggy-examples/tree/main/python/basic-tts)

### Connect Giggy to an AI agent

[giggy-mcp — remote MCP speech tools](https://github.com/GRQDigitalCapital/giggy-mcp)

Giggy exposes a Streamable HTTP MCP endpoint at `https://giggy.ai/mcp`. See the repository for client setup.

## Core APIs

- Native Giggy TTS: `POST https://giggy.ai/v1/text-to-speech`
- OpenAI-compatible TTS: `POST https://giggy.ai/v1/audio/speech`
- Public voice catalog: `GET https://giggy.ai/v1/voices`
- OpenAPI specification: https://giggy.ai/v1/openapi.json

## Documentation

- [Speech API documentation](https://giggy.ai/docs/speech-api)
- [API pricing](https://giggy.ai/pricing)
- [JavaScript/TypeScript SDK](https://github.com/giggy-ai/giggy-js)
- [Integration examples](https://github.com/GRQDigitalCapital/giggy-examples)
- [MCP setup](https://github.com/GRQDigitalCapital/giggy-mcp)
