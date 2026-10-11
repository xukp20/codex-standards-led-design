# Standards maintenance

Read when initializing the library or turning feedback into a proposed rule
change. Keep the library useful for later decisions, not a transcript of every
conversation.

## Initialize from existing material

Inspect existing principles, explicit user decisions, relevant conversation
records, and deferred problem reports. Extract the requirements without losing
their scope, conditions, or rationale. Preserve original evidence according to
project rules and link to it rather than replacing it with a summary.

Separate already confirmed requirements from inferred recommendations. A
failure report such as "this tool exposed too much internal state" supports
investigation; its suggested remedy is not automatically approved. Consolidate
matching confirmed rules, surface conflicts, and present inferred additions
for confirmation. Do not claim complete coverage after sampling a few files.

Organize by the subject the rule constrains, not by where the feedback arose.
For example, feedback about a cache query may belong under Agent interfaces
if it also governs search, dependency queries, and inspection tools. Keep a
cache-specific eviction choice in the cache design.

## Write only the detail that makes the rule usable

Usually a readable heading and a short paragraph suffice. Include:

- The requirement.
- Its applicable scope and any important boundary.
- A reason or example when needed to prevent misapplication.
- A reference to its user or evidence basis when available.

Do not invent numeric limits, absolute prohibitions, or universal exceptions.
Use the user's actual strength of requirement. If two rules compete, expose
the tradeoff instead of silently changing priority. Project-local requirements
do not become cross-project defaults without explicit intent.

## Example: readable tool references

User feedback: "For this cache tool, do not make the Agent provide a random
record ID. Let it use the repository and declaration names."

Possible proposal:

> Agent-facing lookup parameters should use readable business references with
> enough context to resolve ambiguity. Internal storage may retain stable IDs.
> Ambiguous names should return readable candidates rather than silently
> choosing an object.

Present the proposed wider scope before accepting it. Do not infer "all IDs
are forbidden" or "all tool arguments must be flat." A small meaningful
structure may be clearer than many unrelated parameters.

If an accepted rule already requires readable business references, fix the
cache design under that rule. No new rule is necessary.

## Example: sufficient but focused results

User feedback: "The response is enormous, but it still omits why the check
failed."

The reusable requirement may be that results include information needed for
the current action, particularly actionable failures, while unrelated details
are available on demand. Do not translate this into "always return fewer
fields" or remove evidence merely to reduce output size. The exact summary
fields and expansion operation belong in the concrete tool design.

## Apply confirmed changes

Update the existing authoritative paragraph where possible. Add a new topic
only when it has a genuinely distinct responsibility. Keep history where the
project already keeps it; avoid accumulating contradictory rules in the active
library. Update navigation and necessary cross-references.

Record the affected design areas with a short note or link when follow-up is
needed. Confirmation of a new standard does not establish that older designs
have been audited or repaired. If the user approved only the standard, present
concrete design repairs before changing the accepted plans. Do not repeatedly
ask for approval already granted for the same changes.
