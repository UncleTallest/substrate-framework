---
pattern: Conversation Zero
category: Onboarding
purpose: Initial setup conversation that establishes infrastructure
created: 2026-04-02
---

# Pattern: Conversation Zero

**Recognition criteria:** New user setting up Substrate for the first time; need to establish foundation before doing actual work.

---

## The Core Idea

**Conversation Zero** is the setup session where you build Substrate's infrastructure with your AI collaborator **before** trying to do real work. Think of it as "setting up your workshop before building furniture."

**Not this:**
> "Help me with my project" → [chaos as you try to build infrastructure mid-work]

**This:**
> "Let's set up Substrate first" → [infrastructure in place] → "Now help me with my project"

---

## Why This Matters

**For neurodivergent users:**
- Reduces "am I doing this right?" anxiety
- Creates clear structure before complexity
- Prevents mixing setup work with real work
- Establishes patterns for future sessions

**For AI collaboration:**
- Builds shared context deliberately
- Documents decisions made during setup
- Creates foundation files to reference later
- Avoids assumptions about structure

---

## The Conversation Zero Flow

### Phase 1: Understand Your Needs (10 min)

**AI asks, you answer:**

```
"Before we set up Substrate, help me understand your needs:

1. What discontinuity challenges do you face?
   - ADHD/executive function issues?
   - Context-switching costs?
   - Memory gaps?
   - Time blindness?

2. How do you work?
   - Single long-term project?
   - Multiple concurrent projects?
   - Frequent switching?
   - Long breaks between sessions?

3. What complexity are you ready for?
   - Start minimal (just catalogs + session summaries)?
   - Multi-domain from day one?
   - Build gradually as needs emerge?

4. What's your technical comfort?
   - Comfortable with file structures and command line?
   - Prefer simpler approaches?
   - Want to understand the internals?
"
```

**AI listens, adapts recommendations to YOUR profile.**

---

### Phase 2: Choose Your Setup (5 min)

Based on your answers, AI recommends a starting point:

**Option A: Minimal Start (recommended for most)**
```
{INSTANCE_HOME}/
├── FOUNDATION/
│   └── catalogs/
│       └── session-index.md
├── session-metadata/
└── context/
    └── active-context.md
```

**Option B: Task Blocks from Day One**
```
{INSTANCE_HOME}/
├── FOUNDATION/
│   └── catalogs/
│       └── session-index.md
├── session-metadata/
├── context/
│   ├── active-blocks.json
│   └── blocks/
│       └── TEMPLATE.md
```

**Option C: Multi-Domain**
```
{INSTANCE_HOME}/
├── FOUNDATION/
│   ├── catalogs/
│   │   └── session-index.md
│   └── domains/
│       ├── professional-PRIMER.md
│       └── creative-PRIMER.md
├── session-metadata/
└── context/
```

**Key:** Choose based on immediate needs, not future possibilities. You can upgrade later.

---

### Phase 3: Build Together (15 min)

**AI helps you create files interactively:**

```
"Let's create your directory structure. Where do you want your 
Substrate home? (Common choices: ~/substrate, ~/Documents/substrate, 
C:\Substrate on Windows)"

[You choose location]

"Creating directories...
✓ {INSTANCE_HOME}/FOUNDATION/catalogs/
✓ {INSTANCE_HOME}/session-metadata/
✓ {INSTANCE_HOME}/context/

Now let's create your first session-index.md. What are you planning 
to work on initially?"

[You describe your work]

"I'll create an initial entry:

## 2026-04-02 - Substrate Setup (Conversation Zero)

**Session type:** Planning / Setup  
**Duration:** ~30 minutes

**Work completed:**
- Established Substrate infrastructure
- Created directory structure
- Set up catalog system
- Configured for [your workflow type]

**Key decisions:**
- Starting with [minimal/task-blocks/multi-domain] approach
- Will upgrade to [X] when [condition]

**Next session:**
- [ ] Start actual work on [your project]
- [ ] Try first end-of-turn summary

Does this capture it?"

[You review, approve]
```

---

### Phase 4: Document Setup Decisions (5 min)

**Create SETUP-NOTES.md in FOUNDATION:**

