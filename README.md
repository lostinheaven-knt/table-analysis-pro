# table-analysis-pro

A reusable AgentSkill for professional tabular-data analysis and for reviewing table-analysis agent projects.

## What it is

`table-analysis-pro` captures a practical workflow for:

- analyzing CSV / Excel / DataFrame-style tabular data
- handling single-table and multi-table tasks safely
- reviewing projects like table-analysis agents, data copilots, or spreadsheet-focused AI tools
- extracting reusable patterns from table-analysis systems

It focuses on workflow, judgment, and output quality rather than teaching pandas syntax.

## Included files

- `SKILL.md` — core skill instructions
- `references/workflow-patterns.md` — common analysis flow templates
- `references/project-review-rubric.md` — structured review checklist for table-analysis systems
- `references/output-patterns.md` — response and presentation templates

## Usage intent

Use this skill when the task involves:

- schema inspection
- filtering / lookup
- aggregation / KPI summaries
- derived metrics
- pivoting / crosstabs
- merging or comparing tables
- anomaly or data-quality checks
- reviewing the workflow of a table-analysis project

## Design principles

- inspect before concluding
- clarify when ambiguity matters
- plan before multi-step execution
- verify join keys and grain before merging
- prefer structured operations before custom code
- present results with evidence and caveats

## Status

Initial draft. Expected to evolve through real usage and project reviews.
