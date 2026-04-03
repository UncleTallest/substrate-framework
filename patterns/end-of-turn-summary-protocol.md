---
protocol: End-of-Turn Summary
purpose: Prevent data loss at session boundaries
category: Session Management
created: 2026-03-20
---

# End-of-Turn Summary Protocol

**Purpose**: Capture critical session work before context loss, session end, or tier limitations.

**Why This Matters**:
- Pro tier: Less likely to hit limits, but sessions still end
- Free tier: Context loss between sessions is common
- Token limits: Work can be lost if limits hit unexpectedly
- Session crashes: Browser issues, network problems, etc.

---

## When To Trigger

**Automatic triggers**:
- [ ] Completed major architecture work
- [ ] Created/moved multiple files
- [ ] Made significant decisions
- [ ] Approaching 90% of token budget
- [ ] User says "wrap up" or "end session"

**Manual trigger**:
- User says: "Create end-of-turn summary"
- User says: "Summarize what we did today"

---

## Summary Template

### SESSION SNAPSHOT: [Date] - [Brief Title]

**Session Type**: [Planning / Building / Decision-Making / Research]
**Duration**: [Approximate hours or "single session"]
**Tier**: [Pro / Free]
**Token Budget Used**: [Approximate %]

---

### WORK COMPLETED

**Files Created**:
- [Full path] - [Purpose]
- [Full path] - [Purpose]

**Files Modified**:
- [Full path] - [What changed]
- [Full path] - [What changed]

**Files Moved/Reorganized**:
- [Old path] → [New path] - [Why]

**Directories Created**:
- [Full path] - [Purpose]

---

### KEY DECISIONS MADE

**Decision**: [Brief statement]
- Context: [Why this decision]
- Impact: [What this affects]
- Documented: [Where to find details]

---

### CRITICAL INFORMATION TO PRESERVE

**Pending Actions**:
- [ ] [Action item] - [Why/when]
- [ ] [Action item] - [Why/when]

**Constraints Discovered**:
- [Constraint] - [How it affects work]

**User Context Captured**:
- [Important fact about user's situation]

---

### NEXT SESSION PRIORITIES

**Immediate** (Do first):
1. [Priority task]
2. [Priority task]

**Soon** (Within week):
- [Task]
- [Task]

**Later** (When ready):
- [Task]

---

### HANDOFF INSTRUCTIONS

**To resume this work**:
1. Read: [Key file path]
2. Check: [Status/state to verify]
3. Continue: [Next concrete action]

**If context is lost**:
- This summary saved at: [Path]
- Related work: [Where to find related files]

---

### SESSION METADATA

**Related Sessions**: [Links to previous sessions if applicable]
**Task Blocks Updated**: [Which blocks touched]
**Domain**: [Which domain this work belongs to]

---

## Where To Save Summary

**Primary location**: 
```
{INSTANCE_HOME}/session-metadata/YYYY-MM-DD-summary-[brief-title].md
```

**Session index update**:
```
{INSTANCE_HOME}/FOUNDATION/catalogs/session-index.md
```

---

## Protocol Integration

**Add to wake sequence**:
- Check for end-of-turn summaries in session-metadata/
- If found, read before proceeding with new work

**For active-blocks systems**:
- Consider creating "session-summary" block type
- Auto-trigger when major milestones reached

**For Balance Manager domains**:
- Monitor for end-of-turn trigger conditions
- Remind user to create summary before session end
- Verify critical work is preserved

---

*This protocol ensures no work is lost, even across tier changes, session limits, or unexpected interruptions.*
