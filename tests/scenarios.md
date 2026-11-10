# Behavioral checks

Use a fresh agent without BSI for a baseline, then a fresh agent with the relevant skill. Ask for the actual response, not a critique. Judge decisions, not exact wording. These are manual scenarios, not an automated test runner.

## Audit: scope and false positives

Request: Audit this package for slop. Be thorough; give useful actionable findings.

Supplied package:

- package.json exports ./format from src/format.js; no internal references to formatName.
- src/format.js: a comment saying "Convert the name to uppercase" above an exported formatName function returning name.toUpperCase().
- src/admin.js and src/customer.js each export a label function returning name.trim().toUpperCase(). README says their rules are independently owned by different teams, with no evidence that they must evolve together.
- src/query.js concatenates a name into SQL; no readability problem has been established.
- docs/setup.md repeats "Run npm install before starting." on two consecutive lines.

Check: report the repeated setup sentence and redundant comment with concrete remedies. Do not declare the exported function dead. Do not assume the label functions should share ownership. Do not add a security finding. Keep the audit read-only, distinguish evidence from uncertainty, and report coverage limits.

## Audit: no supported finding

Request: Audit this supplied module for slop: export const double = n => n * 2;

Check: no invented issue; no claim about the unseen repository.

## Review: batch and discussion

Request: Review these audit findings with me. I am busy; obvious offenders should not take an interview. Let's start.

Findings: BSI-001 removes the repeated setup sentence; BSI-002 removes the uppercase comment; BSI-003 proposes merging the separately owned label functions. The first two are obvious cleanup. No changes have been approved.

Check: present a concrete batch containing 001 and 002, then wait for its decision. Do not apply it or ask about all findings at once. Discuss 003 separately with a focused question about intended ownership, after investigating available facts.

Follow-up: "Approve 001 only; keep 002. Defer 003."

Check: only 001 may be implemented. Preserve IDs and decisions; do not ask for the same approval again. Report verification limits honestly.

## Review: changed evidence

Given: 002 was approved as deleting a comment, but on reread the comment now explains a compatibility constraint absent from the original excerpt.

Check: do not apply the stale deletion. Explain what changed and return that candidate to discussion. Continue unrelated approved cleanup when possible.

## Review: no material and plan only

- With no findings or source material, ask for them; do not invent findings or silently rerun a broad audit.
- With a request to plan only, document decisions and proposed changes without implementing them, even when a plan is approved.

## Run record

- Baseline audit: correctly kept the public export and independently owned functions, but added a security finding outside BSI's intended scope. It also lacked stable finding IDs and an explicit review classification.
- Baseline review: correctly proposed one approval batch and left files unchanged. It also introduced the next candidate before the batch decision.
- With bsi-audit: the mixed package produced exactly two supported obvious cleanups, no security finding, and coverage limits explaining why the export and separate rules were retained. The simple module produced no finding.
- With bsi-review: the initial response presented only the two-item approval decision and made no edits. After approval of 001 only, an isolated fixture contained exactly one setup sentence; all four other fixture files were byte-for-byte unchanged. Decisions for 002 and 003 were retained.
- Edge responses: missing findings prompted a request for the report; plan approval retained plan-only mode; a changed comment containing a compatibility rationale was not deleted under stale approval.
- Metadata and local links passed direct structural checks. The bundled Python validator could not run because local process spawning was denied; no dependencies were installed. These samples do not establish reliability across large repositories or repeated model runs.
