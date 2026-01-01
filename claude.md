# Claude Cheatsheet

<!-- TOC -->
- [CLI Basics](#cli-basics)
  - [Start Session](#start-session)
  - [Model Selection](#model-selection)
  - [System Prompts](#system-prompts)
  - [Tool Control](#tool-control)
  - [Output Format](#output-format)
  - [Permissions](#permissions)
  - [Other Flags](#other-flags)
  - [Environment Variables](#environment-variables)
- [Slash Commands](#slash-commands)
- [Keyboard Shortcuts](#keyboard-shortcuts)
- [File References](#file-references)
  - [Examples](#examples)
- [Shell Commands](#shell-commands)
- [Memory (CLAUDE.md)](#memory-claudemd)
  - [File Locations](#file-locations)
  - [Commands](#commands)
  - [What to Store](#what-to-store)
- [Custom Slash Commands](#custom-slash-commands)
  - [Example: /deploy command](#example-deploy-command)
- [Model Aliases](#model-aliases)
- [Agent Usage](#agent-usage)
  - [Creating Agents](#creating-agents)
  - [Using Agents](#using-agents)
- [Skill Usage](#skill-usage)
  - [Creating Skills](#creating-skills)
  - [Skill Structure](#skill-structure)
- [Prompting Tips](#prompting-tips)
  - [Be Specific](#be-specific)
  - [Thinking Modes](#thinking-modes)
  - [Planning & Structure](#planning-structure)
  - [Output Control](#output-control)
  - [Effective Patterns](#effective-patterns)
  - [For Code Tasks](#for-code-tasks)
  - [Avoid](#avoid)
<!-- /TOC -->

## CLI Basics

### Start Session
```
claude                    # interactive mode
claude "prompt"           # one-shot query
claude -c                 # continue last conversation
claude -r                 # resume conversation picker
claude -p                 # print mode (no interactive)
claude update             # update to latest version
```

### Model Selection
```
--model <model>           # set model (opus, sonnet, haiku, or full name)
--fallback-model <model>  # fallback when primary model overloaded
```

### System Prompts
```
--system-prompt "text"         # replace default system prompt
--append-system-prompt "text"  # append to default prompt
--system-prompt-file <path>    # load system prompt from file
```

### Tool Control
```
--tools "Read,Edit,Bash"       # specify available tools
--allowedTools "Bash(git:*)"   # tools that skip permission prompts
--disallowedTools "Edit"       # tools removed from context
```

### Output Format
```
--output-format text           # plain text output (default)
--output-format json           # JSON output
--output-format stream-json    # streaming JSON
```

### Permissions
```
--permission-mode plan              # start in plan mode
--dangerously-skip-permissions      # skip all permission prompts
```

### Other Flags
```
--add-dir <path>          # add additional working directories
--max-turns <n>           # limit agentic turns in headless mode
--verbose                 # enable verbose logging
--debug                   # enable debug mode
```

### Environment Variables
```
ANTHROPIC_API_KEY         # API key
CLAUDE_CODE_USE_BEDROCK=1 # use AWS Bedrock
CLAUDE_CODE_USE_VERTEX=1  # use Google Vertex
```

## Slash Commands

### Navigation
- `/help` - show help
- `/exit` - exit the REPL
- `/status` - show version, model, account info
- `/resume [session]` - resume conversation by ID/name
- `/clear` - clear conversation history

### Configuration
- `/config` - open settings interface
- `/model [name]` - select or change model
- `/permissions` - view/update permissions
- `/memory` - edit CLAUDE.md memory files
- `/vim` - toggle vim keybindings

### Context Management
- `/compact [focus]` - compact conversation with optional focus
- `/context` - visualize context usage
- `/cost` - show token usage statistics
- `/todos` - list current TODO items

### Tools & Integrations
- `/mcp` - manage MCP server connections
- `/hooks` - manage hook configurations
- `/ide` - manage IDE integrations
- `/agents` - manage custom subagents

### Code & Git
- `/review` - request code review
- `/pr-comments` - view PR comments
- `/init` - initialize project with CLAUDE.md
- `/doctor` - check installation health

## Keyboard Shortcuts
- `Ctrl+C` - cancel current operation
- `Ctrl+D` - exit session
- `Ctrl+L` - clear screen
- `Ctrl+O` - toggle verbose output (see thinking)
- `Ctrl+R` - reverse search history
- `Ctrl+V` / `Alt+V` - paste image from clipboard
- `Escape` - interrupt response
- `Esc Esc` - rewind code/conversation
- `Tab` - autocomplete file paths
- `Shift+Tab` / `Alt+M` - toggle permission modes
- `Alt+P` / `Option+P` - switch model
- `Up/Down` - navigate history

## File References
```
@filename              # reference file (tab-completable)
@path/to/file.js       # reference with path
@folder/               # reference entire directory
@screenshot.png        # reference image
```

### Examples
```
@src/main.ts explain this file
@package.json what deps are outdated?
review @src/utils/ for security issues
compare @old.js and @new.js
```

## Shell Commands
```
!command               # run shell command
$command               # same as above
```

Or just ask: "run npm install" / "build the project"

## Memory (CLAUDE.md)

### File Locations
```
./CLAUDE.md              # project-specific (in repo)
./CLAUDE.local.md        # project-specific (gitignored)
~/.claude/CLAUDE.md      # global (all projects)
```

### Commands
- `/init` - create CLAUDE.md in current project
- `/memory` - open CLAUDE.md for editing
- `#` prefix - add note to memory inline (e.g. `# always use tabs`)

### What to Store
- Project conventions (formatting, naming)
- Tech stack / framework versions
- Common commands (build, test, deploy)
- File structure notes
- Personal preferences

### Input Tips
- Use `\` at end of line for multiline input
- Or use `Shift+Enter` for multiline

## Custom Slash Commands

Create `.claude/commands/` in project or `~/.claude/commands/` globally.

### Example: /deploy command
File: `.claude/commands/deploy.md`
```markdown
Deploy the application to $ARGUMENTS environment.

Steps:
1. Run tests first
2. Build for production
3. Deploy using: ./scripts/deploy.sh $ARGUMENTS
4. Verify deployment succeeded
```

Usage: `/deploy staging` or `/deploy production`

Variables: `$ARGUMENTS` for user input after command

## Model Aliases

Use these as shorthand with `--model` or `/model`:
```
sonnet              # Claude Sonnet (daily coding)
opus                # Claude Opus (complex reasoning)
haiku               # Claude Haiku (fast, simple tasks)
opusplan            # Opus for planning, Sonnet for execution
sonnet[1m]          # Sonnet with 1M token context
```

## Agent Usage

### Creating Agents

Create agent files in `.claude/agents/` (project) or `~/.claude/agents/` (personal):

```markdown
# .claude/agents/reviewer.md
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
```

### Using Agents

Agents are auto-delegated based on context, or invoke explicitly:
```
use the reviewer agent to check my auth module
```

## Skill Usage

### Creating Skills

Create skills in `.claude/skills/` (project) or `~/.claude/skills/` (personal):

```markdown
# .claude/skills/my-skill/SKILL.md
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
```

### Skill Structure
- `SKILL.md` - main skill file (required)
- Additional `.md` files for detailed docs
- `scripts/` folder for utility scripts

## Prompting Tips

### Be Specific
- Provide context upfront
- Use examples for complex tasks
- Break down multi-step requests

### Thinking Modes
```
think                  # extended thinking for complex problems
think harder           # deeper reasoning
ultrathink             # maximum reasoning depth
```

Example: `ultrathink: design a caching layer for this API`

Note: Only works when MAX_THINKING_TOKENS not already set. Toggle thinking globally via `/config`.

### Planning & Structure
```
plan                   # structured step-by-step approach
multi staged plan      # break into phases with checkpoints
/plan                  # enter plan mode before implementation
```

Mode keywords: `plan` / `planning` trigger plan mode context.

### Output Control
```
be concise / be brief  # shorter responses
be thorough            # detailed responses
no yapping             # skip preamble, just answer
```

### Effective Patterns
- "Think step by step" - improves reasoning
- "Here's an example: [X] -> [Y]" - few-shot learning
- "Output only JSON/code" - constrain format
- "Before answering, consider..." - self-reflection

### For Code Tasks
- Share relevant files/context
- Specify language/framework versions
- Mention constraints (no external deps, etc)
- Ask for tests alongside implementation

### Avoid
- Vague requests ("make it better")
- Too many tasks at once
- Assuming context from previous sessions
