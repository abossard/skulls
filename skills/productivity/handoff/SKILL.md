---
name: handoff
description: Compact the current conversation into a handoff document for another agent to pick up.
argument-hint: "What will the next session be used for?"
disable-model-invocation: true
---

Write a handoff document summarising the current conversation so a fresh agent can continue the work. Save to the temporary directory of the user's OS - not the current workspace.

Include a "suggested skills" section in the document, naming which skills the next agent should call the Skill tool for.

Do not duplicate content already captured in other artifacts (specs, plans, ADRs, issues, commits, diffs). Reference them by path or URL instead.

Include these evidence sections:

```markdown
## Verified

- <claim>: <method and observed result>

## Unverified

- <claim or assumption>: <missing verification and why>

## Evidence pointers

- <path or URL>: <what it supports>
```

An agent statement is not evidence. Put a claim under **Verified** only when the session observed it through a test, command, browser run, primary source, or explicit human judgment. Label human judgment as such: it verifies a decision, not system behavior. Put everything else under **Unverified**, even if the agent sounded confident. Point to existing outputs, screenshots, CI runs, prototypes, research, and source documents without copying them into the handoff.

Redact any sensitive information, such as API keys, passwords, or personally identifiable information.

If the user passed arguments, treat them as a description of what the next session will focus on and tailor the doc accordingly.
