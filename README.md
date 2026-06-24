# Free Claude-Code

A guide to running local LLMs (like Gemma 4) and using Claude Code on your machine.

## 🚀 Getting Started

### 1. Install Ollama
Ollama is the easiest way to run open-source LLMs locally.

#### **Ubuntu**
Run the following command in your terminal:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

#### **macOS**
1. Download the Ollama app from [ollama.com/download](https://ollama.com/download).
2. Unzip the file and move Ollama to your `Applications` folder.
3. Launch the app to start the Ollama server.

---

### 2. Install Claude Code
Claude Code is the official CLI for Claude, providing an interactive agent experience in your terminal.

**Prerequisites:** Node.js 18+

Install the CLI globally via npm:
```bash
npm install -g @anthropic-ai/claude-code
```

After installation, initialize it by running:
```bash
claude
```

---

### 3. Running Gemma 4 with Ollama
To use the Gemma 4 model locally, follow these steps:

1. Ensure the Ollama server is running.
2. Pull and run the Gemma 4 model:
```bash
ollama launch claude --model gemma4:31b-cloud
```

---

### 🛠 Connecting Claude Code to Local Models
Claude Code is natively designed to work with Anthropic's Claude models. To use it with a local provider like Ollama, you typically need an API proxy that translates the Anthropic API format to the Ollama format.

**General Setup:**
1. **Start Ollama:** Keep the Ollama server running in the background.
2. **Setup Proxy:** Use a tool like `lite-llm` or a similar proxy to map `/v1/messages` (Anthropic) to the local Ollama endpoint.
3. **Configure Environment:** Set your API base URL to point to your local proxy:
   ```bash
   export ANTHROPIC_BASE_URL="http://localhost:PORT/v1"
   ```
4. **Launch Claude Code:**
   ```bash
   claude
   ```

## 📚 Resources
- [Ollama Official Site](https://ollama.com)
- [Claude Code Documentation](https://claude.ai/code)
- [Gemma 4 Model Page](https://ollama.com/library/gemma4)
