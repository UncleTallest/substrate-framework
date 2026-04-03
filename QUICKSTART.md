# Substrate Framework - Quick Start

**Get started with neurodivergent cognitive scaffolding for AI collaboration in 30 minutes.**

---

## Prerequisites

- Access to Claude (claude.ai, API, or other AI with context persistence capability)
- A place to store files (local directory, cloud storage, etc.)
- Willingness to experiment and adapt patterns to your brain

---

## Step 1: Choose Your Starting Point (5 min)

**Option A: Minimal Start** (recommended for beginners)
- Single AI instance
- Just catalog system + session summaries
- No domains yet

**Option B: Multi-Domain Start** (if you already know context-switching burns you)
- Professional + Creative domains
- Isolated contexts from day one
- Add Balance Manager later

**Option C: Single Pattern** (if you just need one thing)
- Pick one pattern from `/patterns/` 
- Implement just that
- Add more as needed

**For this guide, we'll use Option A (Minimal Start).**

---

## Step 2: Set Up Your File Structure (5 min)

Create a directory structure that works for your operating system:

```
~/substrate/                    # Or C:\Substrate\ on Windows
├── FOUNDATION/
│   ├── catalogs/
│   │   └── session-index.md   # Your work history
│   └── patterns/              # Copy from this repo
├── session-metadata/          # End-of-turn summaries
└── context/
    └── active-context.md      # What you're working on now
```

**Copy these files from substrate-framework repo:**
- `patterns/catalog-system.md`
- `patterns/end-of-turn-summary-protocol.md`

---

## Step 3: Create Your First Catalog (5 min)

Create `FOUNDATION/catalogs/session-index.md`:

```markdown
# Session Index

Track what you accomplished in each session.

---

## 2026-04-02 - Initial Substrate Setup

**Work completed:**
- Created directory structure
- Set up catalog system
- First end-of-turn summary

**Next session:**
- [ ] Start using active-context.md
- [ ] Build first domain (if multi-domain)
```

---

## Step 4: Configure Your AI Instance (10 min)

### For Claude.ai Desktop/Web:

In "Settings → Custom Instructions" (or your AI platform's equivalent), add:

```markdown
# Substrate Framework

I use the Substrate cognitive scaffolding framework for managing discontinuity.

**At session start:**
1. Check {INSTANCE_HOME}/FOUNDATION/catalogs/session-index.md
2. Check {INSTANCE_HOME}/context/active-context.md
3. Ask me what I'm working on today

**During session:**
- Use catalog-first navigation (load catalogs, then specific files)
- Track decisions and progress
- Tell me when we're at 80% token budget

**At session end:**
- Create end-of-turn summary (follow protocol in patterns/)
- Save to {INSTANCE_HOME}/session-metadata/YYYY-MM-DD-summary-[title].md
- Update session-index.md
```

Replace `{INSTANCE_HOME}` with your actual path (e.g., `~/substrate` or `C:\Substrate`).

---

## Step 5: First Conversation (5 min)

Start a new conversation with your AI instance:

```
I'm using the Substrate framework. Load:
1. ~/substrate/FOUNDATION/catalogs/session-index.md
2. ~/substrate/context/active-context.md

Let's work on [your actual task].
```

The AI will orient itself using the catalogs, then help with your work.

---

## Step 6: End Your First Session (5 min)

When you're ready to wrap up:

```
Create an end-of-turn summary following the protocol in 
~/substrate/patterns/end-of-turn-summary-protocol.md
```

The AI will generate a summary capturing:
- What you accomplished
- Key decisions made
- Next session priorities

Save this to `session-metadata/2026-04-02-summary-[topic].md`

---

## Next Steps

**After your first successful session:**

1. **Add more catalogs** (as needed):
   - `patterns-catalog.md` - Which patterns you're using
   - `decisions-catalog.md` - Major decisions you've made
   
2. **Try multi-domain** (if context-switching is painful):
   - Read `domains/MULTI-DOMAIN-ARCHITECTURE.md`
   - Create Professional domain first
   - Add others as needed

3. **Customize patterns**:
   - Adapt catalog system to your file structure
   - Modify end-of-turn protocol to capture what matters to you
   - Create new patterns for problems you discover

---

## Troubleshooting

**"AI doesn't load my files"**
- Check file paths are correct
- Verify AI has filesystem access (Desktop app) or provide content manually
- Some platforms require explicit file upload

**"Catalogs feel like extra work"**
- Start with just session-index.md
- Add others only when you feel the pain of not having them
- Catalogs pay off after 3-5 sessions when you forget what you did

**"I don't need end-of-turn summaries"**
- Try it for one week
- See if it helps you restart work after breaks
- Skip it if it doesn't help your brain

---

## What Makes This Different

**Not a prompt library:** You're not just configuring AI responses, you're building persistent infrastructure.

**Not automation:** You're creating external memory that bridges discontinuity gaps.

**Not templates:** Every pattern is meant to be adapted to how YOUR brain works.

**It's scaffolding:** Like physical scaffolding supports construction, these patterns support your cognitive work.

---

## Getting Help

- **Read patterns/** for specific solutions
- **Check examples/** for implementation samples
- **Adapt freely** - your brain's architecture is unique

---

*Start minimal. Add patterns as you need them. Build scaffolding that fits YOUR discontinuity.*