```markdown
# Substrate Setup Decisions

**Date:** 2026-04-02
**Approach:** Minimal start
**Primary use:** Single long-term project (software development)

## Why This Setup

Starting minimal because:
- First time using Substrate
- Single project focus initially
- Want to learn patterns before adding complexity
- Can upgrade to task blocks if needed later

## Planned Upgrades

Will consider task blocks when:
- Active-context.md hits ~500 lines
- Start working on multiple projects concurrently
- Feel the pain of monolithic context

Will consider multi-domain when:
- Need to separate professional/creative work
- Context-switching becomes costly

## Neurodivergent Profile

Challenges:
- ADHD: working memory gaps, time blindness
- Context-switching costs high
- Need external memory for continuity

Preferences:
- Explicit structure over implicit
- Written documentation over remembering
- Clear next-actions lists
```

This becomes your reference for "why did I set it up this way?"

---

### Phase 5: Test the System (5 min)

**Do a mini round-trip:**

```
"Let's test your setup. I'll create a small task in active-context.md, 
then we'll do an end-of-turn summary to close this session.

This gives you a working example of the full cycle:
1. Load context at wake
2. Work on task
3. Create summary at end
4. Next session loads summary and continues

Ready?"

[Do mini task]

"Now let's create your first end-of-turn summary following the 
protocol in patterns/end-of-turn-summary-protocol.md..."

[Create summary together]

"Perfect! Your substrate-framework is set up. Next session, you'll:
1. Load session-metadata/2026-04-02-summary-setup.md
2. Continue with actual work

The infrastructure is in place."
```

---

## What You'll Have After Conversation Zero

1. **Directory structure** tailored to your needs
2. **Initial session-index.md** documenting setup
3. **SETUP-NOTES.md** explaining decisions
4. **First end-of-turn summary** showing the pattern
5. **Understanding** of how Substrate works
6. **Confidence** to start real work next session

---

## Common Mistakes

**Mistake 1: Skipping Conversation Zero**
> Jump straight to "help me with my project" without setup → chaos

**Mistake 2: Over-engineering from day one**
> Start with multi-domain + task blocks + full catalog system → overwhelmed

**Mistake 3: Not documenting setup decisions**
> Build structure without noting "why" → future confusion

**Mistake 4: Rushing the test**
> Skip the mini round-trip → don't verify system works

**Mistake 5: Not adapting to your profile**
> Copy someone else's setup without considering your needs

---

## Conversation Zero Checklist

Use this to ensure you've covered everything:

**Understanding Phase:**
- [ ] Identified your discontinuity challenges
- [ ] Described your work patterns
- [ ] Chose complexity level
- [ ] Assessed technical comfort

**Setup Phase:**
- [ ] Chose directory location
- [ ] Created directory structure
- [ ] Selected approach (minimal/blocks/domains)

**Documentation Phase:**
- [ ] Created initial session-index.md
- [ ] Wrote SETUP-NOTES.md
- [ ] Copied relevant patterns from substrate-framework

**Test Phase:**
- [ ] Did mini task
- [ ] Created first end-of-turn summary
- [ ] Verified you understand the cycle

**Completion:**
- [ ] Know where everything is
- [ ] Understand why setup is this way
- [ ] Ready to start real work next session

---

## After Conversation Zero

**Next session starts with:**

```
"Load my Substrate context:
1. {INSTANCE_HOME}/session-metadata/2026-04-02-summary-setup.md
2. {INSTANCE_HOME}/context/active-context.md

Let's work on [your actual project]."
```

**AI loads context, knows your setup, continues from where you left off.**

---

## Upgrading Later

**When you outgrow your initial setup:**

1. **Reference SETUP-NOTES.md** — Remember why you started minimal
2. **Read upgrade pattern** — context-management.md shows migration path
3. **Do upgrade as Conversation Zero-style session** — Build new structure together
4. **Document the upgrade** — Update SETUP-NOTES.md with new decisions

**Don't upgrade until you feel the pain of the current approach.**

---

## Related Patterns

- [catalog-system.md](catalog-system.md) — What catalogs are and why they matter
- [context-management.md](context-management.md) — Choosing between simple and complex
- [end-of-turn-summary-protocol.md](end-of-turn-summary-protocol.md) — How to close sessions

---

*Conversation Zero builds the foundation. Everything after builds on this.*
