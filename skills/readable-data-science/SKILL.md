---
name: readable-data-science
description: Use when writing, reviewing, or simplifying Python data science code, including pandas, NumPy, Jupyter notebooks, and scikit-learn workflows, especially when code is overengineered or hard for an analyst to follow.
---

# Readable Data Science

Write code a junior data analyst can follow. Optimize for comprehension, not minimum line count. Adapted from Addy Osmani's code-simplification skill; see [LICENSE](LICENSE).

## Working approach

1. Read the requested code and project conventions. Identify whether the task is exploratory analysis, reusable analysis code, or a production pipeline. Match its complexity to that context.
2. For new code, choose the simplest approach that meets the requirements. For cleanup, understand inputs, outputs, side effects, and edge cases before changing anything.
3. Keep edits within the requested scope. Preserve behavior during refactoring; report statistical bugs separately instead of silently changing the analysis.
4. Verify relevant results using existing checks or a small representative comparison. Explain what changed and any checks you could not run.

## Python and data transformations

- Prefer descriptive names, straightforward functions, and early returns over deeply nested logic. Keep familiar scientific notation when it makes formulas easier to understand.
- Introduce classes, wrappers, configuration layers, and helper functions only when they clarify an actual responsibility or useful reuse. Do not split readable code into a maze of tiny functions.
- Prefer standard pandas and NumPy operations. Keep efficient vectorized operations when they are understandable; do not replace them with slow row loops merely to look simpler.
- Break dense method chains into named intermediate steps when that makes the transformation easier to inspect. Short, coherent chains are fine.
- Make join keys, filtering conditions, aggregation intent, and units clear. Avoid unexplained positional indexing and unnecessary conversions between arrays and DataFrames.
- Preserve row order, index alignment, duplicate handling, groupby defaults, missing values, dtypes, and mutation behavior during cleanup. Do not add imputation, dropping, deduplication, or coercion without a task-based reason.
- Use comments for statistical assumptions and non-obvious choices. Add type hints and docstrings where they clarify reusable functions; do not bury exploratory code in boilerplate.

## Notebooks and modeling

- Organize notebooks so they run from top to bottom: load, inspect, prepare, analyze or model, and evaluate as appropriate. Avoid hidden state and dependencies on out-of-order execution.
- Keep small explorations lightweight. Do not turn a notebook into a package or framework unless the task needs it.
- In new modeling code, separate evaluation data before fitting preprocessing; fit transformations inside training folds during cross-validation. Respect temporal and group boundaries when choosing splits.
- Set explicit random seeds for new stochastic experiments when reproducibility is needed. Preserve existing seeds, split membership, model settings, and metrics during refactoring.
- If existing code leaks data or has a statistical error, explain the issue. Treat its correction as a behavior change, separate from simplification.

## Example: name meaningful stages

Prefer this when the stages help the reader inspect the analysis:

```python
completed_orders = orders.loc[orders["status"].eq("completed")]
customer_revenue = completed_orders.groupby("customer_id")["revenue"].sum()
top_customers = customer_revenue.sort_values(ascending=False).head(10)
```

Keep the original aggregation and missing-value semantics when applying this pattern to existing code. Do not introduce a generic pipeline class for these three steps.

## Verification

- For refactoring, compare relevant before/after outputs, including index, columns, dtypes, missing values, and ordering. Use exact equality where appropriate; justify numerical tolerances rather than hiding changes behind loose comparisons.
- Run affected notebook cells or the notebook in a fresh kernel when practical and authorized. Do not blindly rerun costly training or cells that modify external data; report the verification limit instead.
- Preserve useful error handling and performance constraints. Avoid unrelated cleanup and new dependencies solely for style.

## Attribution

Adapted from [code-simplification](https://github.com/addyosmani/agent-skills/blob/main/skills/code-simplification/SKILL.md), copyright (c) 2025 Addy Osmani, under the MIT License. The original credits Anthropic's Code Simplifier as inspiration. This variation adds data science guidance and removes frontend-specific examples and heavyweight refactoring procedures.
