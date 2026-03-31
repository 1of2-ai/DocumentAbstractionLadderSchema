# Document Abstraction Ladder Toolkit

This directory contains a small toolkit for compressing documents into aligned abstraction layers and reconstructing plausible source documents from those layers.

The system is designed to preserve four different kinds of information:

- **shape** — what the document looked like structurally
- **rhetorical function** — what each section was doing
- **governing intent** — the deeper thesis, rules, and author stance
- **atomic detail** — local motifs, repeated patterns, examples, and constraints

The goal is not perfect inversion. The goal is to make reconstruction more reliable, more directional, and less prone to tone/structure drift.

---

## Core idea

A source document is encoded into a ladder with aligned layers:

- **Canonical top-level shape**  
  Shared top-level structure and overall schema framing.

- **Level 1 — Structural Skeleton**  
  Preserves layout, section order, relative lengths, formatting tendencies, and observable rhetoric.

- **Level 2 — Section Function Map**  
  Preserves what each section is doing and how the argument moves.

- **Level 3 — Governing Principles**  
  Preserves the deepest stable thesis, heuristics, and authorial stance.

- **Sidecar 1 — Atomic Inventory**  
  Detail bank for local motifs, repeated tokens, examples, and fine-grained constraints.

- **Sidecar 2 — Reconstruction Hints** *(optional)*  
  Anti-drift rules and explicit reverse-engineering constraints.

These layers are meant to work together. Canonical shape defines the overall frame, Level 1 gives shape, Level 2 gives rhetorical flow, Level 3 gives intent, and the sidecars restore local texture and reconstruction guidance.

---

## Directory contents

### Prompt and workflow documents

#### `minimized_ladder_encoding_prompt.md`
Prompt for encoding a source document into the minimized ladder schema.

Use this when generating a new minimized ladder from raw source text.

#### `token_saving_encoding_prompt.md`
Prompt for encoding with the token-saving variant.

Use this when context is limited and a lighter representation is needed.

#### `reconstruction_prompt.md`
Prompt for reconstructing a plausible original source document from a ladder artifact.

Use this after a ladder has already been created.

#### `compression_rules.md`
Rules for what belongs in each layer and what should be omitted.

Use this when encoding a document into the ladder so the abstraction chain stays clean.

#### `token_saving_variant.md`
Reduced ladder strategy for tight token budgets.

Use this when preserving the most important reconstruction signal with less overhead.

#### `recommended_file_set.md`
Suggested file naming and organization for ladder-based workflows.

Use this when setting up a working directory for a specific document.

#### `ladder_workflow.md`
Operational workflow for encoding, validating, reconstructing, and refining.

Use this as the process guide for the whole system.

### Schema files

#### `schema/standard/schema.yaml`
Primary full schema definition.

#### `schema/standard/schema.example.yaml`
Example full-schema payload.

#### `schema/standard/canonical_top_level_shape.yaml`
Top-level canonical shape definition for the ladder system.

#### `schema/standard/level_1.yaml`
Level 1 schema or payload for the structural skeleton layer.

#### `schema/standard/level_2.yaml`
Level 2 schema or payload for the section function map layer.

#### `schema/standard/level_3.yaml`
Level 3 schema or payload for the governing principles layer.

#### `schema/standard/sidecar_1.yaml`
Sidecar 1 schema or payload for atomic detail recovery.

#### `schema/standard/sidecar_2.yaml`
Sidecar 2 schema or payload for reconstruction hints and anti-drift rules.

### Minimized schema files

#### `schema/minimized/schema.yaml`
Minimized schema definition for token-efficient encoding.

#### `schema/minimized/schema.example.yaml`
Example minimized-schema payload.

#### `schema/minimized/keys.yaml`
Short-key mapping used by the minimized schema.

#### `schema/minimized/conventions.yaml`
Minimized encoding conventions, enums, and storage rules.

---

## Repository layout

