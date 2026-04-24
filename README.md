# Facemarket Live Avatar — Integration Guide

Developer documentation for integrating [Facemarket Live Avatar](https://facemarket.ai) into your application. Covers every supported integration mode from a 5-minute quick start to fully self-managed RTC deployments.

## Contents

- [Live Avatar Integration Guide](./Live%20Avatar%20Integration%20Guide.md)

## What's Inside

| Chapter | Description |
| --- | --- |
| I. Quick Start | Up and running in 5 minutes with the default managed pipeline |
| II. Choosing an Advanced Mode | Decision table for picking the right integration mode |
| III. Key Concepts | Credentials, sessions, rooms, participant roles, and abbreviations |
| IV. API Key Hosting | Let the platform proxy your LLM — no inference infra required |
| V. WebSocket Mode | Full control over conversation logic via WS Outbound or WS Inbound |
| VI. WebRTC Mode | Custom voice agent with Platform RTC or BYO (self-managed) RTC |
| VII. Frontend SDK | JS SDK reference for the `@sanseng/livekit-ws-sdk` package |
| VIII. Sandbox | 30 free minutes/month for end-to-end testing |
| IX. FAQ | Common error codes and troubleshooting |

## Integration Modes at a Glance

| Mode | Best For | Effort |
| --- | --- | --- |
| Default (managed) | Get started fast; platform handles ASR → LLM → TTS | Minimal |
| API Key Hosting | Bring your own LLM without running inference infra | Low |
| WS Outbound | Public backend, full control over conversation logic | Medium |
| WS Inbound | Serverless / private network, full control | Low |
| Platform RTC | Custom voice agent, ultra-low latency | High |
| BYO RTC | Private deployment, fully self-managed RTC | Very High |

## Quick Start

```bash
npm install @sanseng/livekit-ws-sdk
```

```javascript
import { createClient } from '@sanseng/livekit-ws-sdk';

const client = createClient({
  avatarId: 'your_avatar_id',
  video: { containerElement: document.getElementById('avatar') },
});

client.setAuthToken(sessionToken); // obtained from your backend
await client.connect();
client.startAudioCapture();
```

See [Chapter I](./Live%20Avatar%20Integration%20Guide.md#i-quick-start-up-and-running-in-5-minutes) for the full 5-step walkthrough.

## Backend SDKs

- **Java**: [newportAI-lab/liveavatar-channel](https://github.com/newportAI-lab/liveavatar-channel)
- **Python**: [newportAI-lab/liveavatar-channel-python](https://github.com/newportAI-lab/liveavatar-channel-python)

## License

Apache License 2.0 — see [LICENSE](./LICENSE).
