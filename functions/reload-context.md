---
function: reload-context
category: navigation
purpose: Refresh context from catalogs after significant changes
created: 2026-03-19
---

# Function: reload-context

## When to Use

**Invoke when:**
- Files have been created/moved/renamed since wake
- Task blocks have been activated/suspended
- Catalogs have been updated
- Returning to work after a break
- "What's changed?" feeling

**Don't invoke when:**
- Nothing has changed
- Just loaded context moments ago
- Mid-task (use sidebar-query instead)

---

## How It Works

1. **Load all catalogs** (if not already loaded this session)
   ```
   Filesystem:read_multiple_files([
       "{INSTANCE_HOME}/FOUNDATION/catalogs/session-index.md",
       "{INSTANCE_HOME}/FOUNDATION/catalogs/patterns-catalog.md",
       "{INSTANCE_HOME}/FOUNDATION/catalogs/filesystem-catalog.json",
       "{INSTANCE_HOME}/context/active-blocks.json"
   ])
   ```

2. **Identify what changed**
   - Compare current active-blocks vs what's loaded
   - Check session-index for new entries
   - Note any new files in filesystem-catalog

3. **Load updated content**
   - Load new active blocks
   - Update session context if needed
   - Refresh task status

4. **Report what changed**
   ```
   "Context reloaded:
   - 1 new active block: project-x
   - 2 blocks moved to suspended: project-y, project-z
   - Session index updated (3 new entries)
   
   Current focus: [active blocks summary]"
   ```

---

## Parameters

**None** — Reload always checks all catalogs and updates accordingly.

---

## Example

```
User: "Reload context"

AI: [reads functions/reload-context.md]
    [loads all catalogs]
    [identifies changes]
    [loads updated blocks]
    
    "Context reloaded from catalogs.
    
    Changes detected:
    - Active blocks: substrate-framework (new), devrel-applications (active)
    - Suspended: fiverr-gigs (waiting for gift card)
    - Completed today: email-setup, domain-registration
    
    Ready to continue with substrate-framework."
```

---

## Notes

**Token cost:** ~10-15KB typically (catalogs + active blocks)

**When to skip:** If nothing has changed and you're mid-task, don't reload. The overhead isn't worth it.

**Alternative:** For quick checks without full reload, use sidebar-query: "What's in active blocks now?"

---

## Related

- **Pattern:** [catalog-system.md](../patterns/catalog-system.md)
- **Pattern:** [context-management.md](../patterns/context-management.md)
- **Function:** [unload-context.md](unload-context.md)
