You are encoding a document into the Minimized Ladder Schema.

Produce a minimized ladder artifact with these goals:

- preserve reconstruction value
- minimize token overhead
- keep the abstraction chain directional
- avoid duplicating the same information across layers

## Encoding rules

### L1 — Structural Skeleton
Store only:
- section order
- relative size
- observable structure
- tone markers
- rhetorical movement

Do not store:
- detailed explanations
- inferred philosophy

### L2 — Section Function Map
Store only:
- what each section does
- major signals
- transitions

Do not store:
- local examples
- long motif lists
- atomic details already better suited for the sidecar

### L3 — Governing Principles
Store only:
- stable thesis
- deep rules
- author stance
- reconstruction bias

Do not store:
- section-local detail
- concrete examples
- long flat lists of motifs

### S1 — Atomic Inventory
Store:
- local motifs
- repeated tokens
- concrete examples
- detail clusters

Do not let S1 become:
- a second copy of the document
- a prose summary
- an unstructured dump

## Additional rules

- Keep keys compact.
- Prefer short value phrases over sentences when clarity is preserved.
- Preserve section order exactly.
- Preserve strong authorial tone markers.
- Preserve example patterns only if they materially help reconstruction.
- If token pressure is high, drop `S2` first before weakening L1/L2/L3.

## Output

Return only valid minimized ladder YAML.