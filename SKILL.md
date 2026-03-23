---
name: table-analysis-pro
description: Professional workflow for analyzing CSV, Excel, and DataFrame-style tabular data, and for reviewing or designing AI agents that operate on structured tables. Use when the task involves schema inspection, filtering, aggregation, sorting, merging, pivoting, multi-table comparison, anomaly checking, KPI calculation, or evaluating the data-processing flow of table-analysis systems.
---

Use this skill for two kinds of work:

1. Analyze structured tables such as CSV, Excel, and DataFrame-like data.
2. Review or design table-analysis agents, data copilots, or spreadsheet-oriented AI systems.

Keep the workflow disciplined: inspect first, clarify if needed, plan when complexity warrants it, execute safely, then validate before concluding.

## Core rules

- Inspect schema before making claims.
- Ask a clarification question when ambiguity would materially change the result.
- Plan before executing multi-step, multi-table, or project-review tasks.
- Prefer structured operations first; use code only when simpler operations are insufficient.
- Check join keys, grain, and metric definitions before merging or comparing tables.
- Report conclusions with supporting numbers.
- End with a self-check: confirm the user request was answered and major assumptions were stated.

## Fast task classification

Classify the request early:

- Single-table exploration
- Filtering / lookup
- Aggregation / KPI summary
- Derived-metric calculation
- Pivot / crosstab analysis
- Multi-table merge
- Multi-table comparison
- Data-quality / anomaly inspection
- Project review or workflow design

Choose the lightest workflow that still produces a reliable answer.

## Workflow for table analysis

### 1. Understand the request
Extract the minimum needed to proceed:

- target tables/files
- desired output
- metric or comparison requested
- grouping level or time range
- whether the user wants exploration, explanation, or execution

Ask a concise clarification question if any missing detail would materially change the answer.

### 2. Inspect before analysis
Inspect enough of each table to establish:

- row and column counts
- column names
- data types
- sample rows
- missingness or suspicious fields
- candidate keys / join columns
- likely grain of each row

Do not infer semantics from column names alone when sample values can disambiguate them.

### 3. Make a short plan when needed
Make an explicit plan when the task involves:

- multiple tables
- multiple transformations
- custom KPIs or business logic
- substantial ambiguity
- project review rather than direct computation

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

### 5. Handle multi-table work carefully
Before joining or comparing tables, check:

- same grain or different grain?
- unique key on either side?
- should one side be aggregated first?
- are time ranges aligned?
- are the metrics defined the same way?

If comparability is weak, state that clearly before giving strong conclusions.

### 6. Use code only when justified
Use code when:

- the transformation is too custom for direct table operations
- several operations are clearer in code
- pattern detection or bespoke logic is required
- built-in operations cannot express the logic safely

When using code:
- keep it narrow
- make assumptions explicit
- favor readability over cleverness
- preserve traceable reasoning when it matters

### 7. Validate before concluding
Check:

- totals, counts, and row changes are plausible
- filters did not silently drop most rows
- derived metrics are mathematically consistent
- the final answer covers the original request
- caveats and assumptions are stated

### 8. Present results cleanly
Default structure:

- task understanding
- method summary
- key findings
- supporting numbers
- caveats / uncertainty
- next step (optional)

Compress this for simple tasks. Keep it explicit for complex tasks.

## Workflow for reviewing a table-analysis project

When studying a project rather than analyzing a dataset, review it along these dimensions:

### 1. Input layer
Check:
- supported file formats
- upload/loading flow
- in-memory vs persisted state
- metadata preservation

### 2. Schema understanding
Check:
- whether the system inspects columns, types, samples, and missingness
- whether schema discovery is explicit or implicit
- whether it distinguishes numeric / categorical / temporal fields
- whether it identifies grain and join candidates

### 3. Intent handling
Check:
- clarification logic
- plan generation
- support for multi-step tasks
- whether the system avoids premature execution

### 4. Execution model
Check:
- tool-based execution vs freeform code
- available table operations
- traceability of tool or code execution
- iterative loop design
- reflection / self-check pass

### 5. Multi-table reasoning
Check:
- join support
- comparison support
- per-table isolation before synthesis
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
- sandbox boundaries

### 8. Engineering and safety
Check:
- state isolation
- multi-user readiness
- sandbox quality
- observability
- suitability for prototype vs production

For project reviews, separate:
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
- overgeneralizing from sample rows
- returning conclusions without numeric support
- skipping planning on complex tasks
- reviewing a demo as if it were production-ready
- defaulting to code when direct table operations are enough

## Reference files

Read these only when needed:

- `references/workflow-patterns.md` for reusable analysis and review templates
- `references/project-review-rubric.md` for a structured system-review checklist
- `references/output-patterns.md` for response and presentation templates
