# Project Review Rubric for Table-Analysis Systems

Use this checklist when reviewing a project that performs tabular-data analysis or acts as a table-analysis agent.

Score informally if needed: strong / adequate / weak.

## 1. Product goal

- What user problem does the project solve?
- Is it a demo, research prototype, internal tool, or production system?
- Is the target workflow clear?

## 2. Data ingestion

- What file formats are supported?
- How are files uploaded or loaded?
- Is parsing robust?
- Are parse failures explained clearly?
- Is state stored in memory, on disk, or per session?

## 3. Schema discovery

- Does the system inspect columns, types, missingness, and samples?
- Is there explicit schema understanding before execution?
- Does it recognize table grain and join keys?
- Does it support multiple tables cleanly?

## 4. Intent handling

- Does it ask clarifying questions when necessary?
- Can it distinguish simple from complex tasks?
- Does it support plan generation or task decomposition?
- Does it avoid premature execution?

## 5. Execution model

- Tool-driven, code-driven, or hybrid?
- Are the available operations sufficient for normal analysis?
- Can intermediate results be reused?
- Is execution traceable and inspectable?
- Is there a reflection or self-check stage?

## 6. Multi-table reasoning

- Does it support join operations safely?
- Does it support compare/synthesize workflows?
- Is there per-table isolation before synthesis?
- Does it express uncertainty when tables are not fully comparable?

## 7. Memory and context management

- Does it persist user preferences or domain facts?
- Is memory relevance-filtered?
- Is long context compacted or summarized?
- Are sessions isolated?

## 8. Extensibility

- Can users define custom skills/tools?
- Can common workflows be reused?
- Is there plugin or registry support?
- Can the system learn or distill new patterns?

## 9. Code execution and safety

- Is code execution sandboxed?
- What imports/calls are blocked?
- Is there a timeout?
- Is this suitable only for local use, or hardened for untrusted users?
- Are security claims proportionate to reality?

## 10. Engineering maturity

- Is the code modular?
- Is state management clean?
- Is multi-user support present?
- Are logs/errors observable?
- Is there test coverage?
- Is the system production-ready or prototype-only?

## 11. Output quality

- Are conclusions grounded in actual results?
- Are uncertainties or assumptions reported?
- Are results structured and readable?
- Does the system separate evidence from interpretation?

## 12. Reusability

- What patterns could be extracted into a skill/framework?
- What parts are project-specific?
- What parts generalize to other table-analysis systems?

## Suggested review output

Structure reviews like this:

1. Project positioning
2. Core workflow
3. Strengths
4. Weaknesses
5. Engineering maturity
6. Reusable patterns worth extracting
7. Final verdict
