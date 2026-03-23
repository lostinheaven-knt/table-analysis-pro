# table-analysis-pro

A reusable AgentSkill for professional tabular-data analysis and for reviewing table-analysis agent projects.

## What it does

`table-analysis-pro` captures a disciplined workflow for:

- analyzing CSV / Excel / DataFrame-style tabular data
- handling single-table and multi-table tasks safely
- reviewing table-analysis agents, data copilots, and spreadsheet-oriented AI tools
- extracting reusable patterns from table-analysis systems

It focuses on workflow, judgment, and output quality rather than teaching pandas syntax.

## Repository structure

- `SKILL.md` — core skill instructions
- `references/workflow-patterns.md` — reusable analysis and review patterns
- `references/project-review-rubric.md` — checklist for evaluating table-analysis systems
- `references/output-patterns.md` — response and presentation templates
- `references/join-safety.md` — safe merge/join guidance
- `references/metric-definition.md` — KPI and derived-metric guidance
- `PUBLISHING.md` — release and packaging notes
- `CHANGELOG.md` — release history

## Use this skill when the task involves

- schema inspection
- filtering / lookup
- aggregation / KPI summaries
- derived metrics
- pivoting / crosstabs
- merging or comparing tables
- anomaly or data-quality checks
- reviewing a table-analysis workflow or project

## Working principles

- inspect before concluding
- clarify when ambiguity matters
- plan before multi-step execution
- verify join keys and grain before merging
- define metrics before computing or comparing them
- prefer structured operations before custom code
- present results with evidence and caveats

## Release status

`v0.1.0` candidate — documentation-first, publishable draft.
