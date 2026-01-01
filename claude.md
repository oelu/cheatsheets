# CLAUDE CODE CLI

## Command Arguments

### Basic Commands

- `claude` - start interactive REPL.
- `claude "query"` - start REPL with initial prompt.
- `claude -p "query"` - print response and exit (headless mode).
- `claude -c` - continue most recent conversation.
- `claude -r <session>` - resume session by ID or name.
- `claude update` - update to latest version.

### Model Selection

- `--model <model>` - set model (opus, sonnet, haiku, or full name).
- `--fallback-model <model>` - fallback when primary model overloaded.

### System Prompts

- `--system-prompt "text"` - replace default system prompt.
- `--append-system-prompt "text"` - append to default prompt.
- `--system-prompt-file <path>` - load system prompt from file.

### Tool Control

- `--tools "Read,Edit,Bash"` - specify available tools.
- `--allowedTools "Bash(git:*)"` - tools that skip permission prompts.
- `--disallowedTools "Edit"` - tools removed from context.

### Output Format

- `--output-format text` - plain text output (default).
- `--output-format json` - JSON output.
- `--output-format stream-json` - streaming JSON.

### Permissions

- `--permission-mode plan` - start in plan mode.
- `--dangerously-skip-permissions` - skip all permission prompts.

### Other Flags

- `--add-dir <path>` - add additional working directories.
- `--max-turns <n>` - limit agentic turns in headless mode.
- `--verbose` - enable verbose logging.
- `--debug` - enable debug mode.

## Slash Commands

### Navigation

- `/help` - show help.
- `/exit` - exit the REPL.
- `/status` - show version, model, account info.
- `/resume [session]` - resume conversation by ID/name.
- `/clear` - clear conversation history.

### Configuration

- `/config` - open settings interface.
- `/model [name]` - select or change model.
- `/permissions` - view/update permissions.
- `/memory` - edit CLAUDE.md memory files.

### Context Management

- `/compact [focus]` - compact conversation with optional focus.
- `/context` - visualize context usage.
- `/cost` - show token usage statistics.
- `/todos` - list current TODO items.

### Tools & Integrations

- `/mcp` - manage MCP server connections.
- `/hooks` - manage hook configurations.
- `/ide` - manage IDE integrations.
- `/agents` - manage custom subagents.

### Code & Git

- `/review` - request code review.
- `/pr-comments` - view PR comments.
- `/init` - initialize project with CLAUDE.md.

### Custom Commands

Create project commands:

    mkdir -p .claude/commands
    echo "Your prompt here" > .claude/commands/my-command.md

Use with `/my-command`.

## Prompting Tips

### File References

Use `@` to reference files in prompts:

    Explain @src/utils/auth.js
    Compare @file1.js and @file2.js

### Bash Mode

Use `!` prefix for direct shell commands:

    ! git status
    ! npm test

### Memory Shortcut

Press `#` at start of input to add to CLAUDE.md memory.

### Multiline Input

Use `\` at end of line or Shift+Enter for multiline.

## Special Keywords

### Extended Thinking

- `ultrathink` - enables extended thinking for single request.

Example:

    ultrathink: design a caching layer for this API

Note: Only works when MAX_THINKING_TOKENS not already set. Toggle thinking globally via `/config`.

### Model Aliases

Use these as shorthand with `--model` or `/model`:

- `sonnet` - Claude Sonnet (daily coding).
- `opus` - Claude Opus (complex reasoning).
- `haiku` - Claude Haiku (fast, simple tasks).
- `opusplan` - Opus for planning, Sonnet for execution.
- `sonnet[1m]` - Sonnet with 1M token context.

### Mode Keywords

- `plan` / `planning` - triggers plan mode context.

## Agent Usage

### Creating Agents

Create agent files in `.claude/agents/` (project) or `~/.claude/agents/` (personal):

    mkdir -p .claude/agents

Example agent file `.claude/agents/reviewer.md`:

    ---
    name: reviewer
    description: Code review specialist. Use after writing code.
    tools: Read, Grep, Glob, Bash
    model: sonnet
    ---

    You are a senior code reviewer focusing on quality and security.

    When invoked:
    1. Run git diff to see changes
    2. Review modified files
    3. Provide feedback by priority

### Using Agents

Agents are auto-delegated based on context, or invoke explicitly:

    use the reviewer agent to check my auth module

## Skill Usage

### Creating Skills

Create skills in `.claude/skills/` (project) or `~/.claude/skills/` (personal):

    mkdir -p .claude/skills/my-skill

Example skill file `.claude/skills/my-skill/SKILL.md`:

    ---
    name: my-skill
    description: What this skill does and when to use it.
    allowed-tools: Read, Edit
    ---

    # My Skill

    ## Instructions
    Step-by-step guidance for using this skill.

    ## Examples
    Concrete examples of skill usage.

### Skill Structure

- `SKILL.md` - main skill file (required).
- Additional `.md` files for detailed docs.
- `scripts/` folder for utility scripts.

## Keyboard Shortcuts

- `Ctrl+C` - cancel current input.
- `Ctrl+D` - exit session.
- `Ctrl+L` - clear terminal screen.
- `Ctrl+O` - toggle verbose output (see thinking).
- `Ctrl+R` - reverse search history.
- `Ctrl+V` / `Alt+V` - paste image from clipboard.
- `Shift+Tab` / `Alt+M` - toggle permission modes.
- `Alt+P` / `Option+P` - switch model.
- `Esc Esc` - rewind code/conversation.
