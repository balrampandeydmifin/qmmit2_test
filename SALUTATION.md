# Salutation

Hello and welcome!

This project is a lightweight wrapper for interacting with various Large Language Model (LLM) APIs through a single unified interface.

## What it offers

- A unified interface for OpenAI, Anthropic, Google Gemini, and local model backends.
- Simple configuration via environment variables or direct initialization.
- Optional conversation memory for chat-style workflows.
- Lightweight design with minimal dependencies.

---

## Quick Start for Developers

Follow these steps to get your development environment ready and start coding:

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd <project-folder>
```

### 2. Install Dependencies

For Python:
```bash
pip install -r requirements.txt
```
For Node.js:
```bash
npm install
```

### 3. Configure API Keys

Create a `.env` file in the project root and add your API keys:
```env
OPENAI_API_KEY=your-openai-api-key
ANTHROPIC_API_KEY=your-anthropic-api-key
GEMINI_API_KEY=your-gemini-api-key
```

### 4. Run Example Code

Try out the example in `README.md` or below to verify your setup:
```python
from llm_wrapper import LLMWrapper
llm = LLMWrapper(provider="openai", model="gpt-4o")
print(llm.generate("Hello, world!"))
```

---

## Developer Checklist

- [ ] Clone the repository
- [ ] Install dependencies
- [ ] Set up your `.env` file with API keys
- [ ] Run the example code to verify setup
- [ ] Start building your features in the `llm_wrapper` module

---

## Getting started

Install the package using your preferred package manager:

```bash
pip install simple-llm-wrapper
# or
npm install simple-llm-wrapper
```

Then configure your API keys in environment variables, for example:

```env
OPENAI_API_KEY="your-openai-api-key"
ANTHROPIC_API_KEY="your-anthropic-api-key"
GEMINI_API_KEY="your-gemini-api-key"
```

## Example usage

```python
from llm_wrapper import LLMWrapper

llm = LLMWrapper(provider="openai", model="gpt-4o")
response = llm.generate("Explain quantum computing in one sentence.")
print(response)
```

## Supported providers

- OpenAI (`gpt-4o`, `gpt-4-turbo`, `gpt-3.5-turbo`)
- Anthropic (`claude-3-opus`, `claude-3-sonnet`, `claude-3-haiku`)
- Google Gemini (`gemini-1.5-pro`, `gemini-1.5-flash`)
- Local models via Ollama or Llama.cpp

## Contribution invitation

Your contributions are welcome! Fork the repository, create a feature branch, commit your changes, and open a Pull Request.

Thank you for checking out this project!

---

Happy coding! If you have questions, check the README or open an issue.