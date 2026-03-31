# Ladder Workflow

## Purpose

This workflow is for compressing a source document into aligned abstraction layers and then reconstructing it later with minimal drift.

## Steps

1. Encode the source into the abstraction ladder schema.
2. Validate that the ladder answers the core reconstruction questions.
3. If token pressure is high, apply the token-saving variant.
4. Save the artifact using the recommended file set.
5. Reconstruct the document using the reconstruction prompt.
6. Compare reconstruction against source.
7. Refine the ladder, not just the prompt, if recovery is weak.

## Validation questions

### Canonical top-level shape
Can this answer: what is the overall document frame and top-level organization?

### L1
Can this answer: what did the document look like?

### L2
Can this answer: what was each section doing?

### L3
Can this answer: why was this written, and what author stance shaped it?

### S1
Can this answer: what exact local details must not be lost?

### S2
Can this answer: what reconstruction constraints reduce drift?

## Failure modes

- Canonical shape too weak -> reconstruction loses the overall frame
- L1 too vague -> reconstruction loses structure
- L2 too thin -> reconstruction loses section purpose
- L3 too polished -> reconstruction loses author signal
- S1 too large -> sidecar becomes a duplicate summary
- S1 too weak -> reconstruction loses specificity
- S2 omitted when needed -> reconstruction drifts even when core ladder is correct

## Correction rule

Do not respond to weak reconstruction by only changing the prompt.
First inspect whether the ladder itself failed to preserve the needed information.