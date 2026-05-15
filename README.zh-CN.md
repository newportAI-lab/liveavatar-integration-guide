[中文]() | [English](./README.md)

# Facemarket Live Avatar — 集成指南

[Facemarket Live Avatar](https://facemarket.ai) 的开发者集成文档。覆盖所有支持的集成模式——从 5 分钟快速开始到完全自管 RTC 部署。

## 文档

- English: [Live Avatar Integration Guide](./Live%20Avatar%20Integration%20Guide.md)
- 中文: [Live Avatar Integration Guide (中文版)](./Live%20Avatar%20Integration%20Guide.zh-CN.md)

## 内容概览

| 章节 | 说明 |
| --- | --- |
| I. Quick Start | 5 分钟快速跑通全托管流水线 |
| II. 进阶模式选择 | 集成模式决策表 |
| III. 核心概念 | 凭证、会话、房间、参与者角色与术语缩写 |
| IV. 从后端启动会话 | Server-to-Server 会话生命周期 API |
| V. WebSocket Agent | 通过 WebSocket 完全控制对话逻辑 |
| VI. WebRTC 模式 | 自研语音 Agent，支持平台 RTC 与自备 RTC |
| VII. 前端 SDK | `@sanseng/liveavatar-js-sdk` JS SDK 参考 |
| VIII. 沙箱环境 | 每月 30 分钟免费测试额度 |
| IX. FAQ | 常见错误码与故障排查 |

## 集成模式一览

| 模式 | 适合场景 | 接入成本 |
| --- | --- | --- |
| 全托管 | 快速开始，平台接管 ASR → LLM → TTS；支持自选模型与自带 API Key | 极低 |
| WebSocket Agent | Serverless / 内网环境，完全控制对话逻辑 | 低 |
| Platform RTC | 自研语音 Agent，追求极低延迟 | 高 |
| BYO RTC | 私有化部署，完全自管 RTC 基础设施 | 极高 |

## 快速开始

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

完整 5 步教程见 [第一章](./Live%20Avatar%20Integration%20Guide.md#i-quick-start-up-and-running-in-5-minutes)。

## 后端 SDK

- **Java**: [newportAI-lab/liveavatar-channel](https://github.com/newportAI-lab/liveavatar-channel)
- **Python**: [newportAI-lab/liveavatar-channel-python](https://github.com/newportAI-lab/liveavatar-channel-python)

## License

Apache License 2.0 — 详见 [LICENSE](./LICENSE)。
