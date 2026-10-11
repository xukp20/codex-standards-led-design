# Design review and later audits

Read for a substantial candidate review or an audit of existing designs after
standards evolve. Scale the review to the question; this is not a mandatory
form for every discussion.

## Review a candidate

Give the reviewer the design, applicable standards, original requirements,
relevant evidence, and a bounded scope. Include accepted constraints, but do
not prime the reviewer with the author's preferred verdict. Ask the reviewer
to distinguish:

- Violations of confirmed requirements.
- Gaps that prevent the intended behavior or leave a necessary decision open.
- Optional simplifications or alternatives.
- Questions that cannot be settled from the available evidence.

For a substantive finding, identify the affected design, applicable requirement,
concrete trigger or example, and consequence. A different architectural taste
alone is not a defect. Check normal behavior and meaningful failure cases;
do not invent unsupported scenarios to justify more infrastructure.

Review whether the design introduces duplicate authoritative data, unnecessary
states or layers, unclear responsibility, or recurring synchronization work.
These are questions to evaluate against the actual project requirements, not
universal bans on caches, state, or abstraction.

The lead assesses the evidence and revises the proposal. Resolve routine
findings directly; present consequential unresolved choices to the user.
Stop iterating when material findings are addressed or further progress
requires a user decision or new evidence. Do not claim that two agents agreeing
makes a design correct or accepted.

## Audit earlier designs

Select scope from the changed requirement and the relevant module boundaries.
A tool-output rule may affect tool contracts and views, without affecting the
scheduler. A data-ownership rule may cross several modules. Explain the chosen
scope and note known areas left for later inspection.

For each actionable mismatch, provide:

| Location | Standard | Mismatch and consequence | Proposed repair |
| --- | --- | --- | --- |
| A concrete design section | Current requirement or link | What no longer fits and why it matters | The smallest adequate change |

Use prose instead of a table when there are only one or two findings. Do not
require a full standards-by-document matrix. Separate actual mismatches from
missing evidence, deferred work, and optional improvements.

A design accepted under earlier requirements is not necessarily a prior error.
Explain what changed. Obtain approval for repairs to accepted designs unless
existing authorization already covers those repairs. Then update the canonical
sections and check related references for contradictions. Record uncompleted
repairs in the existing project backlog.

## Report proportionate evidence

A concise delivery states the resulting design, important tradeoffs, review
coverage, and remaining questions. State whether review was independent and
what was actually inspected. A design-only review is not evidence of working
code, performance, or successful tests; identify experiments separately when
those claims matter.
