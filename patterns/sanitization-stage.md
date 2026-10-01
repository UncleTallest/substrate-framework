---
pattern: Sanitization Stage
category: Publication
purpose: Gate every move from a private working substrate to a public repo through a personal-data check
created: 2026-10-01
---

# Pattern: Sanitization Stage

**Recognition criteria:** You are copying a pattern, example, template or log from your own working Substrate into anything other people can read: a public repo, a blog post, a shared folder.

## The Core Idea

Your working Substrate is full of real life: job searches, money, health, people, places, plans. Patterns are extracted *from* that life, so the first draft of any public pattern usually carries some of it along. A `.gitignore` does not help, because the leak is not a private file being committed. It is real content copied into a file that was meant to be public, most often an "example."

The sanitization stage is a required step between private and public. Nothing crosses without passing it, and a human signs off on the result.

## Why This Matters

- **Leaks hide in examples.** The fastest way to write an example is to copy a real one. That is exactly where real data slips through.
- **Git remembers.** Removing something in a later commit leaves it in the history. Catching it before the first public commit is far cheaper than rewriting history afterward.
- **Executive function is the bottleneck.** A checklist you run every time replaces a judgment call you might skip when tired.

## How to Apply It

1. **Stage the candidate.** Put the files you intend to publish in a staging area, never directly in the public repo.
2. **Run the checklist** over every staged file, including examples, comments and frontmatter:
    - **Identity and contact:** real names (other than an intended author credit), email addresses and aliases, phone numbers, usernames on other services.
    - **Locations:** home or work addresses, home-directory paths (`/home/<you>/…`), machine names, hostnames, IP addresses.
    - **Secrets:** API keys, tokens, passwords, connection strings, even expired ones.
    - **Money and work:** income sources, finances, employers, job applications, outreach targets, rates.
    - **Health and personal life:** diagnoses, medications, family details, schedules.
    - **Third parties:** anyone else's name, details or messages.
    - **Private infrastructure:** names of private repos, internal projects, service providers you use.
    - **Plans and timing:** dates or deadlines that reveal what you are doing and when.
3. **Substitute, don't redact.** Replace real content with clearly fictional content that keeps the same shape, and mark the file as a fictional example. `[REDACTED]` teaches the reader nothing.
4. **Record new rules as decisions.** When you catch a new kind of leak, add it to the checklist as a standing decision, so the next pass catches it without you having to remember.
5. **Ratify.** A human reviews the sanitized diff and approves it before it is published. An AI can run the checklist and flag findings; it does not approve its own output.

## When NOT to Use It

- **Content you intend to be personal.** An author credit, a public contact address or a deliberate first-person essay is fine. The stage checks for *unintended* disclosure.
- **As a substitute for keeping secrets out of the Substrate.** Credentials belong in a secrets manager, not in any file that might one day be copied.

## Implementation Notes

- **Already published?** Fix the files in a new commit immediately, then decide whether the history also needs rewriting. For a repo with very few commits, rewriting is cheap; later it costs every fork and clone.
- **AI-assisted runs:** give the assistant the checklist and ask it to list every finding with file and line before changing anything. Review the list, then let it substitute.
- **Automated runs:** the checklist can become a pre-commit or pre-merge check. Treat its findings as signal for a human, never as an automatic block-and-fix.

## Related Patterns

- [always-explain-why.md](always-explain-why.md) — each finding should say why it is a disclosure
- [catalog-system.md](catalog-system.md) — keep the checklist and its decisions findable
- [context-management.md](context-management.md) — task blocks are the most common source of leaked examples