```text
.
├── compression_rules.md
├── ladder_workflow.md
├── minimized_ladder_encoding_prompt.md
├── README.md
├── recommended_file_set.md
├── reconstruction_prompt.md
├── schema
│   ├── minimized
│   │   ├── conventions.yaml
│   │   ├── keys.yaml
│   │   ├── schema.example.yaml
│   │   └── schema.yaml
│   └── standard
│       ├── canonical_top_level_shape.yaml
│       ├── level_1.yaml
│       ├── level_2.yaml
│       ├── level_3.yaml
│       ├── schema.example.yaml
│       ├── schema.yaml
│       ├── sidecar_1.yaml
│       └── sidecar_2.yaml
├── token_saving_encoding_prompt.md
└── token_saving_variant.md
```

---

## Recommended working file layout for a specific document

A typical working set for an encoded document looks like this:

```code
<doc_id>.source.md
<doc_id>.ladder.yaml
<doc_id>.ladder.minimized.yaml
<doc_id>.reconstructed.md
<doc_id>.reconstruction_prompt.md
```

Optional additions:

```code
<doc_id>.notes.md
<doc_id>.diff.md
```

Use the repository-level files in this directory as the toolkit, and use `<doc_id>.*` files as per-document working artifacts.

---

## Typical workflow

1. Start with the source document.
2. Encode it into either the standard schema or the minimized schema.
3. Validate the ladder:
   - canonical top-level shape captures the shared frame
   - Level 1 captures shape
   - Level 2 captures rhetorical function
   - Level 3 captures governing principles
   - Sidecar 1 captures local recoverable detail
   - Sidecar 2 captures reconstruction hints when needed
4. Reconstruct a plausible source document from the ladder.
5. Compare reconstruction to source.
6. Refine the ladder and/or prompt if needed.

---

## Validation questions

### Canonical top-level shape
Can this answer: **What is the overall document frame and top-level organization?**

### Level 1
Can this answer: **What did the document look like?**

### Level 2
Can this answer: **What was each section doing?**

### Level 3
Can this answer: **Why was this written, and what author stance shaped it?**

### Sidecar 1
Can this answer: **What exact local details must not be lost?**

### Sidecar 2
Can this answer: **What reconstruction constraints reduce drift?**

If any of those fail, the ladder is under-specified.

---

## Failure modes

Common problems:

- **canonical top-level shape too weak**  
  Reconstruction loses the overall frame.

- **Level 1 too vague**  
  Reconstruction loses structure.

- **Level 2 too thin**  
  Reconstruction loses section purpose.

- **Level 3 too polished**  
  Reconstruction loses author signal.

- **Sidecar 1 too bloated**  
  The sidecar becomes a duplicate summary instead of a detail bank.

- **Sidecar 1 too weak**  
  Reconstruction loses specificity and local texture.

- **Sidecar 2 omitted when needed**  
  Reconstruction drifts even when the core ladder is correct.

Correction rule:

> Do not respond to weak reconstruction by only changing the prompt.  
> First check whether the ladder itself failed to preserve the needed information.

---

## Design philosophy

This toolkit is built on a simple principle:

> Reconstruction works better when meaning, structure, and author signal are preserved in separate but aligned forms.

A normal summary tends to compress everything into one blurred output. The ladder separates those signals so reconstruction has a stronger directional basis.

This is especially useful for:
- style manifests
- design specs
- instruction files
- strong-voice operational documents
- documents where tone and structure matter as much as raw content

---

## When to use the minimized/token-saving variant

Use the minimized variant when:
- context is limited
- broad structural recovery is still needed
- some section-level nuance can be sacrificed
- thesis, shape, and local detail need to be preserved efficiently

In that mode:
- shrink Level 2 first
- drop Sidecar 2 first
- preserve canonical shape, Level 1, Level 3, and the most valuable parts of Sidecar 1

---

## Suggested usage pattern

- Use `minimized_ladder_encoding_prompt.md` to create minimized artifacts.
- Use `compression_rules.md` to sanity-check the encoding.
- Use `reconstruction_prompt.md` to regenerate a plausible source.
- Use `ladder_workflow.md` to iterate if results drift.
- Use `recommended_file_set.md` to keep per-document outputs consistent.

---

## Status

This directory is a working toolkit, not a final standard.

It is meant to be:
- reusable
- minimized
- inspectable
- improvable

As you use it, refine the schema files and the prompts together rather than treating either one as fixed.
