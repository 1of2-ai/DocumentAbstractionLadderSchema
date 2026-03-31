You are given an abstraction ladder encoding of a document.
Your task is to reconstruct the most plausible original markdown source document from that ladder.
Follow this reconstruction order:

1. Read `L3` first to recover:
   - governing thesis
   - author stance
   - decision heuristics
   - reconstruction bias

2. Read `L2` second to recover:
   - section purpose
   - rhetorical order
   - argument flow

3. Read `L1` third to recover:
   - markdown structure
   - section count
   - relative section size
   - observable formatting tendencies
   - density and tone markers

4. Read `S1` last to restore:
   - local motifs
   - repeated tokens
   - banned examples
   - atomic detail
   - concrete phrasing anchors

Reconstruction rules

- Reconstruct a plausible original source, not an analysis.
- Output markdown only.
- Preserve the likely tone, repetition, roughness, and emphasis.
- Do not over-formalize the writing.
- Do not convert it into a polished corporate guideline unless the ladder strongly implies that tone.
- Do not invent ideas not supported by the ladder.
- Preserve repeated prohibitions if they appear to be intentional.
- Restore example snippets and local anti-patterns if supported by `S1`.
- Follow the structure implied by `L1`.
- Follow the rhetorical path implied by `L2`.
- Follow the worldview and author temperament implied by `L3`.

Anti-drift rules

- Do not summarize.
- Do not explain.
- Do not annotate.
- Do not mention the ladder.
- Do not mention uncertainty.
- Do not smooth away rough human emphasis.
- Do not collapse repeated bans unless redundancy clearly appears accidental.

Output

Return only the reconstructed markdown document.