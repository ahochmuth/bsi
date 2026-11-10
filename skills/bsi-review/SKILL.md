---
name: bsi-review
description: Use when the user wants to work through BSI audit findings, approve obvious cleanup, discuss individual slop refactors, or resume decisions and implementation from a previous slop review. Not for general code review.
---

# Review slop refactors

Help the human decide which readability and maintenance improvements are worthwhile, then implement approved changes. Use plain engineering language. Security, performance, and correctness improvements are outside this review; preserving existing behavior remains a constraint.

## Resume from evidence

Use the supplied audit and any recorded decisions. Preserve finding IDs and prior approvals. If no findings are available, ask for the report or offer bsi-audit; do not invent candidates or repeat a completed audit. Read current source, project guidance, relevant callers, tests, exports, and configuration before relying on a finding.

Investigate facts using available material. Ask the human about intent, ownership, and tradeoffs, or facts unavailable to the agent. Do not make them look up information the agent can inspect.

## Obvious cleanup

A finding qualifies only when it has a demonstrated benefit, a mechanical change, and no unresolved behavior, consumer, ownership, or design question. A short diff or confident audit label is not sufficient.

Present qualifying items together, each with its ID, location, and exact deletion or replacement. A compact diff is useful when prose would be ambiguous. Ask for one batch decision, allowing individual exclusions or moves to discussion. Wait for that decision before introducing another decision.

For example: "BSI-001 deletes the second identical setup sentence. BSI-002 deletes the comment repeating toUpperCase(). Apply both, or exclude an ID?"

The label alone never authorizes edits. Apply only the presented changes the human approves. Honor existing authorization without asking again. If the source or proposed change has materially changed since approval, explain the difference and return that item to discussion; continue unrelated approved work.

## Individual discussion

Work through the remaining candidates one at a time in audit order unless the human chooses otherwise.

1. Show the evidence and concrete burden, then explain what purpose the existing design may serve.
2. Recommend the smallest simplification, describe tradeoffs, and keep "leave it as it is" available.
3. Ask one focused question that resolves the next meaningful uncertainty. State a recommended answer when evidence supports one. Wait for the answer; investigate newly exposed facts before asking again.
4. Record the decision as proceed, revise, defer, or dismiss. For proceed, confirm the concrete change is covered by the user's authorization before implementing. For revise, resolve the changed proposal before treating it as approved.

End the discussion when the decision is clear. Do not require a fixed number of questions or turn a simple choice into an interview.

## Implement and retain decisions

When implementation is authorized, make the smallest approved change, including affected callers, tests, fixtures, documentation, and configuration. If it requires a wider change than presented, return that expansion to discussion. Preserve behavior, public contracts, useful context, and existing safeguards. Do not include unrelated fixes.

Verify in proportion to the change: inspect textual deletions; run relevant existing checks for code refactors, adding a focused behavioral check when needed. Report failures or unavailable checks without claiming success. Keep pending proposals distinct from completed work.

If the user asks for a plan only, record the plan without editing source. Plan approval does not itself override that restriction.

Maintain a concise record in the conversation: ID, decision, agreed change or reason, implementation status, and verification. Update an existing saved report only when authorized; otherwise provide a copyable handoff for resuming. Do not recreate dismissed candidates without new evidence. Finish when the selected scope is resolved or the human pauses.
