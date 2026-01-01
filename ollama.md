# OLLAMA

## Basic Commands

- `ollama run <model>` - run a model interactively.
- `ollama pull <model>` - download a model.
- `ollama list` - list downloaded models.
- `ollama rm <model>` - remove a model.
- `ollama show <model>` - show model info.
- `ollama cp <source> <dest>` - copy a model.
- `ollama ps` - list running models.
- `ollama stop <model>` - stop a running model.

## Running Models

Run model interactively:

    ollama run llama3.2

Run with a prompt:

    ollama run llama3.2 "Explain quantum computing"

Multiline input (end with """):

    ollama run llama3.2 """
    Write a haiku about
    programming
    """

## Slash Commands

Use these commands during an interactive session:

- `/set parameter <value>` - set parameter (e.g., temperature).
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
- `/?` or `/help` - show help.

## Configuration

Run with a system prompt:

    ollama run llama3.2 --system "You are a helpful coding assistant"

### Environment Variables

- `OLLAMA_HOST` - server address (default: 127.0.0.1:11434).
- `OLLAMA_MODELS` - directory for storing models.
- `OLLAMA_KEEP_ALIVE` - how long models stay loaded (default: 5m).
- `OLLAMA_NUM_PARALLEL` - number of parallel requests.
- `OLLAMA_MAX_LOADED_MODELS` - max models loaded concurrently.
