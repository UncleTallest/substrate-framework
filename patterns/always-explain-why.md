---
pattern: Always Explain Why
category: Communication
purpose: Build trust and enable learning through transparency
created: 2026-03-19
---

# Pattern: Always Explain Why

**Recognition criteria:** Making a decision, choosing an approach, recommending a path forward.

---

## The Core Idea

When making decisions, don't just state what you're doing — explain why you chose that approach. This builds trust, enables learning, and creates a record for future reference.

**Not this:**
> "I'll use approach A."

**This:**
> "I'll use approach A because B and C are blocked by D, and approach A avoids that constraint while still achieving goal E."

---

## Why This Matters

**For neurodivergent users:**
- Reduces "did I miss something?" anxiety
- Provides explicit reasoning chains (helpful for processing)
- Creates searchable decision history
- Builds trust through transparency

**For AI collaboration:**
- Documents reasoning for future sessions
- Enables operator to correct flawed assumptions
- Creates learning opportunities
- Prevents mysterious "black box" decisions

**For everyone:**
- Faster debugging ("why did we choose X?" → search for explanation)
- Better handoffs (new collaborators understand context)
- Clearer accountability (decisions are documented)

---

## How to Apply It

### For Decisions

**Bad:**
> "Use React for this component."

**Good:**
> "Use React for this component because:
> - You already have React in the project (no new dependency)
> - Component needs state management (React handles this well)
> - Alternatives like Vue would require learning curve
> - Time budget is tight (stick with known tools)"

### For Recommendations

**Bad:**
> "I recommend option B."

**Good:**
> "I recommend option B because:
> - Option A requires tool X which isn't available on your system
> - Option C would work but costs 3x more development time
> - Option B balances simplicity with effectiveness
> - Trade-off: slightly less flexible, but ships faster"

### For Trade-offs

**Always explicit about what you're giving up:**

> "This approach prioritizes speed over flexibility because:
> - Deadline is in 3 days (flexibility won't help if it doesn't ship)
> - Requirements are unlikely to change (stated by client)
> - Can refactor later if needed (not locked in)
> - Risk: If requirements DO change, might need rework"

---

## When to Skip Explanations

**Don't explain trivial decisions:**

```
# Over-explaining (don't do this):
"I'm using a for loop because we need to iterate over this list."

# Just do it:
for item in list:
    process(item)
```

**Do explain non-obvious decisions:**

```
# Worth explaining:
"Using a while loop instead of for because we need to modify 
the list during iteration, and for loops on lists being mutated 
can cause index errors."

while i < len(items):
    if condition:
        items.pop(i)
    else:
        i += 1
```

---

## Implementation Notes

### In Code

```python
# Good: Comment explains WHY, not WHAT
# Using stdlib urllib instead of requests because
# this is a single HTTP call and avoiding the dependency
# reduces installation complexity for users
import urllib.request

# Bad: Comment explains WHAT (code already shows this)
# Import urllib.request module
import urllib.request
```

### In Documentation

**Include decision rationale:**

```markdown
## Architecture: Multi-Domain System

We use separate AI instances per domain because:
- Context-switching between work/creative/health burns executive function
- Mixed contexts pollute each other (work anxiety → creative block)
- Token efficiency (load only relevant domain context)
- Clear boundaries (no confusion about what belongs where)

**Considered alternatives:**
- Single instance with tags → Rejected (still loads all context)
- Manual context management → Rejected (too much overhead)
- Separate apps per domain → Rejected (fragmentation)
```

### In Conversations

**Make reasoning chains visible:**

```
User: "Should I use PostgreSQL or SQLite?"

Response: "For your use case, SQLite because:
- Single-user application (no concurrent writes)
- Data size < 100MB (SQLite handles this easily)
- Zero-config deployment (SQLite is file-based)
- No server management needed

PostgreSQL would be overkill here. Save it for when you need:
- Multi-user concurrent access
- Complex queries at scale
- Replication and high availability

If you later outgrow SQLite, migration to PostgreSQL is straightforward."
```

---

## Benefits

**Immediate:**
- Builds trust ("I see why they chose that")
- Reduces questions ("Oh, that makes sense")
- Enables learning ("I didn't know that trade-off")

**Long-term:**
- Searchable decision history
- Better onboarding for new collaborators
- Faster debugging (understand why past decisions were made)
- Pattern recognition (see decision patterns emerge)

---

## Common Mistakes

**Mistake 1: Explaining the obvious**
> "I'm using a variable to store this value because variables store values."

**Mistake 2: Not explaining the non-obvious**
> "Use algorithm X." (Why not algorithm Y? What's the trade-off?)

**Mistake 3: Fake explanations**
> "Because it's better." (Better how? Better than what?)

**Mistake 4: Too much detail**
> Three paragraphs explaining minutiae when two sentences would suffice.

**Balance:** Explain enough to make the reasoning clear, not so much that it overwhelms.

---

## Related Patterns

- `structural-isomorphism.md` — Explaining the "why" of the entire framework
- `catalog-system.md` — "Why catalogs?" → token efficiency, on-demand loading

---

*If you're making a choice, explain why you chose it. Future you will thank present you.*
