---
name: implement
description: "Implement a piece of work based on a spec or set of tickets."
disable-model-invocation: true
---

# Implement

Implement the work described by the user in the spec, ticket, or current conversation.

## Process

1. Read the source of the work and list its acceptance criteria. Before changing code, pair every criterion with its agreed verification method and seam. If either is missing, settle it with the user.
2. Use `/tdd` where possible, at those pre-agreed seams.
3. Run typechecking and focused tests regularly.
4. Once the implementation exists, use `/code-review` and address the findings you agree with. A review is static analysis, not proof that the behavior works.
5. After the last relevant code change, run the full test suite once and verify every acceptance criterion.

## Evidence gate

Evidence is an observed result from the current revision or worktree, produced by the criterion's verification method. Reading the code, a clean `/code-review` report, or saying that the work is complete is not evidence.

For a UI criterion, use the repo's existing browser automation. If it has none, use browser tooling already supplied by the harness rather than adding a framework just for verification. Drive the critical path, assert the expected DOM state, check console errors and failed network requests, and capture a deterministic screenshot. Record its route, viewport, fixture or state, and revision. A screenshot proves appearance at that state, not functional behavior, so keep it beside the browser assertions rather than in place of them.

Present the final result as:

| Acceptance criterion | Verification | Observed result | Artifact |
| --- | --- | --- | --- |
| <criterion> | <command or method at the agreed seam> | <what actually happened> | <test output, CI run, screenshot, trace, or source pointer> |

Keep outputs concise and point at existing artifacts instead of committing complete logs. Evidence is **fresh** only when it was collected after the last change that could affect that criterion. Re-run affected rows after review fixes or any later edit.

State **Done** only when every row has fresh evidence. Otherwise state **Unverified**, name the missing evidence and why it could not be collected, and ask the user how to proceed. Never infer a passing row from code or from another row.

When an originating work item is available, attach the evidence table, check off only verified criteria, and close it only when every row is verified. Commit the work to the current branch after the gate; commit partial or unverified work only when the user explicitly asks for it.
