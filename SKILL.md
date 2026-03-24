---
name: table-analysis-pro
description: Professional workflow for (1) analyzing CSV, Excel, spreadsheet, and DataFrame-style tabular data, and (2) reviewing or designing AI agents and systems that operate on structured tables. Use when the task involves spreadsheet analysis, table reasoning, schema inspection, filtering, aggregation, KPI or metric definition, joins, pivots, cross-table comparison, anomaly checks, or evaluating a table-analysis workflow, data copilot, or table-agent product.
---

Use this skill for either direct table analysis or for reviewing/designing table-analysis systems. Choose the lightest workflow that still produces a reliable answer.

## Core rules

- Inspect schema before making claims.
- Ask a clarification question when ambiguity would materially change the meaning of the result.
- Plan before executing multi-step, multi-table, KPI-heavy, or project-review tasks.
- Prefer structured operations first; use code only when simpler operations are insufficient.
- Do not join before confirming grain, keys, and duplication risk.
- Do not compare metrics before confirming definition parity.
- Separate observed results from interpretation.
- Report conclusions with supporting numbers and explicit caveats.
- End with a self-check: confirm the request was answered and major assumptions were stated.

## Decision gates

Use these gates to decide what to do next:

### Clarify first when

- the requested metric could use multiple valid definitions
- the grain of the answer is unclear
- time range, grouping level, or comparison target is underspecified
- multiple tables could be joined in more than one plausible way
- the user may want exploration, explanation, or direct execution and this changes the workflow

### Make an explicit plan when

- the task spans multiple tables
- the task requires multiple transformations
- KPI logic or business rules matter
- the task is a system/project review rather than direct analysis
- ambiguity is substantial enough that the approach itself needs visibility

### Avoid strong conclusions when

- comparability across tables is weak
- join safety has not been established
- metric definitions are inconsistent or unknown
- key fields were not sampled or validated
- the available data supports only a partial answer

## Fast task classification

Classify the request early:

- single-table exploration
- filtering / lookup
- aggregation / KPI summary
- derived-metric calculation
- pivot / crosstab analysis
- multi-table merge
- multi-table comparison
- data-quality / anomaly inspection
- project review or workflow design

Choose the lightest workflow that still produces a reliable answer.

## Workflow for table analysis

### 1. Frame the task
Extract only what is needed to proceed:

- target tables/files
- desired output
- metric or comparison requested
- grouping level or time range
- whether the user wants exploration, explanation, or execution

Clarify if a missing detail would materially change the answer.

### 2. Inspect before transforming
Inspect enough of each table to establish:

- row and column counts
- column names
- data types
- sample rows
- missingness or suspicious fields
- candidate keys / join columns
- likely grain of each row

Do not infer semantics from column names alone when sample values can disambiguate them.

### 3. Plan when complexity warrants it
For multi-step, multi-table, or KPI-heavy tasks, make a short explicit plan.

A good plan usually follows:
- inspect
- clean / align
- transform
- aggregate / compare
- validate
- summarize

### 4. Execute in a safe order
Typical order:

1. inspect / preview
2. clean or normalize if needed
3. filter relevant rows
4. derive metrics
5. aggregate or pivot
6. sort / rank / compare
7. validate results
8. summarize findings

Prefer aggregation-first over merge-first when it reduces duplication risk.

### 5. Validate before concluding
Check:

- totals, counts, and row changes are plausible
- filters did not silently drop most rows
- derived metrics are mathematically consistent
- the final answer covers the original request
- caveats and assumptions are stated

### 6. Present results cleanly
Default structure:

- task framing
- method summary
- findings
- supporting evidence
- caveats / uncertainty
- interpretation or next step (optional)

Keep simple tasks concise. Keep complex tasks explicit.

## Code use

Use code when:

- the transformation is too custom for direct table operations
- several operations are clearer in code
- pattern detection or bespoke logic is required
- built-in operations cannot express the logic safely

When using code:

- keep it narrow
- make assumptions explicit
- favor readability over cleverness
- use code as an execution aid, not a substitute for schema, grain, or metric reasoning
- preserve traceable reasoning when it matters

## Workflow for reviewing a table-analysis project

When reviewing a table-analysis project, assess it across these dimensions:

- product goal and target workflow
- ingestion and schema understanding
- clarification and planning behavior
- execution model and traceability
- multi-table reasoning and synthesis
- memory/context handling
- extensibility and reuse
- engineering maturity and safety
- output quality and uncertainty handling

Separate:

- product idea quality
- workflow design quality
- codebase maturity
- production readiness

Use `references/project-review-rubric.md` when a structured or deeper review is needed.

## Gotchas

Build up this section over time from real failure points.

Avoid these mistakes:

- treating column names as ground truth without sampling values
- joining before confirming grain, key behavior, and duplication risk
- comparing metrics with different definitions or time windows
- treating null as zero without justification
- overgeneralizing from sample rows
- mixing observed results with interpretation
- returning conclusions without numeric support
- skipping planning on complex tasks
- reviewing a demo as if it were production-ready
- defaulting to code when direct table operations are enough
- silently choosing a statistical or business definition the user did not confirm

## Reference files

Read these only when needed:

- `references/workflow-patterns.md` for reusable analysis and review templates
- `references/project-review-rubric.md` for structured system reviews
- `references/output-patterns.md` for response and presentation templates
- `references/join-safety.md` for multi-table merge, join, or alignment safety
- `references/metric-definition.md` for KPI-heavy tasks or derived-metric reasoning
- `references/related-projects.md` for external comparison points or product-pattern inspiration (for example, TabClaw)
