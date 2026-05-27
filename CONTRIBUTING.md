# Contributing

Thanks for contributing to **awesome-multimodal-agent-benchmarks**. Please follow the rules below so the list stays high-signal.

## Inclusion criteria (must satisfy both)

1. **Agentic** — multi-step planning, tool use, environment interaction, or long-horizon reasoning. Single-turn QA does not qualify.
2. **Multimodal** — inputs and/or outputs include modalities beyond plain text (image, video, audio, GUI screenshot, 3D, sensor, etc.).

If a benchmark is borderline (e.g., agentic but text-only, or multimodal but static QA), open an issue first to discuss.

## Pull request checklist

- [ ] Benchmark has a public paper (arXiv, conference, or journal) **or** a public code/data release.
- [ ] Entry is placed in the most specific section. If no section fits, propose a new one in the PR description.
- [ ] Entry follows the template below (≤120 characters total).
- [ ] Section order is preserved (newest first by initial release year).
- [ ] You added the benchmark to the comparison table **only if** it is among the most-cited / most-used (keep table ≤15 rows).
- [ ] Links are verified to be live; arXiv links point to abstract page, not a specific PDF version.
- [ ] No emojis, no marketing language, no SEO filler.
- [ ] Description states **what the benchmark evaluates**, not who built it.

## Entry template

```markdown
- [Benchmark Name](https://link.to.paper.or.repo) — One-line description of what it evaluates and any defining feature. `paper` `code` `leaderboard`
```

Suffix tags (use only those that apply):

- `paper` — link is the paper / arXiv page
- `code` — public code or environment release
- `leaderboard` — public, maintained leaderboard
- `dataset` — large standalone dataset release

## Removing or updating entries

Stale links, retracted papers, or benchmarks superseded by a newer official version should be updated in-place (preserve the original arXiv ID where possible) or moved to the *Related* section with a one-line note.

## Style

- One line per entry, ≤120 characters including markdown.
- Sort within sections by **year, newest first**. Break ties by alphabetical order.
- US English. No first-person voice.
- Don't editorialize ("the best benchmark for X" → "evaluates X").
