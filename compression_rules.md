# Compression Rules for the Minimized Ladder Schema

Use these rules whenever encoding a new document into the minimized ladder format.

## L1 — Structural Skeleton

Store only:
- section order
- relative size
- observable structure
- tone markers
- rhetorical movement

Do not store:
- detailed explanations
- inferred philosophy

## L2 — Section Function Map

Store only:
- what each section does
- major signals
- transitions

Do not store:
- local examples
- long motif lists
- atomic details already better suited for the sidecar

## L3 — Governing Principles

Store only:
- stable thesis
- deep rules
- author stance
- reconstruction bias

Do not store:
- section-local detail
- concrete UI examples
- long enumerations of banned motifs

## S1 — Atomic Inventory

Store:
- local motifs
- repeated tokens
- concrete examples
- detail clusters

Do not let S1 become:
- a second copy of the document
- a prose summary
- an unstructured dump of every sentence

## General Rule

The ladder should compress upward cleanly:

- L1 preserves **shape**
- L2 preserves **rhetorical function**
- L3 preserves **governing intent**
- S1 preserves **recoverable detail**

If a piece of information can live at a higher layer without losing usefulness, prefer the higher layer.

If a piece of information is too local, too concrete, or too example-specific for L1/L2/L3, place it in S1.