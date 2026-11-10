# Bureau of Slop Investigation (BSI)

<img src="skills/bsi-audit/assets/bsi-icon.png" alt="BSI logo: a slop monster crossed out by a red prohibition sign" width="180">

*Protecting Humans from Crimes Against Readability.*

Two skills for finding unnecessary reading and maintenance work, then deciding what to remove. The branding is satire; findings and implementation use plain engineering language.

| Skill | Purpose |
| --- | --- |
| [bsi-audit](skills/bsi-audit/SKILL.md) | Inspect verbosity, complexity, duplication, dead weight, and misleading communication without changing files. |
| [bsi-review](skills/bsi-review/SKILL.md) | Approve obvious cleanup together, then examine other refactors one at a time. |

Security, performance, and correctness audits are outside BSI's scope. Approved refactors preserve existing behavior.

## Workflow

1. Request an audit of a repository, folder, or supplied material.
2. Review concrete findings grouped into obvious cleanup and candidates needing discussion.
3. Approve the presented cleanup batch, excluding any items you want to discuss.
4. Discuss remaining candidates individually; proceed, revise, defer, or dismiss.
5. Apply approved changes and verify them. Keep decisions attached to the original finding IDs.

A finding is a hypothesis, not an obligation to change something. Fewer lines alone do not establish an improvement.

## Use

These are skill source directories, not an installed plugin. Each directory under skills/ is self-contained. Once made available to your agent, example requests are:

- "$bsi-audit Audit src/ and docs/ for slop."
- "$bsi-review Review these BSI findings with me."

The review approach is inspired by Matt Pocock's [grill-me](https://github.com/mattpocock/skills/tree/main/skills/productivity/grill-me) and [grilling](https://github.com/mattpocock/skills/tree/main/skills/productivity/grilling): investigate facts independently and ask the human to settle decisions. BSI uses one refactor at a time and a shorter approval path for obvious cleanup; those skills are not runtime dependencies.
