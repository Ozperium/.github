# Ozperium

**Open-source tooling for AI developers.** We build the observability layer for the AI-native dev workflow.

---

## AI Dev Workflow Stack

Four tools. One coherent stack. Each solves a distinct problem that shows up when you build seriously with AI.

| Tool | What it does | Install |
|------|-------------|---------|
| **[AgentSpec](https://github.com/Ozperium/agentspec)** | Test AI agent behavior — catch regressions before production | `npm i -g @ozperium/agentspec` |
| **[AICostTracker](https://github.com/Ozperium/aicost-tracker)** | Track token usage and costs across projects — one-line integration | `npm i -g @ozperium/aicost-tracker` |
| **[quota](https://github.com/Ozperium/quota)** | Monitor AI rate limits — know what's left before it stops you | `npm i -g @ozperium/quota` |
| **[Stoke][stoke]** | Agent safety proxy | [Install][stoke-install] |

[stoke]: https://github.com/Ozperium/stoke
[stoke-install]: https://stokegate.com/install

---

## AgentSpec

[![npm version](https://img.shields.io/npm/v/@ozperium/agentspec)](https://www.npmjs.com/package/@ozperium/agentspec)
[![npm downloads](https://img.shields.io/npm/dw/@ozperium/agentspec)](https://www.npmjs.com/package/@ozperium/agentspec)

AI agents are non-deterministic. When you change a prompt, swap a model, or update a tool, behavior shifts in ways you can't predict. AgentSpec lets you write tests that catch those shifts before they reach production.

```bash
npm install -g @ozperium/agentspec
agentspec run --dir tests
```

→ [agentspec.dev](https://agentspec.dev) · [GitHub](https://github.com/Ozperium/agentspec) · [npm](https://www.npmjs.com/package/@ozperium/agentspec) · [Build notes](https://dev.to/pawfromoz/testing-ai-agents-with-agentspec-jest-for-non-deterministic-behavior-55kg)

---

## AICostTracker

[![npm version](https://img.shields.io/npm/v/@ozperium/aicost-tracker)](https://www.npmjs.com/package/@ozperium/aicost-tracker)
[![npm downloads](https://img.shields.io/npm/dw/@ozperium/aicost-tracker)](https://www.npmjs.com/package/@ozperium/aicost-tracker)

Know exactly what you're spending on AI APIs. One line of code auto-logs every OpenAI and Anthropic call:

```typescript
import { track } from '@ozperium/aicost-tracker';
const openai = track(new OpenAI());  // all calls logged automatically
```

→ [GitHub](https://github.com/Ozperium/aicost-tracker) · [npm](https://www.npmjs.com/package/@ozperium/aicost-tracker) · [Build notes](https://dev.to/pawfromoz/stop-manually-logging-your-ai-api-calls-one-line-auto-logging-for-openai-and-anthropic-1b5m)

---

## quota

[![npm version](https://img.shields.io/npm/v/@ozperium/quota)](https://www.npmjs.com/package/@ozperium/quota)
[![npm downloads](https://img.shields.io/npm/dw/@ozperium/quota)](https://www.npmjs.com/package/@ozperium/quota)

See your remaining AI coding quota before it stops you mid-task. Reads `~/.claude` and `~/.codex` locally — no API calls, no telemetry.

```bash
npm install -g @ozperium/quota
quota
```

```
  Claude Code   ████████████░░  3h 12m of 5h    reset in 2h 48m
  Codex         ███░░░░░░░░░░░  3 of 40 reqs    reset in 4h 12m
```

→ [GitHub](https://github.com/Ozperium/quota) · [npm](https://www.npmjs.com/package/@ozperium/quota)

---

## Stoke

A local-first Rust proxy that puts hard budget caps, rate limits, loop detection, and routing in front of AI agents.

```bash
curl -sSf https://stokegate.com/install | sh -s -- --version nightly
```

→ [GitHub](https://github.com/Ozperium/stoke) · [stokegate.com](https://stokegate.com)

---

MIT licensed. Built by [@pawfromoz](https://dev.to/pawfromoz).
