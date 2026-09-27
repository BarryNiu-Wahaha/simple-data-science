# My Agent Skills

A small collection starting with one self-contained skill: **readable-data-science**.

It guides an agent to write and simplify Python, pandas, NumPy, notebooks, and scikit-learn code that an analyst can follow, without unnecessary frameworks or abstractions. It preserves analytical behavior during cleanup and distinguishes statistical fixes from refactoring.

## Use in Codex

Ask Codex to install `skills/readable-data-science` from this repository using its skill installer. You can also copy the entire `skills/readable-data-science` directory into your personal skills directory. Keep the included LICENSE with the skill.

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

This is a condensed adaptation of Addy Osmani's [code-simplification skill](https://github.com/addyosmani/agent-skills/tree/main/skills/code-simplification), reviewed on 2026-09-26. It is not a fork of the full collection and has no runtime dependency on the original skill.

Retained principles: preserve behavior, follow project conventions, prefer clarity, avoid unnecessary abstractions, scope changes, and verify results. Added guidance covers data transformations, notebooks, reproducibility, and evaluation leakage. Frontend examples and heavyweight process requirements were removed.

The original skill credits [Anthropic's Code Simplifier](https://github.com/anthropics/claude-plugins-official/tree/main/plugins/code-simplifier) as inspiration. The original MIT copyright and permission notice are preserved in [LICENSE](LICENSE) and within the installable skill folder.
