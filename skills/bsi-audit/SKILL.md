---
name: bsi-audit
description: Use when the user requests a BSI or slop audit of code, tests, configuration, documentation, prompts, or skills for verbosity, unnecessary complexity, duplication, dead weight, or misleading communication. Not for general code review or security, performance, or correctness audits.
---

# Slop audit

Find concrete opportunities to reduce the effort of understanding and maintaining the requested material. Produce an audit without changing files, including automatic cleanup or saved reports. Return the report in the conversation; save it only when requested.

Keep instructions and findings in plain engineering language. BSI branding may appear in the report title; satire must not replace explanations or ridicule authors.

## Inspect the scope

Use the target named by the user. For a repository request without a narrower target, use the current repository. If no target is available, ask for it. Read project guidance and trace relevant callers, tests, exports, configuration, and documentation. Inspect relationships between files, not just individual files. Exclude generated and vendored content unless requested; inspect its maintained source where relevant. State sampling and access limits.

| Area | Look for |
| --- | --- |
| Verbosity | Redundant explanations, boilerplate, comments that repeat the code |
| Complexity | Needless indirection, speculative flexibility, scattered logic, mixed responsibilities |
| Duplication | Repeated rules or explanations maintained in multiple places |
| Dead weight | Unused code, obsolete documentation, stale configuration, unsupported speculative features |
| Misleading communication | Vague names, inaccurate comments, unexplained jargon, inconsistent terminology |

Length, repetition, or one implementation is a reason to investigate, not proof of slop. Preserve useful explicitness and independent domain rules. Before recommending deletion, search references including exports, dynamic registration, fixtures, and configuration. No internal callers does not establish that a public API is unused.

Exclude security, performance, and correctness findings and fixes from this report, including separate bonus sections. Behavior preservation constrains a proposed simplification; it does not expand the audit into those domains.

## Establish findings

Each finding needs evidence of a reader or maintenance burden and a concrete, smaller remedy. Combine overlapping observations about the same underlying problem into one finding. Verify identical code expresses the same rule before recommending shared ownership. Keep unresolved assumptions visible; do not invent certainty or findings to fill a quota.

Classify each finding:

- **Obvious cleanup:** A demonstrated benefit, a specific mechanical change, and no unresolved behavior, consumer, ownership, or design question. Removing an exactly repeated setup sentence can qualify.
- **Needs discussion:** A supported readability concern whose purpose, benefit, replacement, or tradeoffs need a human decision. Uncertain findings cannot enter the obvious batch. Different ownership may justify keeping identical implementations.

Impact and certainty are separate: obvious does not mean important. Order each group by demonstrated burden. If evidence cannot establish a burden, omit the finding and mention material uncertainty under coverage limits.

For large scopes, independent read-only subagents may inspect distinct areas when available and permitted. Give each the scope, exclusions, and finding format below. Consolidate and verify their evidence before reporting; use a single reviewer when delegation adds no value.

## Report

Start with scope and coverage. Group findings under **Obvious cleanup** and **Needs discussion**, omitting empty groups. Assign stable IDs such as BSI-001, retained during review. Each finding contains:

- **Location and evidence:** Path and lines or section, with a short excerpt.
- **Burden:** The concrete cost to understanding or maintenance; identify the area.
- **Proposed change:** Exact deletion or replacement for obvious cleanup; a concrete candidate for discussion. Include a brief before/after when helpful.
- **Basis and open questions:** What was checked, why the classification fits, and what remains unresolved.

Finish with coverage limits. If nothing is supported, say so. Do not claim a partial inspection clears the whole repository. Findings are candidates, not mandatory work. Offer bsi-review for batch approval of obvious cleanup and individual discussion of the remainder; do not start editing during the audit.
