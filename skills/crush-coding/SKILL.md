---
name: crush-coding
description: |
  Skill for using Crush to handle complex source code tasks.
  Provides guidance on effective prompting and when to use Crush.
metadata:
  author: alexcabrera
  version: "1.0"
---

# Crush Coding Skill

This skill provides guidance for using Crush effectively for source code tasks.

## When to Use Crush

Crush excels at:

- **Multi-file changes**: Refactoring that spans multiple files
- **Feature implementation**: Adding new functionality across a codebase
- **Debugging**: Finding and fixing issues in code
- **Test creation**: Writing comprehensive test suites
- **Code generation**: Creating new code from specifications

## Effective Prompting

### Structure Your Prompts

1. **Clear objective**: What needs to be accomplished
2. **Scope**: Which files or directories are involved
3. **Constraints**: What should NOT be changed
4. **Success criteria**: How to verify completion

### Good Prompt Examples

**Creating a new project:**
```
Create a basic single page application in the my-app directory.
Use vanilla HTML, CSS, and JavaScript.
Include an index.html with a simple navigation header, a main content area, and a footer.
```

**Modifying existing code:**
```
Add comprehensive error handling to the database connection logic in internal/db/.
Wrap all database calls with proper error context.
Do NOT modify the connection pool configuration.
```

**Debugging:**
```
Debug and fix the memory leak in the WebSocket handler.
The issue is in internal/ws/handler.go - connections are not being properly cleaned up on disconnect.
```

### Bad Prompt Examples

- "Fix the errors" (too vague)
- "Make it faster" (no specific scope)
- "Refactor everything" (too broad)

## Scope Guidelines

| Scope | How to Specify |
|-------|----------------|
| New project | "in the my-app directory" |
| Single file | "in api/handlers/user.go" |
| Directory | "in the internal/auth/ directory" |
| Multiple files | "in user.go, auth.go, and session.go" |
| Project-wide | "across the entire codebase" (use sparingly) |

## Constraint Specification

Always specify what should NOT be modified:

- "Do not modify any test files"
- "Preserve the existing public API"
- "Keep backwards compatibility with v1 endpoints"
- "Do not change the database schema"

## Best Practices

1. **Be specific**: Vague prompts lead to vague results
2. **Set clear boundaries**: Specify what NOT to change
3. **Request verification**: Ask to run tests after changes
4. **Iterate incrementally**: Large tasks should be broken into phases
5. **Provide context**: Include relevant background for complex tasks
