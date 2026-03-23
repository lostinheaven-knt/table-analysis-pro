# Output Patterns

Use these templates to present results clearly. Adapt tone and depth to the user’s question.

## 1. Simple analysis answer

### Template
- Task: what was analyzed
- Method: what operations were used
- Result: direct answer with key numbers
- Caveat: only if needed

### Example shape
Task: Analyze sales by region in Q4.
Method: Filter Q4 rows, aggregate revenue by region, sort descending.
Result: East leads with 12.4M, followed by South at 10.8M.
Caveat: Two rows had missing region and were excluded.

---

## 2. Structured analysis answer

### Template
## Task understanding
Brief restatement of the user request.

## Method
List the main operations:
- inspected schema
- filtered rows
- computed metric
- aggregated / ranked / compared

## Key findings
- finding 1 with number
- finding 2 with number
- finding 3 with number

## Caveats
- ambiguity
- data quality issue
- comparability issue

## Next step
Optional follow-up suggestion.

---

## 3. Multi-table comparison answer

### Template
## Comparison setup
Explain which tables were compared and on what basis.

## Shared patterns
- consensus finding
- consensus finding

## Differences
- table A vs table B
- strongest divergence
- possible reason

## Uncertainty / comparability limits
- grain mismatch
- key mismatch
- time coverage mismatch

## Final conclusion
Short synthesis with 3–5 bullets.

---

## 4. Project review answer

### Template
## Project positioning
What the project is trying to do.

## Core workflow
Input → schema understanding → planning → execution → output.

## Strengths
- workflow or product strengths
- reusable design ideas

## Weaknesses
- engineering gaps
- safety gaps
- production-readiness limits

## Reusable patterns
What could be extracted into a generic skill or framework.

## Verdict
Short final assessment.

---

## 5. Uncertainty-aware phrasing

Use these when the evidence is incomplete:

- "Based on the available columns and sample values..."
- "This conclusion is directionally strong, but depends on the assumption that..."
- "These tables are not perfectly comparable because..."
- "The merge appears to create duplication risk due to..."
- "I can give a stricter answer after confirming..."

Avoid fake certainty when:
- metric definitions are unclear
- join keys are weak
- sample-only evidence is available
- time windows differ
- null handling changes the result materially

---

## 6. Review verdict pattern

Use short verdicts like:

- Strong product idea, prototype-grade engineering
- Clear workflow design, limited production readiness
- Good table-agent architecture, light safety boundaries
- Useful for local/internal usage, not yet suitable for multi-tenant deployment
