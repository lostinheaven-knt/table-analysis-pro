---
name: table-analysis-pro
description: Professional workflow for analyzing CSV, Excel, and DataFrame-style tabular data, and for reviewing or designing AI agents that operate on structured tables. Use when the task involves schema inspection, filtering, aggregation, sorting, merging, pivoting, multi-table comparison, anomaly checking, or evaluating the data-processing flow of table-analysis systems.
---

Use this skill when the task involves tabular or structured data, including CSV, Excel, pandas/DataFrame-style workflows, or when reviewing a table-analysis agent/project.

## Core rules

- Inspect schema before making claims.
- Clarify when ambiguity would materially change the analysis.
- Plan before executing when the request is multi-step or cross-table.
- Prefer structured operations first; use code only when built-in operations are insufficient.
- For multi-table work, verify join keys, grain, and comparability before merging.
- Report conclusions with supporting numbers, not vibes.
- End with a self-check: confirm the request was fully answered and no major assumption went unstated.

## Task classification

Classify the request early. Common categories:

- Single-table exploration
- Single-table aggregation/statistics
- Filtering or lookup
- Derived-metric calculation
- Pivot/crosstab analysis
- Multi-table merge/join
- Multi-table comparison
- Anomaly or data-quality inspection
- Review/design of a table-analysis agent or workflow

Choose the lightest workflow that still gives a reliable answer.

## Standard workflow for table analysis

### 1. Understand the request
Extract:

- the target tables or files
- the desired output
- the metric or comparison being asked for
- any time range, grouping level, or business definition
- whether the user wants exploration, explanation, or execution

If any of these is underspecified and would change the result meaningfully, ask a concise clarification question.

### 2. Inspect the data first
Before analysis, inspect enough of the table(s) to establish:

- row count and column count
- column names
- data types
- sample rows
- missing values or suspicious fields
- candidate keys / join columns
- likely grain of each table (row = what?)

Do not infer semantic meaning from column names alone when sample data can disambiguate it.

### 3. Build a short plan for non-trivial tasks
Use a brief explicit plan when the task involves:

- more than one table
- multiple transformations
- user-defined metrics
- ambiguous business logic
- a review of a project/system rather than a direct numeric answer

A good plan usually includes:
- inspect
- clean / align
- transform
- compare / aggregate
- verify
- summarize

### 4. Execute analysis in a reliable order
Typical order:

1. inspect / preview
2. clean or normalize if needed
3. filter relevant rows
4. derive metrics
5. aggregate or pivot
6. sort / rank / compare
7. validate outputs
8. summarize findings

Avoid merging early if aggregation-first will produce a cleaner and safer result.

### 5. Handle multi-table tasks carefully
Before joining or comparing tables, explicitly check:

- Are the tables at the same grain?
- Is the join key unique on either side?
- Should one side be aggregated first?
- Are time ranges aligned?
- Are the compared metrics defined the same way?

If any of these is uncertain, state the uncertainty before presenting strong conclusions.

### 6. Use code only when needed
Prefer direct table operations first. Use code when:

- the transformation is too custom for standard operations
- multiple operations are easier to express in code
- pattern detection or custom logic is required
- built-in tools cannot represent the needed logic safely

When using code:
- keep it narrow
- make assumptions explicit
- favor readability over cleverness
- preserve intermediate reasoning when it matters

### 7. Validate before concluding
Check:

- Are totals, counts, and row changes plausible?
- Did any filter unexpectedly drop most rows?
- Are derived metrics mathematically consistent?
- Does the final answer address the original request?
- Are caveats or assumptions clearly stated?

### 8. Present results cleanly
Default output structure:

- task understanding
- method summary
- key findings
- supporting numbers
- caveats / uncertainty
- next step (optional)

For simple requests, compress this structure. For complex requests, keep it explicit.

## Workflow for reviewing a table-analysis project

When the task is to study a project rather than analyze a dataset, review it along these dimensions:

### 1. Input layer
Check:
- supported file formats
- upload/loading flow
- in-memory vs persisted state
- metadata preservation

### 2. Schema understanding
Check:
- whether the system inspects columns, types, samples, missingness
- whether schema discovery is explicit or implicit
- whether it distinguishes numeric / categorical / temporal fields

### 3. Intent handling
Check:
- clarification logic
- plan generation
- support for multi-step tasks
- whether the system prevents premature execution

### 4. Execution model
Check:
- tool-based execution vs freeform code
- available table operations
- tool traceability
- iterative loop design
- reflection / self-check pass

### 5. Multi-table reasoning
Check:
- join support
- comparison support
- parallel per-table analysis
- synthesis / aggregator design
- uncertainty handling

### 6. Memory and context
Check:
- persistent preferences or facts
- context compaction / summarization
- session isolation
- relevance filtering

### 7. Extensibility
Check:
- custom skills/plugins
- learned workflows
- reusable tool abstractions
- code sandboxing boundaries

### 8. Engineering and safety
Check:
- state isolation
- multi-user readiness
- sandbox quality
- observability
- suitability for prototype vs production

For project reviews, distinguish clearly between:
- product idea quality
- workflow design quality
- codebase maturity
- production readiness

## Common failure modes

Avoid these mistakes:

- treating column names as ground truth without sampling values
- merging before confirming grain and key behavior
- comparing metrics with different definitions
- treating null as zero without justification
- overgeneralizing from a sample
- returning conclusions without numeric support
- skipping planning on complex tasks
- reviewing a demo project as if it were production-ready
- recommending code-heavy solutions when simple table operations suffice

## Reference files

Read these only when needed:

- `references/workflow-patterns.md` for common analysis patterns and execution templates
- `references/project-review-rubric.md` for a structured checklist when reviewing a table-analysis system/project
- `references/output-patterns.md` for response templates and result presentation patterns
