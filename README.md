# ayo-plugins-crush

Crush coding agent plugin for [ayo](https://github.com/alexcabrera/ayo).

## Overview

This plugin provides the `@crush` agent which uses [Crush](https://github.com/charmbracelet/crush) for complex source code tasks including:

- Multi-file refactoring
- Feature implementation
- Debugging and fixing issues
- Test creation and modification
- Code generation

## Prerequisites

Crush must be installed and available in your PATH:

```bash
go install github.com/charmbracelet/crush@latest
```

## Installation

```bash
ayo plugins install https://github.com/alexcabrera/ayo-plugins-crush
```

## Usage

### Direct invocation

```bash
ayo @crush "Add comprehensive error handling to the database layer"
```

### Via delegation

Configure in your project's `.ayo.json`:

```json
{
  "delegates": {
    "coding": "@crush"
  }
}
```

Then any coding task will be automatically delegated to `@crush`:

```bash
ayo "Refactor the authentication module to use JWT tokens"
```

## What's included

| Component | Description |
|-----------|-------------|
| `@crush` agent | Coding agent that invokes Crush for source code tasks |
| `crush-coding` skill | Guidance for using Crush effectively |
| `crush` tool | External tool definition mapping to `crush run` |

## Configuration

The agent accepts model configuration via the standard ayo model context. Pass your preferred model and it will be forwarded to Crush.

## License

MIT
