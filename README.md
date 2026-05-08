# MiniMax Provider Plugin

Adds [MiniMax](https://www.minimax.io/) (M2.7) as an LLM provider in Agent Zero.

## Models

| Model | Context | Speed | Price (in/out per MTok) |
|-------|---------|-------|------------------------|
| MiniMax M2.7 | 205K | 45 tok/s | $0.30 / $1.20 |
| MiniMax M2.7 Highspeed | 205K | ~100 tok/s | $0.30 / $1.20 |

## Setup

1. Get an API key from [platform.minimax.io](https://platform.minimax.io/)
2. Add `MINIMAX_API_KEY` to your Agent Zero secrets
3. Select `minimax` as the provider and choose `MiniMax-M2.7` as the model in Agent Zero settings

## Architecture

- OpenAI-compatible API at `https://api.minimax.io/v1`
- Provider ID `minimax` auto-maps to `MINIMAX_API_KEY` environment variable
- Registered via `conf/model_providers.yaml` (config-only plugin, no Python code)

## Benchmarks (Artificial Analysis, May 2026)

- AA Intelligence Index: 50 (#7/85)
- GPQA Diamond: 87%
- tau2-Bench (agentic): 85%
- Non-Hallucination Rate: 66%
- Cache pricing: $0.06/MTok (-80%)
