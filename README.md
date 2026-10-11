<h1 align="center">Standards-led Design for Codex</h1>

<p align="center">
  <strong>Develop concrete designs, learn from feedback, and keep project standards useful.</strong>
</p>

<p align="center">
  <a href="skills/standards-led-design/SKILL.md">
    <img alt="Codex Skill" src="https://img.shields.io/badge/Codex-Skill-2563eb?style=flat-square">
  </a>
  <img alt="Focus" src="https://img.shields.io/badge/focus-design%20and%20standards-0f8f88?style=flat-square">
</p>

<p align="center">
  <a href="#why">Why</a> &middot;
  <a href="#use">Use</a> &middot;
  <a href="#workflow">Workflow</a> &middot;
  <a href="#install">Install</a> &middot;
  <a href="skills/standards-led-design/SKILL.md">Skill Reference</a>
</p>

`standards-led-design` helps Codex develop designs under agreed project
requirements, review them, and propose reusable lessons from user feedback.
The user concentrates on important requirements and consequential decisions
rather than specifying every design detail again.

The skill is a documentation and collaboration workflow. It does not prescribe
an architecture, impose a universal engineering rulebook, or install an agent
runtime. Project-specific standards stay in the project.

## Why

Long design conversations often mix three things:

- Questions still requiring a decision.
- Reusable requirements that should guide many decisions.
- Concrete designs made under those requirements.

When these are mixed, the same feedback repeats, local preferences become
universal rules, and old designs quietly drift from newer requirements. This
skill keeps them distinct while connecting design review, feedback, and later
audits.

## Use

```text
Use $standards-led-design to organize our open design questions and develop
this module against our agreed standards. Keep standards separate from the
concrete design and show any proposed standards changes for confirmation.
```

```text
Review this design with an authorized independent reviewer. Incorporate
supported findings and present the revised proposal, unresolved tradeoffs,
and any reusable lessons that need my confirmation.
```

```text
Our tool-interface standards have changed. Audit the affected older designs,
identify concrete mismatches, and propose repairs before updating accepted plans.
```

Existing explicit authorization remains valid: the workflow does not require
repeated approval for the same edits or ordinary decisions within an accepted
scope. A request to discuss a design does not authorize implementation.

## Workflow

| Step | Result |
| --- | --- |
| Establish the basis | Relevant standards, evidence, accepted decisions, and open questions |
| Develop the candidate | A concrete proposal with necessary mechanisms and material tradeoffs |
| Review and iterate | Findings checked against requirements, with decisions owned by the lead |
| Learn from feedback | A design correction plus any proposed clarification or reusable requirement |
| Maintain the records | Confirmed standards and accepted designs updated in their own locations |
| Audit at boundaries | A scoped check of earlier designs when requirements change or modules finish |

Not every correction needs a new rule. It may be a missed existing requirement,
a clarification, a local choice, or a conflict that needs resolution. The skill
asks Codex to explain that distinction instead of continuously growing the
standards library.

Independent review is used when useful and authorized. Model and backend
selection follow the user's current settings. The optional
[Directed Delegation](https://github.com/xukp20/codex-directed-delegation)
companion handles assignment and routing when available; it is not required
for local design work. This skill does not launch or configure agents itself.

## Project documents

Keep standards and concrete designs separately discoverable. A shared area is
a useful starting point, not a required layout:

```text
design-area/
├── index.md       # Navigation and open topics
├── standards/     # Reusable requirements with their scope and basis
└── design/        # Concrete, accepted designs
```

Existing project conventions take precedence. Separate documents can suffice.
Use references to original decisions and evidence; do not replace required
source records with lossy summaries. No mandatory IDs, version registry,
compliance matrix, or new process database is needed.

## Install

```bash
git clone https://github.com/xukp20/codex-standards-led-design.git
cd codex-standards-led-design
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
ln -s "$PWD/skills/standards-led-design" \
  "${CODEX_HOME:-$HOME/.codex}/skills/standards-led-design"
```

Inspect an existing destination before replacing it. Reload Codex if discovery
does not refresh. A linked checkout can be updated with `git pull --ff-only`.
There are no runtime dependencies or executable helpers. Installation does not
change global instructions, model settings, project documents, or permissions.

## Repository layout

```text
codex-standards-led-design/
├── README.md
└── skills/
    └── standards-led-design/
        ├── SKILL.md
        ├── agents/openai.yaml
        └── references/
            ├── standards-maintenance.md
            └── design-review.md
```

Only the directory under `skills/` is installed. The root README explains the
package; the skill contains the reusable working instructions.

## Validation

Run the validator from an installed `skill-creator` skill:

```bash
python /path/to/skill-creator/scripts/quick_validate.py \
  skills/standards-led-design
```

Also check local links and UI metadata. Behavioral evaluation should use small
realistic scenarios: a missed existing standard, a local exception, a proposed
generalization, an old-design mismatch, and a discussion-only request. Inspect
what the agent actually proposes or changes. Syntax validation alone does not
establish good judgment or compliance on future tasks.

## Boundaries

- User confirmation governs proposed new standards and revisions to accepted
  designs; existing authorization need not be requested again.
- Do not silently generalize a local preference, convert a deferred remedy into
  an approved rule, or weaken standards to make a candidate pass review.
- Keep project standards in the project; do not copy private discussions into
  the shared skill or alter global instructions as a side effect.
- Review claims apply only to inspected scope. Agent agreement is not evidence
  of implementation correctness or user acceptance.
- Use existing document organization and update topics in place. Create a new
  document only for a distinct need.
