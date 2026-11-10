Bureau of Slop Investigation (BSI)

<img src="skills/bsi-audit/assets/bsi-icon.png" alt="BSI logo: a slop monster crossed out by a red prohibition sign" width="180">

Protecting Human Minds from Crimes Against Readability.

Has your documentation been contaminated by AI-generated slop? Are your precious mental tokens being consumed by unnecessary abstractions, corporate word salads, and paragraphs that say absolutely nothing?

The Bureau is here to help.

🔎 /bsi-audit — Investigate crimes against readability.

⚖️ /bsi-review — Review the evidence, approve cleanup, and prosecute excessive verbosity.

🧠 Reclaim your mental tokens. Let the bots clean up their own mess.

All documentation is presumed guilty until proven useful.

⸻

The Bureau

BSI is a two-skill suite for identifying and eliminating unnecessary complexity, duplication, and maintenance overhead in code and documentation.

The branding is satire. The engineering is not.

Skill	Responsibility
bsi-audit	Investigate verbosity, unnecessary complexity, duplication, dead code, and misleading documentation. Produces findings without modifying files.
bsi-review	Review findings, approve straightforward cleanup, and evaluate more substantial refactors individually before implementation.

Jurisdiction: Readability, maintainability, and unnecessary complexity.

Security, performance, and correctness audits fall outside the Bureau’s jurisdiction. All approved refactors must preserve existing behavior.

Investigation Procedure

1. Audit — Inspect a repository, directory, or supplied material.
2. Report — Present actionable findings, separating straightforward cleanup from changes requiring discussion.
3. Approve — Review and approve the cleanup batch, excluding anything that warrants further investigation.
4. Deliberate — Evaluate remaining proposals individually: approve, revise, defer, or dismiss.
5. Enforce — Apply approved changes, verify behavior, and preserve traceability to the original findings.

Bureau policy: A finding is a hypothesis, not a mandate. Fewer lines do not automatically mean better engineering.

Usage

BSI consists of two self-contained agent skills located under skills/. They are not installed automatically.

Once the skills are made available to your agent, invoke them with:

$bsi-audit Audit src/ and docs/ for slop.
$bsi-review Review these BSI findings with me.

Acknowledgments

The review workflow draws inspiration from Matt Pocock’s grill-me and grilling skills.

BSI follows the same principle: investigate independently, but leave consequential decisions to the human.

Unlike those workflows, BSI provides batch approval for straightforward cleanup while reviewing substantial refactors individually. Neither skill is a runtime dependency.
