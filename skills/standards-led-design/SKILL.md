---
name: standards-led-design
description: "Develop and review designs against agreed project standards, turn user feedback into proposed reusable guidance, and audit earlier designs when standards evolve. Use for iterative architecture or design discussions and standards-library maintenance; keep concrete designs separate from general requirements."
---

# Standards-led Design

Help the user establish reusable requirements, then do the design work within
those requirements. The user reviews consequential proposals rather than
having to specify every implementation choice. Maintain two connected loops:

- Design: frame the question, apply agreed standards, develop and review a
  candidate, then present it for acceptance.
- Standards: understand feedback, propose any reusable correction, obtain
  confirmation, then apply it to relevant current and earlier designs.

This Skill defines the workflow, not a universal engineering rulebook. Keep
project requirements in the project. Do not impose a model, document tree,
implementation framework, or approval ceremony for routine authorized work.

## Establish the current basis

Locate the relevant standards, accepted design, open questions, and primary
evidence. Use existing project navigation before creating new documents.
Distinguish confirmed requirements from observations, proposed solutions,
and hypotheses. Deferred issues are evidence of problems, not automatically
approved remedies or general standards.

When beginning a substantial design effort, identify the major questions:
current failures to address, distinctive mechanisms to examine, decisions
needed, and dependencies between those decisions. Keep this an actionable
topic list, not an exhaustive inventory of possible abstractions. Reuse and
update that list as topics are resolved; do not restart it each turn.

Make material uncertainty visible. Resolve ordinary choices using the agreed
basis; ask the user only when missing intent or a consequential tradeoff
cannot be resolved from it. Do not send ordinary design work back to the user
as a long questionnaire.

## Develop a concrete candidate

Read the standards relevant to the topic. Explain the proposed behavior,
responsibilities, necessary data or mechanisms, and important failure cases
at the level of detail the current discussion needs. Show material tradeoffs
and why the selected approach fits the requirements. Distinguish verified
implementation facts from design assumptions and proposals.

Check for missing requirements, duplicated authority, unnecessary concepts,
and maintenance work that the proposed solution introduces. Apply project
standards with their actual scope; do not turn an example into a universal
ban or add speculative features just to make the design more general.

Keep discussion drafts distinguishable from accepted design. Design discussion
does not authorize implementation. Once a proposal is accepted for recording,
update the existing topic in place rather than creating another competing
"latest" design. Preserve the evidence and history required by the project.

## Review and iterate

For substantial designs, use independent review when authorized and useful.
The reviewer receives the candidate, applicable standards, user constraints,
and primary evidence without being told what verdict to reach. Read
[design review](references/design-review.md) for reviewer guidance and audits.

The lead resolves findings and owns the revised proposal. Agent agreement is
not user acceptance. Do not require a minimum number of findings, a fixed
number of rounds, or repeated reviews with no new evidence. Bring unresolved
user-owned tradeoffs back with concrete options.

If `directed-delegation` is available, use it for authorized delegation and
honor the current model and routing choices. This Skill does not configure
agents or authorize new sidebar sessions. Review can also be performed by the
lead; accurately state when it was not independent.

## Learn from feedback without accumulating rules

Respond to a correction by revising the design and classifying the lesson:

| Finding | Action |
| --- | --- |
| An existing standard was missed | Fix the design; identify the missed standard |
| A standard is ambiguous or poorly scoped | Propose a clarification or narrower scope |
| A reusable requirement is newly identified | Propose a new standard with its scope and basis |
| The choice is specific to this design | Keep it in the design, not the standards library |
| The feedback conflicts with an existing standard | Explain the conflict; propose replacing or qualifying the old rule |

Show the design adjustment and any proposed standards change together. A
compact response can say: what changes in the design, what requirement was
understood, how the library should change, and which earlier designs may be
affected. If the library already covers the lesson, say so instead of adding
another rule. Read [standards maintenance](references/standards-maintenance.md)
when extracting, revising, or organizing standards.

Apply explicit user corrections to the current proposal immediately. Do not
silently promote an inferred generalization into an accepted standard. Record
new or changed standards after user confirmation; existing explicit approval
or an authorized batch update does not need to be requested again.

## Keep records separate and current

Keep standards and concrete designs independently discoverable, preferably
under a shared project documentation area when that fits existing conventions.
Separate subdirectories are useful, but separate clearly identified documents
also work. Keep open topics in the existing index or planning document.

Maintain one authoritative current statement per standard and design topic.
Use readable headings and links; no mandatory IDs, state machine, version
registry, or complete compliance matrix is needed. Keep accepted rules,
pending proposals, and historical rationale visibly distinct. Do not copy
project-specific standards into this installed Skill or silently alter global
instructions.

## Audit at meaningful boundaries

After a material standards change, identify the potentially affected designs.
At a module boundary or agreed milestone, inspect that scope against the
current standards. Run a full audit when requested or when the change really
crosses the whole design; do not reread every document after every correction.

Report the inspected scope, concrete mismatches, consequences, and proposed
repairs. Distinguish uninspected work from compliant work. Update accepted
designs after the user approves the proposed changes, reusing existing
approval where it already covers them. Track deferred repairs in the project's
existing place so identifying a mismatch is not mistaken for fixing it.
