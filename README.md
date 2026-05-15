# Facemarket Live Avatar — Integration Guide

Developer documentation for integrating [Facemarket Live Avatar](https://facemarket.ai) into your application. Covers every supported integration mode from a 5-minute quick start to fully self-managed RTC deployments.

## Documentation

- English: [Live Avatar Integration Guide](./Live%20Avatar%20Integration%20Guide.md)
- 中文: [Live Avatar Integration Guide (中文版)](./Live%20Avatar%20Integration%20Guide.zh-CN.md)

## What's Inside

| Chapter | Description |
| --- | --- |
| I. Quick Start | Up and running in 5 minutes with the fully managed pipeline |
| II. Choosing an Advanced Mode | Decision table for picking the right integration mode |
| III. Key Concepts | Credentials, sessions, rooms, participant roles, and abbreviations |
| IV. Start a Session from Backend | Server-to-server session lifecycle API |
| V. WebSocket Agent | Full control over conversation logic via WebSocket |
| VI. WebRTC Mode | Custom voice agent with Platform RTC or BYO (self-managed) RTC |
| VII. Frontend SDK | JS SDK reference for the `@sanseng/liveavatar-js-sdk` package |
| VIII. Sandbox | 30 free minutes/month for end-to-end testing |
| IX. FAQ | Common error codes and troubleshooting |

## Integration Modes at a Glance

| Mode | Best For | Effort |
| --- | --- | --- |
| Fully Managed | Get started fast; platform handles ASR → LLM → TTS. Supports custom models with your own API Key | Minimal |
| WebSocket Agent | Serverless / private network, full control over conversation logic | Low |
| Platform RTC | Custom voice agent, ultra-low latency | High |
| BYO RTC | Private deployment, fully self-managed RTC | Very High |

## Quick Start

```bash
npm install @sanseng/liveavatar-js-sdk
```

```javascript
import { createClient, type PerformanceMetricRecord } from '@sanseng/liveavatar-js-sdk';

const client = createClient({
  connectConfig: {
    type: 'direct',
    config: {
      sfuUrl: '',
      userToken: '',
    },
  },
});
```

See [Chapter I](./Live%20Avatar%20Integration%20Guide.md#i-quick-start-up-and-running-in-5-minutes) for the full 5-step walkthrough.

## Backend SDKs

- **Java**: [newportAI-lab/liveavatar-channel](https://github.com/newportAI-lab/liveavatar-channel)
- **Python**: [newportAI-lab/liveavatar-channel-python](https://github.com/newportAI-lab/liveavatar-channel-python)

## License

Apache License 2.0 — see [LICENSE](./LICENSE).
