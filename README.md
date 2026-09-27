# simple-data-science

A lightweight agent skill for writing clear, simple, and reproducible data science code in Python, pandas, NumPy, and scikit-learn.

A small collection starting with one self-contained skill: **readable-data-science**.

It guides an agent to write and simplify Python, pandas, NumPy, notebooks, and scikit-learn code that an analyst can follow, without unnecessary frameworks or abstractions. It preserves analytical behavior during cleanup and distinguishes statistical fixes from refactoring.

It combines code simplification with a compact exploratory-analysis workflow adapted from K-Dense's Scientific Agent Skills. The result remains one self-contained skill with no bundled executables or required third-party skills.

## Use in Codex

Ask Codex to install `skills/readable-data-science` from this repository using its skill installer. You can also copy the entire `skills/readable-data-science` directory into your personal skills directory. Keep the included LICENSE with the skill.

```text
Use $skill-installer to install skills/readable-data-science from
https://github.com/BarryNiu-Wahaha/simple-data-science
```

Then invoke it explicitly:

```text
Use $readable-data-science to write or simplify this analysis.
```

To request its use across projects, append this preference to your global `~/.codex/AGENTS.md` without replacing existing instructions:

```markdown
For tasks that write, edit, or review Python data science code,
use the readable-data-science skill when available.
```

Start a new Codex session after changing global instructions. Project instructions and explicit task requirements still apply.

## Customize

Edit [SKILL.md](skills/readable-data-science/SKILL.md). Keep its description focused on when it should activate. Add a small number of concrete preferences or examples based on actual results; avoid accumulating rules that complicate simple analyses.

Commit and push your changes, then update the installed copy. A local installation does not automatically follow GitHub changes. Keep only one installed copy with this skill name.

## Source and license

This combines condensed guidance from two MIT-licensed sources, reviewed on 2026-09-26:

| Source | Contribution |
| --- | --- |
| Addy Osmani's [code-simplification](https://github.com/addyosmani/agent-skills/tree/main/skills/code-simplification) | Readability and behavior-preserving cleanup |
| K-Dense Inc.'s [exploratory-data-analysis v1.2](https://github.com/K-Dense-AI/scientific-agent-skills/tree/main/skills/exploratory-data-analysis) | Lightweight EDA reasoning |

K-Dense's [Scientific Agent Skills repository](https://github.com/K-Dense-AI/scientific-agent-skills) displayed approximately 46,700 GitHub stars when checked on 2026-09-26. This is the collection's star count, not a rating of the individual skill. Selection also considered relevance, explicit analytical guidance, and its MIT license.

This repository does not bundle either full collection. K-Dense's scripts, specialized file inspectors, dependency pins, and report scaffolding are omitted to keep the adaptation small. There is no runtime dependency on either upstream skill.

Retained principles: preserve behavior, follow project conventions, prefer clarity, avoid unnecessary abstractions, scope changes, and verify results. Added guidance covers data transformations, notebooks, reproducibility, and evaluation leakage. Frontend examples and heavyweight process requirements were removed.

Addy Osmani's original skill credits [Anthropic's Code Simplifier](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-simplifier) as inspiration. Both upstream copyright notices and the MIT permission notice are preserved in [LICENSE](LICENSE) and within the installable skill folder.
