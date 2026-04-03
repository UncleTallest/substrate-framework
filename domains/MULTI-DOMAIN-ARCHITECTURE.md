---
architecture: Multi-Domain System
category: Cognitive Scaffolding
purpose: Offload context-switching burden to infrastructure
created: 2026-03-20
---

# Multi-Domain Architecture

## The Problem

**Neurodivergent context-switching challenge:**
Switching between "professional work brain" and "creative writing brain" and "health management brain" burns excessive executive function. Traditional solutions (calendars, task managers) require the human to manage the switch.

**AI instance challenge:**
A single AI instance handling professional/creative/health tasks mixes contexts, burning tokens and cognitive load maintaining multiple mental states.

---

## The Solution: Domain Separation

Substrate offloads context-switching to the infrastructure by maintaining separate AI instances per domain.

### Domain Architecture

```
{INSTANCE_HOME}  (shared reference - READ access for all domains)
    ├── Domain 1 (Professional)
    ├── Domain 2 (Creative)
    └── Domain 3 (Balance Manager)
```

Each domain:
- Has its own AI instance/session
- Loads only domain-specific context
- Maintains isolated conversational memory
- Shares read access to foundation files

---

## The Three Core Domains

### Domain 1: Professional
**Handles**:
- Technical work, job search, professional projects
- Planning + Building + Shipping
- Problem-solving and architecture
- Professional communication

**Tone**: Efficient, outcome-focused  
**Memory**: Technical decisions, project status, professional narrative  
**Reference**: Full Substrate access on-demand

---

### Domain 2: Creative
**Handles**:
- Fiction writing, creative experiments
- Hobby projects (pressure-free)
- Exploratory work without deadlines
- "What if" brainstorming

**Tone**: Supportive, encouraging, no pressure  
**Memory**: Creative progress, story development, artistic decisions  
**Reference**: Selective Substrate (creative processes, inspiration docs)

---

### Domain 3: Balance Manager
**Handles**:
- Work/life balance monitoring
- Burnout prevention and health tracking
- Pattern recognition across domains
- Accountability without nagging

**Tone**: Caring partner, data-focused  
**Memory**: Daily patterns, health trends, burnout signals  
**Reference**: Minimal Substrate (health protocols, balance patterns)

---

## How Domains Work

### Isolated Memory (WRITE access)
Each domain maintains its own conversational history:
- Domain 1: Technical progress, professional narrative
- Domain 2: Creative progress, story development
- Domain 3: Balance patterns, health data

**Key:** Professional work doesn't pollute creative space. Creative exploration doesn't create technical debt anxiety. Health monitoring doesn't judge work choices.

### Shared Reference (READ access)
All domains read from shared foundation:
- Catalogs (what exists, where to find it)
- Patterns (architectural approaches)
- Identity (operator cognitive profile)
- Session history (overview only)

---

## When to Use Which Domain

| Scenario | Domain |
|----------|--------|
| Building software feature | Domain 1 |
| Job applications | Domain 1 |
| Writing fiction | Domain 2 |
| Creative brainstorming | Domain 2 |
| "Did I exercise this week?" | Domain 3 |
| "I've been coding 12 hours/day for 5 days" | Domain 3 |
| Planning technical architecture | Domain 1 |
| Debugging production issue | Domain 1 |

---

## Benefits

**For neurodivergent users:**
1. **No context-switching overhead**: Choose domain, already in right mental space
2. **Clear boundaries**: No confusion about what belongs where
3. **Memory isolation**: Professional anxiety doesn't leak into creative work
4. **Burnout prevention**: Balance Manager catches patterns other domains ignore

**For AI instances:**
1. **Token efficiency**: Load only domain-relevant context
2. **Focused responses**: No mixed-context confusion
3. **Persistent specialization**: Build expertise in domain area
4. **Scalable**: Add more domains without bloating existing ones

---

## Implementation Notes

### Minimum Viable Setup
Can start with just 2 domains (Professional + Creative) or even monolithic and add domains later.

### Account Strategy
- Use separate AI accounts per domain (Claude Pro vs Free)
- Or use same account with clear session separation
- Or use conversation naming/organization in single account

### Progressive Activation
Don't need all 3 domains immediately:
1. Start with Domain 1 (Professional) using existing setup
2. Add Domain 3 (Balance Manager) when burnout risk appears
3. Add Domain 2 (Creative) when ready to protect creative space

---

## Domain Primer Structure

Each domain needs a primer file that:
- Defines domain identity and responsibilities
- Lists what it handles and what it doesn't
- Specifies tone and communication style
- Documents memory focus
- Lists reference files it needs

**Location**: `{INSTANCE_HOME}/FOUNDATION/domains/[domain-name]-PRIMER.md`

See `examples/` for sample domain primers.

---

## Communication Between Domains

**Current**: Manual (human reports across domains)
- "I coded 8 hours today" → tell Balance Manager
- "Finished chapter draft" → tell Creative

**Future**: Native cross-domain communication (when multi-session APIs available)
- Domains can interact directly
- Still maintain memory isolation
- Shared reference via Substrate

---

## Optional Nature of Domains

**Important:** The domain system is **optional scaffolding**. 

**Use domains if:**
- Context-switching between work types burns executive function
- You need creative space protected from professional anxiety
- Burnout monitoring requires isolation from productivity pressure

**Don't use domains if:**
- You prefer monolithic operation
- Context-switching costs are low
- Single integrated view works better for your brain

The catalog system, patterns, and other Substrate components work with or without domains.

---

*The human doesn't context-switch — they just choose which domain to engage. The AI instance already has full context.*
