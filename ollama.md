# OLLAMA

## Quick Start

    ollama pull llama3.2 && ollama run llama3.2

## Basic Commands

- `ollama serve` - start the ollama server.
- `ollama run <model>` - run a model interactively.
- `ollama pull <model>` - download a model.
- `ollama push <model>` - publish model to registry.
- `ollama create <name> -f <Modelfile>` - create custom model.
- `ollama list` - list downloaded models.
- `ollama rm <model>` - remove a model.
- `ollama show <model>` - show model info.
- `ollama cp <source> <dest>` - copy a model.
- `ollama ps` - list running models.
- `ollama stop <model>` - stop a running model.

### Model Tags

Models use `name:tag` format for variants:

    ollama pull llama3.2:70b      # specific size
    ollama pull llama3.2:latest   # latest version
    ollama pull codellama:7b-instruct

## Running Models

Run model interactively:

    ollama run llama3.2

Run with a prompt:

    ollama run llama3.2 "Explain quantum computing"

Multiline input:

    ollama run llama3.2 """Write a haiku about programming"""

Run with a system prompt:

    ollama run llama3.2 --system "You are a helpful coding assistant"

Examples for show/cp/stop:

    ollama show llama3.2 --modelfile   # show modelfile
    ollama cp llama3.2 my-llama        # duplicate model
    ollama stop llama3.2               # unload from memory

## Interactive Session

Slash commands during interactive mode:

- `/set parameter temperature 0.8` - set temperature.
- `/set parameter top_p 0.9` - set top_p.
- `/set system <message>` - set system message.
- `/show info` - show model info.
- `/show license` - show model license.
- `/show modelfile` - show Modelfile.
- `/show parameters` - show model parameters.
- `/show system` - show system message.
- `/load <model>` - load a different model.
- `/save <model>` - save session to a new model.
- `/clear` - clear session context.
- `/bye` - exit the session.
- `/?` - show help.

## Modelfile

Create custom models with a Modelfile:

    FROM llama3.2
    PARAMETER temperature 0.7
    PARAMETER top_p 0.9
    SYSTEM "You are a senior software engineer."
    TEMPLATE "{{ .System }}\n\nUser: {{ .Prompt }}\nAssistant:"

Build and run:

    ollama create mymodel -f Modelfile
    ollama run mymodel

### Modelfile Directives

- `FROM <model>` - base model (required).
- `PARAMETER <name> <value>` - set parameters.
- `SYSTEM <message>` - system prompt.
- `TEMPLATE <template>` - prompt template (Go template syntax).
- `ADAPTER <path>` - LoRA adapter path.
- `LICENSE <text>` - license info.
- `MESSAGE <role> <content>` - conversation history.

## API

Default endpoint: `http://localhost:11434`

Generate completion:

    curl http://localhost:11434/api/generate -d '{
      "model": "llama3.2",
      "prompt": "Why is the sky blue?",
      "stream": false
    }'

Chat completion:

    curl http://localhost:11434/api/chat -d '{
      "model": "llama3.2",
      "messages": [{"role": "user", "content": "Hello"}],
      "stream": false
    }'

List models:

    curl http://localhost:11434/api/tags

## Configuration

### Environment Variables

- `OLLAMA_HOST` - server address (default: `127.0.0.1:11434`).
- `OLLAMA_MODELS` - directory for storing models.
- `OLLAMA_KEEP_ALIVE` - model stay loaded duration (`5m`, `10s`, `-1` forever, default: `5m`).
- `OLLAMA_NUM_PARALLEL` - number of parallel requests.
- `OLLAMA_MAX_LOADED_MODELS` - max models loaded concurrently (default: `1`).
- `OLLAMA_DEBUG` - enable debug logging (`1` to enable).
- `OLLAMA_ORIGINS` - allowed CORS origins (comma-separated).
