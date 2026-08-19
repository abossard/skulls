---
name: research
description: Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo. Use when the user wants a topic researched, docs or API facts gathered, or reading legwork delegated to a background agent.
---

Spin up a **background agent** to do the research, so you keep working while it reads.

Its job:

1. Investigate the question against **primary sources** (official docs, source code, specs, first-party APIs), not a secondary write-up of them. Follow every claim back to the source that owns it.
2. Write the findings to a single Markdown file using the evidence contract below.
3. Save it where the repo already keeps such notes; match the existing convention, and if there is none, put it somewhere sensible and say where.

## Evidence contract

Start the file with the exact question, its scope, the date, and a stopping condition. Record each finding in one table:

| Type | Claim | Evidence | Scope or version | Checked | Invalidated by |
| --- | --- | --- | --- | --- | --- |
| sourced fact / observed result / inference / unresolved | <precise claim> | <primary-source URL, source path, command, or artifact> | <where the claim applies> | <YYYY-MM-DD> | <change that requires re-checking it> |

- **Sourced fact** follows a claim to the source that owns it.
- **Observed result** names what was run and the concise result. Do not paste complete logs.
- **Inference** links its supporting evidence and stays labelled as reasoning, not fact.
- **Unresolved** states what evidence is missing instead of filling the gap with an agent assertion.

Stop when the scoped question can be answered, every answer-bearing claim is sourced or observed, and contradictions and unresolved questions are visible. Do not broaden the question to make the file look comprehensive. If the stopping condition cannot be met, return the partial file as **unresolved** and say why.
