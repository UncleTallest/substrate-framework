# Substrate Functions

Functions are reusable behavioral patterns that AI instances can invoke during sessions. They're like shell aliases or keyboard shortcuts — documented shortcuts for common operations.

---

## What Are Functions?

Functions are **documented behaviors** that AI instances can execute:

- **reload-context** — Refresh context from catalogs after major changes
- **unload-context** — Explicitly release large files from active memory
- **sidebar-query** — Ask a quick question without losing current context
- **timestamp-check** — Verify current date/time for time-sensitive operations

**Not actual code** (though they might invoke scripts). They're behavioral templates.

---

## How Functions Work

### Definition Structure

Each function is documented in a `.md` file:

```markdown
---
function: function-name
category: [navigation | session-management | communication]
purpose: One-line description
created: YYYY-MM-DD
---

# Function: function-name

## When to Use
[Recognition criteria]

## How It Works
[Step-by-step process]

## Example
[Concrete usage example]

## Related
[Links to patterns, other functions]
```

### Usage Pattern

AI instance reads function documentation, then executes the described behavior:

```
User: "Load the latest context"

AI: [reads functions/reload-context.md]
    [executes steps: check catalogs, identify changed files, load updated versions]
    
    "Reloaded context from:
    - session-index.md (updated today)
    - active-blocks.json (2 new blocks added)
    Current focus loaded."
```

---

## Available Functions

### Navigation Functions

**[reload-context.md](reload-context.md)**  
Refresh context from catalogs after significant changes.

**[unload-context.md](unload-context.md)**  
Explicitly release large files from active memory.

### Communication Functions

**[sidebar-query.md](sidebar-query.md)**  
Ask a quick question without losing current working context.

### Session Management Functions

**[timestamp-check.md](timestamp-check.md)**  
Verify current date/time for time-sensitive operations.

---

## Creating New Functions

### When to Create a Function

**Create a function when:**
- You find yourself repeating the same multi-step process
- The operation is complex enough to need documentation
- Multiple AI sessions would benefit from this behavior
- The pattern is generalizable

**Don't create a function when:**
- It's a one-time operation
- The pattern is trivial (one step)
- It's too specific to your unique context

### Function Template

```markdown
---
function: your-function-name
category: [navigation | session-management | communication | custom]
purpose: Brief description
created: YYYY-MM-DD
---

# Function: your-function-name

## When to Use

Describe the recognition criteria — when should this function be invoked?

## How It Works

Step-by-step process:

1. First step
2. Second step
3. Third step

## Parameters (if applicable)

- `param1`: Description
- `param2`: Description

## Example

```
User: "Invoke your-function-name"

AI: [executes function steps]
    
    Result: [what happens]
```

## Notes

Important details, gotchas, or context.

## Related

- **Patterns:** [related-pattern.md](../patterns/related-pattern.md)
- **Functions:** [related-function.md](related-function.md)
```

---

## Functions vs Hooks

**Functions** are invoked explicitly:
- User says "reload context"
- AI reads function documentation
- AI executes steps

**Hooks** (future feature) are triggered automatically:
- Session ends → auto-trigger end-of-turn summary
- Token budget hits 80% → auto-warn
- New files created → auto-update filesystem catalog

Substrate currently focuses on **functions** (explicit invocation). Hooks require more infrastructure.

---

## Integration with Catalogs

Functions are cataloged in `FOUNDATION/catalogs/functions-catalog.md`:

```markdown
# Functions Catalog

## Navigation Functions
- `reload-context` — Refresh context from catalogs (functions/reload-context.md)
- `unload-context` — Release large files from memory (functions/unload-context.md)

## Communication Functions
- `sidebar-query` — Quick question without context loss (functions/sidebar-query.md)

## Session Management Functions
- `timestamp-check` — Verify current date/time (functions/timestamp-check.md)
```

AI instances load this catalog at wake to know what functions exist.

---

## Implementation Notes

**For neurodivergent users:**
- Functions reduce "how do I do X again?" overhead
- Documented patterns beat remembering sequences
- Consistent behavior across sessions

**For AI instances:**
- Functions provide behavioral templates
- Reduces reinventing common patterns
- Clear execution steps (no guessing)

---

## Future: Hooks System

**Hooks** would enable automatic triggering:

```python
# Example hook configuration (future feature)
{
  "hooks": {
    "session-end": {
      "trigger": "session_ending",
      "action": "create_end_of_turn_summary",
      "enabled": true
    },
    "token-warning": {
      "trigger": "context_budget > 80%",
      "action": "warn_user_about_token_usage",
      "enabled": true
    }
  }
}
```

This would require more infrastructure (event system, triggers, etc.). Current Substrate focuses on explicit functions.

---

## Contributing Functions

See [CONTRIBUTING.md](../CONTRIBUTING.md) for how to submit new functions.

**Good function contributions:**
- Solve a real repeated problem
- Well-documented with examples
- Generalizable across different users
- Clear "when to use" criteria

---

*Functions are shortcuts for common operations. Use them to reduce repetitive cognitive work.*
