# Simple LLM Wrapper

A lightweight, un-opinionated wrapper for interacting with various Large Language Model (LLM) APIs (like OpenAI, Anthropic, Gemini, etc.) through a single, unified interface.

## Features

- 🔌 **Unified Interface**: Swap between different model providers without changing your core application logic.
- ⚙️ **Easy Configuration**: Set up via environment variables or direct initialization.
- 💬 **Conversation Memory**: (Optional) Easily manage message history for chat-based interactions.
- 🚀 **Lightweight**: Minimal dependencies, keeping your project bloat-free.

## Installation

*(Note: Replace with your actual package manager command once published)*

```bash
pip install simple-llm-wrapper
# or
npm install simple-llm-wrapper
```

## Configuration

Set your API keys in your environment variables. You can use a `.env` file for local development:

```env
OPENAI_API_KEY="your-openai-api-key"
ANTHROPIC_API_KEY="your-anthropic-api-key"
GEMINI_API_KEY="your-gemini-api-key"
```

## Quick Start

Here is a basic example of how to use the wrapper:

### Python Example

```python
from llm_wrapper import LLMWrapper

# Initialize the wrapper (automatically picks up API keys from env)
llm = LLMWrapper(provider="openai", model="gpt-4o")

# Simple completion
response = llm.generate("Explain quantum computing in one sentence.")
print(response)

# Switching providers is as simple as changing the initialization
anthropic_llm = LLMWrapper(provider="anthropic", model="claude-3-opus-20240229")
response = anthropic_llm.generate("Explain quantum computing in one sentence.")
```

### Streaming Responses

```python
for chunk in llm.stream("Write a short poem about coding."):
    print(chunk, end="", flush=True)
```

## Supported Providers

Currently supported model providers include:
- **OpenAI** (`gpt-4o`, `gpt-4-turbo`, `gpt-3.5-turbo`)
- **Anthropic** (`claude-3-opus`, `claude-3-sonnet`, `claude-3-haiku`)
- **Google Gemini** (`gemini-1.5-pro`, `gemini-1.5-flash`)
- **Local Models** (via Ollama or Llama.cpp)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

Distributed under the MIT License. See `LICENSE` for more information.
