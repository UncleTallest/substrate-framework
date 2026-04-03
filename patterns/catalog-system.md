---
pattern: Catalog System
category: Navigation
purpose: Efficient file discovery without loading everything
created: 2026-03-19
---

# Pattern: Catalog System

**Recognition criteria:** Need to find a specific file; loading everything to find one thing; uncertainty about what exists.

---

## The Core Idea

Catalogs are indices, not content. They tell you WHERE data lives without carrying the data itself. Load the catalog (small) to find what exists, then load the specific file (exactly what you need) only when you need it.

This is the same principle as a library card catalog versus reading every book to find the one you want.

---

## The Catalog Hierarchy

### General Catalogs (`FOUNDATION/catalogs/`)

| Catalog | What it indexes |
|---|---|
| `session-index.md` | Work history — what prior sessions accomplished |
| `episodic-catalog.json` | High-salience emotional/decisional snapshots |
| `filesystem-catalog.json` | Complete file map — where everything lives |
| `functions-catalog.md` | Available behavioral patterns and functions |
| `patterns-catalog.md` | Discovered architectural patterns (like this one) |
| `decisions-catalog.md` | Key decisions with numbering and descriptions |

### Identity Catalog (`FOUNDATION/identity/`)

| Catalog | What it indexes |
|---|---|
| `identity-catalog.json` | All identity files — instance and operator, by depth |

---

## How to Use Them

### At Wake (Always)

Load all catalogs in a single multi-read call. This gives you a complete map of the system in ~3-4KB total. You now know what exists and where to find it — without loading any of it.

### During Work (On-Demand)

**"I need to understand the operator's cognitive profile"**
→ Check identity-catalog.json → `operator_cognitive-profile.md` → load it

**"What did the last session accomplish?"**
→ Check session-index.md → find relevant entry → load specific session file if needed

**"I need the git sync function"**
→ Check functions-catalog.md → `functions/git-sync.md` → load it

**"Was there a decision about [topic]?"**
→ Check decisions-catalog.md → find relevant decision → load it

---

## What Catalogs Are NOT

Catalogs are not summaries that replace reading the actual files. They are navigation aids. When you need the content, load the file. When you need to know if something exists and where, check the catalog.

Don't try to work from catalog entries alone for anything nuanced. The entry is a pointer, not the data.

---

## Keeping Catalogs Accurate

Catalogs are only useful if they reflect reality. When files are created, moved, or renamed:

1. Update the relevant catalog entry
2. If a new type of file is added (new decision, new function, new pattern), add an entry
3. Never leave a catalog entry pointing at a file that doesn't exist

A wrong catalog is worse than no catalog — it sends future sessions on a dead-end search.

---

## The Two-Level Rule

Every catalog operates at two levels:

**Level 1: Does this thing exist?**
The catalog answers this without loading anything.

**Level 2: What exactly does it contain?**
Load the file to answer this.

Never try to use a catalog entry to answer Level 2 questions. Load the file.

---

## Implementation Notes

**For neurodivergent users:** This pattern is especially valuable for ADHD/executive dysfunction because it:
- Reduces decision fatigue (clear map vs. searching)
- Minimizes context switching (load only what's needed)
- Preserves working memory (don't hold entire file tree in head)

**Token efficiency:** Loading 7-8 small catalog files (~4KB total) vs. loading every file (~100KB+) saves significant context window.

---

*Know where everything is. Load only what you need. Keep the map accurate.*
