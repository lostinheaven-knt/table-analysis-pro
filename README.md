# table-analysis-pro

A reusable AgentSkill for professional tabular-data analysis, safe multi-table workflows, and table-analysis project review.

## Why this exists

Many table-analysis tasks fail not because of syntax, but because of weak workflow: wrong joins, unclear metric definitions, missing grain checks, and overconfident conclusions.

`table-analysis-pro` is designed to make those failures less likely by enforcing a more disciplined analysis process.

## What it does

`table-analysis-pro` captures a disciplined workflow for:

- analyzing CSV / Excel / DataFrame-style tabular data
- handling single-table and multi-table tasks safely
- reviewing table-analysis agents, data copilots, and spreadsheet-oriented AI tools
- extracting reusable patterns from table-analysis systems

It focuses on workflow, judgment, and output quality rather than teaching pandas syntax.

## Typical use cases

Use this skill when the task involves:

- analyzing CSV / Excel / DataFrame-style data
- checking joins before merging tables
- defining KPIs before computing results
- reviewing a table-analysis agent, workflow, or project
- presenting findings with evidence, caveats, and next steps

## Example prompts

- Analyze this CSV and summarize the main KPIs.
- Compare these two tables and identify anomalies.
- Review this table-analysis agent design for join-safety and metric-definition risks.
- Help me validate whether this metric is defined correctly before I compute it.

## Quick start

### Get the packaged skill

Download the latest `.skill` artifact from the GitHub Release page:

- [v0.1.0 release](https://github.com/lostinheaven-knt/table-analysis-pro/releases/tag/v0.1.0)
- [Direct download: table-analysis-pro-v0.1.0.skill](https://github.com/lostinheaven-knt/table-analysis-pro/releases/download/v0.1.0/table-analysis-pro-v0.1.0.skill)

### Use the repository directly

If you want to inspect or adapt the skill before packaging, start with:

- `SKILL.md` for the core workflow
- `references/` for reusable analysis and review guidance
- `PUBLISHING.md` for release and packaging notes

## Repository structure

- `SKILL.md` — core skill instructions
- `references/workflow-patterns.md` — reusable analysis and review patterns
- `references/project-review-rubric.md` — checklist for evaluating table-analysis systems
- `references/output-patterns.md` — response and presentation templates
- `references/join-safety.md` — safe merge/join guidance
- `references/metric-definition.md` — KPI and derived-metric guidance
- `references/related-projects.md` — external comparison points and inspiration
- `PUBLISHING.md` — release and packaging notes
- `CHANGELOG.md` — release history

## Related project reference

- [`fishsure/TabClaw`](https://github.com/fishsure/TabClaw) — a strong external reference point for conversational table-analysis UX, planning, multi-table orchestration, memory, and skill-learning patterns

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

## Packaging

A distributable `.skill` package is included in `dist/` for release builds.

## Release status

`v0.1.0` — initial publishable draft.
