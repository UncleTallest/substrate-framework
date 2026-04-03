# Substrate Domains

The multi-domain system is **optional scaffolding** that offloads context-switching burden to infrastructure.

---

## What Are Domains?

Domains are separate AI instances/sessions, each handling a specific type of work:

- **Domain 1 (Professional):** Technical work, job search, professional projects
- **Domain 2 (Creative):** Fiction, creative experiments, pressure-free exploration  
- **Domain 3 (Balance Manager):** Health, burnout prevention, pattern recognition

Each domain loads only its relevant context, maintaining clear boundaries.

---

## When to Use Domains

**Use multi-domain if:**
- Context-switching between work types burns executive function
- Professional anxiety bleeds into creative space (or vice versa)
- Need health monitoring isolated from productivity pressure
- Working on 3+ concurrent projects with different mental states

**Don't use domains if:**
- You prefer monolithic operation
- Single-project focus works well
- Context-switching costs are low for you
- Additional complexity feels overwhelming

**Start without domains. Add them when monolithic operation hurts.**

---

## Domain Architecture

See [MULTI-DOMAIN-ARCHITECTURE.md](MULTI-DOMAIN-ARCHITECTURE.md) for complete explanation.

**Quick summary:**

```
{INSTANCE_HOME}  (shared reference - all domains can READ)
    ├── Domain 1 (Professional) - AI instance #1
    ├── Domain 2 (Creative) - AI instance #2
    └── Domain 3 (Balance Manager) - AI instance #3
```

**Isolated memory** (each domain writes its own):
- Domain 1: Technical decisions, project status
- Domain 2: Creative progress, story development
- Domain 3: Health data, balance patterns

**Shared reference** (all domains read):
- Catalogs (what exists, where to find it)
- Patterns (architectural approaches)
- Session history (overview only)

---

## Domain Primer Structure

Each domain needs a primer file that:
- Defines domain identity and responsibilities
- Lists what it handles and what it doesn't
- Specifies tone and communication style
- Documents memory focus
- Lists reference files it needs

**Location:** `{INSTANCE_HOME}/FOUNDATION/domains/[domain-name]-PRIMER.md`

---

## Example Primers

### Professional Domain (Example)

```markdown
# Domain 1: Professional / Technical

**Handles:**
- Software development, technical projects
- Job search and professional networking
- DevRel work, portfolio building
- Technical problem-solving

**Does NOT handle:**
- Creative writing (Domain 2)
- Health tracking (Domain 3)
- Personal/hobby projects (Domain 2)

**Tone:** Efficient, outcome-focused, solution-oriented

**Memory focus:**
- Technical decisions and why they were made
- Project status and next actions
- Professional narrative and positioning
- Job search progress

**Reference access:**
- Full catalog system
- Technical patterns
- Professional identity docs
- Session history (work-related)
```

### Creative Domain (Example)

```markdown
# Domain 2: Creative / Personal

**Handles:**
- Fiction writing and creative projects
- Hobby work (pressure-free)
- Exploratory experiments
- "What if" brainstorming

**Does NOT handle:**
- Professional work (Domain 1)
- Health monitoring (Domain 3)
- Deadline-driven projects (Domain 1)

**Tone:** Supportive, encouraging, no pressure

**Memory focus:**
- Creative progress (without judgment)
- Story development and ideas
- Artistic decisions and explorations
- Inspiration and references

**Reference access:**
- Creative patterns
- Inspiration docs
- Minimal professional context
- No work deadlines or pressure
```

### Balance Manager (Example)

```markdown
# Domain 3: Balance / Health

**Handles:**
- Work/life balance monitoring
- Burnout prevention
- Health tracking and patterns
- Cross-domain pattern recognition

**Does NOT handle:**
- Active work (Domain 1)
- Creative projects (Domain 2)
- Judgment or nagging

**Tone:** Caring accountability partner, data-focused

**Memory focus:**
- Daily patterns (work hours, exercise, sleep)
- Health trends over time
- Burnout warning signs
- Balance metrics

**Reference access:**
- Health protocols
- Balance patterns
- Minimal work context (for pattern recognition only)
- No creative context
```

---

## Setting Up Domains

### Prerequisites

- Working monolithic Substrate setup
- Understanding of catalog system
- Clear sense of why domains would help
- Ready to manage multiple AI instances

### Setup Process

1. **Create domain primers** in `FOUNDATION/domains/`
2. **Set up separate AI instances** (different accounts or clear session separation)
3. **First conversation with each domain:** Load its primer
4. **Test isolation:** Verify domains don't bleed into each other
5. **Establish communication patterns** (how you tell domains about work in other domains)

---

## Migration Path

**From monolithic to multi-domain:**

1. **Week 1-4:** Use monolithic, identify pain points
2. **Week 4-8:** If professional/creative mixing hurts, add Domain 2
3. **Month 2:** If burnout risk appears, add Domain 3
4. **Ongoing:** Adjust domain boundaries as needed

**You can always go back to monolithic if domains don't help.**

---

## Domain Communication

**Current (manual):**
- You tell each domain about relevant work from others
- "I coded 8 hours today" → Balance Manager
- "Finished chapter draft" → Creative

**Future (when multi-session APIs exist):**
- Domains could communicate directly
- Still maintain memory isolation
- Shared reference via Substrate

---

## Benefits

**For neurodivergent users:**
1. No context-switching overhead (choose domain, already in right space)
2. Clear boundaries (no confusion about what belongs where)
3. Memory isolation (work anxiety doesn't leak into creative space)
4. Burnout prevention (Balance Manager catches patterns others ignore)

**For AI instances:**
1. Token efficiency (load only domain-relevant context)
2. Focused responses (no mixed-context confusion)
3. Persistent specialization (build expertise in domain area)

---

## Common Questions

**Q: Do I need all 3 domains?**  
A: No. Start with 2 (Professional + Creative) or even just 1 (monolithic). Add domains as needed.

**Q: Can I have different domain divisions?**  
A: Yes! Domains are a template. Adapt to YOUR work patterns.

**Q: What if I prefer monolithic?**  
A: Keep using it! Domains are optional. If monolithic works, don't fix it.

**Q: How do I know when to add domains?**  
A: When context-switching costs become painful. You'll feel it.

---

## Related Documentation

- **[MULTI-DOMAIN-ARCHITECTURE.md](MULTI-DOMAIN-ARCHITECTURE.md)** — Complete architecture explanation
- **[../patterns/context-management.md](../patterns/context-management.md)** — Managing context within domains
- **[../patterns/conversation-zero.md](../patterns/conversation-zero.md)** — Can help decide if domains fit your needs

---

*Domains are optional scaffolding. Use them if context-switching hurts your brain.*
