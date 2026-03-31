# Recommended File Set for Ladder-Based Document Workflows

Use the following file pattern when working with abstraction ladders and reconstructions.

This toolkit directory contains the reusable shared schemas, prompts, and workflow documents. A specific source document should usually live in its own working set built around a stable `doc_id`.

---

## Per-document working file set

### Use these for an individual encoded document:

```code
<doc_id>.source.md
<doc_id>.ladder.yaml
<doc_id>.ladder.minimized.yaml
<doc_id>.reconstructed.md
<doc_id>.reconstruction_prompt.md
<doc_id>.notes.md
<doc_id>.diff.md
```

## Roles

### The original source document, if available.

```code
<doc_id>.source.md
```

### A standard-schema ladder payload using the repository-level schema files.

```code
<doc_id>.ladder.yaml
```

### A token-efficient ladder payload using the files in schema/minimized/.

```code
<doc_id>.ladder.minimized.yaml
```

### A reconstructed document generated from one of the ladder representations.

```code
<doc_id>.reconstructed.md
```

### The exact reconstruction prompt used for a particular reversal attempt. 

```code
<doc_id>.reconstruction_prompt.md
```

### Used for scratch notes and manual reconstruction guidance.

```code
<doc_id>.notes.md
```

### Tracks the delta between the original source document and the reconstructed output.

```code
<doc_id>.diff.md
```