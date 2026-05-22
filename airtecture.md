# Architecture — Simple LLM Wrapper

## Overview

Simple LLM Wrapper is a lightweight, un-opinionated abstraction layer that provides a unified interface for interacting with multiple Large Language Model APIs. It allows consumers to swap between providers without changing application logic.

## Core Components

### LLMWrapper

The central class that exposes the public API. Responsible for:

- Accepting provider and model configuration
- Routing requests to the appropriate provider backend
- Exposing `generate()` for single completions and `stream()` for streamed responses

### Provider Backends

Each supported provider has a dedicated backend adapter:

| Provider       | Models                                      | Transport       |
|----------------|---------------------------------------------|-----------------|
| OpenAI         | gpt-4o, gpt-4-turbo, gpt-3.5-turbo         | REST API        |
| Anthropic      | claude-3-opus, claude-3-sonnet, claude-3-haiku | REST API     |
| Google Gemini  | gemini-1.5-pro, gemini-1.5-flash            | REST API        |
| Local Models   | Any (Ollama / Llama.cpp)                    | Local HTTP      |

### Configuration Layer

- Reads API keys from environment variables or accepts them at initialization time.
- Supports `.env` files for local development.

### Conversation Memory (Optional)

- Manages message history for multi-turn chat interactions.
- Opt-in; the wrapper remains stateless by default.

## Data Flow

```
User Code
   │
   ▼
LLMWrapper (unified interface)
   │
   ├─► Provider Adapter (OpenAI / Anthropic / Gemini / Local)
   │        │
   │        ▼
   │    Provider API
   │        │
   │        ▼
   └── Response / Stream returned to caller
```

## Design Principles

- Minimal dependencies — keep the footprint small.
- Provider-agnostic public API — switching providers requires only a config change.
- Stateless by default — conversation memory is opt-in.
- Environment-driven configuration — secrets stay out of code.

## Installation & Runtimes

Available as both a Python package (`pip install simple-llm-wrapper`) and a Node.js package (`npm install simple-llm-wrapper`), targeting polyglot teams.

## License

MIT
