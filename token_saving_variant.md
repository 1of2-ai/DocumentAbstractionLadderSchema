# Token-Saving Variant for Minimized Ladder Encoding

Use this when context is tight and the full minimized schema is too expensive.

## Rule

Drop `S2` entirely.

Compress `L2.sf` so it contains only one entry per top-level section, focusing only on the core keys (`id`, `fn`) and dropping optional tracking like `dp` or `ln` unless strictly required.

Do not store subsection-level rhetorical detail unless it is critical to reconstruction.

## Minimal L2 Pattern

```yaml
L2:
  sf:
    - {id: s1, fn: [diagnose bad default UI, prescribe normal UI, ban patterns, set color rule]}
    - {id: s2, fn: [dark palette appendix]}
    - {id: s3, fn: [light palette appendix]}
```