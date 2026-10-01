# Task Block: Plant-Care App Documentation

**ID:** plant-docs-2026-04-02  
**Status:** active  
**Priority:** high  
**Created:** 2026-04-02  
**Last Updated:** 2026-04-02 18:45 UTC  
**Estimated Completion:** 2026-04-05

---

> **Note:** This is a fictional example. Names, projects and details are invented to show the shape of a task block. Never publish a real task block without running it through the [sanitization stage](../patterns/sanitization-stage.md).

---

## Quick Context

Writing user-facing documentation for a small open-source plant-care app so new contributors and users can get started without asking the maintainer.

---

## Objective

Publish a getting-started guide, a configuration reference, and a contributor guide for the app, each short enough to read in one sitting.

---

## Current State

- ✓ **Completed:**
  - Docs folder structure created
  - Getting-started guide drafted
  - Screenshots captured for setup steps

- ⏳ **In Progress:**
  - Configuration reference (watering schedules, notification settings)
  - Contributor guide

- ⏹️ **Pending:**
  - Review pass by a second contributor
  - Link docs from the README
  - Announce in the project's discussion forum

---

## Next Actions

1. Finish the configuration reference
2. Draft the contributor guide from the existing PR template
3. Ask a contributor to review both
4. Merge and link from the README

---

## Key Files

- `/docs/getting-started.md` - Setup walkthrough
- `/docs/configuration.md` - Settings reference
- `/docs/contributing.md` - Contributor guide
- `/README.md` - Entry point that links the docs

---

## Dependencies

**This task depends on:**
- settings-refactor (configuration options must be final before documenting them)

**Tasks depending on this:**
- release-1-2 (release notes link to the new docs)

---

## Notes

**Key decisions:**
- Keep each page under 10 minutes of reading
- Document current behavior only; no roadmap promises in user docs
- Screenshots use the default theme so they stay accurate longer

---

## Related

- **Project:** plant-care app
- **Context:** Domain 1 (Professional) work
- **Timeline:** Target the 1.2 release

---

*A task block holds everything needed to resume this work cold, in one file.*
