---
pattern: Context Management
category: Session Management
purpose: Managing token budget and context clarity
created: 2026-03-19
---

# Pattern: Context Management

**Recognition criteria:** Token budget becoming a constraint; loaded files no longer needed for current task; switching between unrelated work areas.

---

## The Problem

Context window space is finite and shared. Every file loaded at wake or during work occupies tokens that could be used for thinking, generating, or reading new material. Loaded context also has a secondary effect: old data bleeds into new decisions, causing subtle errors and polluted reasoning.

For neurodivergent users with discontinuous workflows, managing what's loaded is especially critical — every reload costs executive function and time.

---

## Two Approaches

### Approach A: Monolithic Active-Context (Simple)

**Best for:**
- Single-task focus
- Short sessions (< 1 week continuous work)
- Minimal context-switching
- Getting started quickly

**Structure:**
```
{INSTANCE_HOME}/context/
└── active-context.md    # One file, all current work
```

**File format:**
```markdown
# Active Context

## Current Focus
What I'm working on right now.

## Next Actions
1. First thing to do
2. Second thing
3. Third thing

## Notes
- Important context
- Decisions made
- Things to remember
```

**Pros:**
- Simple: One file to load/update
- Fast to set up
- Easy to understand

**Cons:**
- Grows over time (becomes unwieldy after ~2 months)
- Mixes multiple concerns in one file
- Hard to suspend one task while keeping another active
- "What was I working on?" requires reading entire file

**When to use:** Starting out, single-project focus, short timelines.

---

### Approach B: Task-Based Context Blocks (Modular)

**Best for:**
- Multi-project work
- Long timelines (> 1 week)
- Frequent context-switching
- Need to suspend/resume tasks independently

**Structure:**
```
{INSTANCE_HOME}/context/
├── active-blocks.json          # Lightweight index
└── blocks/                      # Individual task files
    ├── project-a.md
    ├── project-b.md
    └── project-c-suspended.md
```

**Active-blocks.json format:**
```json
{
  "version": "v1.0.0",
  "last_updated": "2026-04-02T18:00:00Z",
  
  "active": [
    {
      "id": "project-a-2026-04-02",
      "path": "blocks/project-a.md",
      "priority": 1,
      "status": "active",
      "quick_summary": "What this task is about"
    }
  ],
  
  "suspended": [
    {
      "id": "project-c-2026-03-20",
      "path": "blocks/project-c-suspended.md",
      "status": "suspended",
      "reason": "Waiting for external dependency",
      "quick_summary": "Paused work"
    }
  ]
}
```

**Block file format (template in examples/):**
```markdown
# Task Block: [Task Name]

**ID:** task-id-YYYY-MM-DD
**Status:** [planning|active|testing|blocked|complete]
**Priority:** [high|medium|low]

## Quick Context (2-3 sentences)
What this is, why it matters, where it's at.

## Objective
Clear goal statement.

## Current State
- ✓ What's done
- ⏳ What's in progress
- ⏸️ What's blocked
- ⏹️ What's pending

## Next Actions
1. First thing
2. Second thing

## Key Files
- /path/to/file - Description

## Notes
Important context, decisions made, gotchas discovered.
```

**Pros:**
- Token efficient: Load only active tasks (~2-3 files)
- Clear task lifecycle: active → suspended → complete
- Easy context switching: Suspend one block, activate another
- Scalable: Doesn't grow unbounded

**Cons:**
- More initial setup
- Need to maintain active-blocks.json
- Slightly more complex

**When to use:** Multiple projects, long timelines, frequent switching.

---

## Comparison

| Factor | Monolithic | Task Blocks |
|--------|-----------|-------------|
| Setup time | 5 min | 15 min |
| Tokens at wake | All context (~10-30KB) | Active blocks only (~6-9KB) |
| Task switching | Edit one file | Update JSON + switch files |
| Scalability | Poor (grows forever) | Good (bounded by active tasks) |
| Grep-ability | One file to search | Many files, need index |
| Best for | Single focus | Multiple projects |

---

## Migration Path

**Starting simple → Growing complex:**

1. **Week 1-4:** Use active-context.md
2. **Week 4-8:** When file hits ~500 lines, consider task blocks
3. **Week 8+:** Implement task blocks as needed

**Don't prematurely optimize:** If active-context.md works, keep using it. Switch to task blocks when you feel the pain of monolithic context.

---

## Loading Strategy (Both Approaches)

### Load Minimally at Wake

**What to load (always):**
- Session metadata (what happened last time)
- Catalogs (where things are)
- Either active-context.md OR active-blocks.json

**What NOT to load at wake:**
- Historical files (old sessions, completed work)
- Reference documentation (load on-demand)
- Large corpus files (philosophy, background)

**Why:** Start with a map, not the full territory. Load details when needed.

### Unload When Done

When a task requiring deep files is complete, explicitly note:

```
"Unloading [specific context] from active memory.
Location preserved in [catalog] for reload if needed."
```

Then stop referencing that content.

### Reload Surgically

When you need something again, load only the specific file:

```
# Wrong — loads everything
Filesystem:read_multiple_files([all_related_files])

# Right — loads exactly what's needed
Filesystem:read_text_file("{INSTANCE_HOME}/path/to/specific-file.md")
```

---

## Implementation Notes

**For neurodivergent users:**
- Monolithic active-context works until it doesn't (you'll feel it)
- Task blocks mirror how many neurodivergent brains work (discrete focus areas)
- Both approaches reduce "where was I?" overhead

**Token efficiency:**
- Monolithic: Load everything, use what you need
- Task blocks: Load only what's active, ignore the rest

**Choose based on:**
- Your natural work patterns
- How often you context-switch
- How long you work on single projects

---

## Related Patterns

- `catalog-system.md` — How to find files without loading everything
- `end-of-turn-summary-protocol.md` — Capturing work before context clears

---

*Start simple. Add structure when simplicity hurts.*
