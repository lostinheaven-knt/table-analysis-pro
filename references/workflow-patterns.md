# Workflow Patterns

Use these patterns as templates. Adapt them to the task instead of copying them mechanically.

## 1. Single-table exploration

Use when the user asks for a general understanding of one dataset.

### Steps
1. Inspect schema and sample rows
2. Identify numeric / categorical / temporal columns
3. Check missingness and obvious anomalies
4. Infer likely table grain
5. Summarize what the dataset appears to represent
6. Suggest useful next analyses when helpful

### Output focus
- what the dataset contains
- likely grain
- useful columns
- obvious quality issues

---

## 2. Filtering and lookup

Use when the user wants specific rows, entities, or conditions.

### Steps
1. Confirm target table and filter condition
2. Validate relevant columns and value forms
3. Apply exact match, condition, or regex match
4. Report row count and representative matches
5. Note ambiguities if matching is fuzzy

### Watch for
- type mismatch
- case sensitivity
- null handling
- duplicate matches

---

## 3. Aggregation / KPI summary

Use when the user wants totals, averages, counts, rankings, or grouped summaries.

### Steps
1. Confirm the metric and grouping
2. Inspect relevant columns
3. Filter to the relevant slice if needed
4. Aggregate
5. Sort or rank
6. Verify totals and explain the result

### Common metrics
- sum
- average
- count
- distinct count
- min / max
- ratio / derived KPI

---

## 4. Derived metric calculation

Use when the user needs a new column or KPI such as margin, conversion rate, ARPU, or growth.

### Steps
1. Define the formula explicitly
2. Check source columns and types
3. Handle divide-by-zero / nulls
4. Create the derived metric
5. Aggregate or compare if needed
6. Validate with spot checks

### Watch for
- unit mismatch
- percentage vs decimal confusion
- gross vs net definitions

---

## 5. Pivot / cross-tab analysis

Use when the user wants a matrix view by dimensions.

### Steps
1. Confirm index, columns, values, and agg function
2. Inspect data types and category values
3. Build the pivot
4. Check for sparsity or extreme skew
5. Summarize the dominant patterns

### Good use cases
- sales by region x quarter
- headcount by department x level
- satisfaction by country x usage frequency

---

## 6. Multi-table merge analysis

Use when the user wants to combine tables.

### Steps
1. Identify candidate join keys
2. Confirm grain of each table
3. Check key uniqueness and nulls
4. Decide join type
5. Consider aggregating before joining
6. Merge
7. Validate row-count change and duplication risk
8. Proceed to downstream analysis

### Mandatory checks
- one-to-many vs many-to-many
- unmatched keys
- duplicated rows after join
- whether time alignment matters

---

## 7. Multi-table comparison

Use when the user wants differences, similarities, side-by-side metrics, or per-table conclusions.

### Steps
1. Inspect each table separately
2. Standardize comparable fields or metrics
3. Compute per-table findings
4. Synthesize shared and differing patterns
5. Mark uncertainty where definitions, grain, or coverage differ

### Good output pattern
- shared observations
- key differences
- likely causes
- comparability limits

---

## 8. Data-quality / anomaly inspection

Use when the user suspects bad data, outliers, duplicates, or broken records.

### Steps
1. Inspect schema and expected ranges
2. Check missingness
3. Check duplicates / key integrity
4. Check impossible or suspicious values
5. Quantify the problem
6. Suggest remediation or exclusion logic

### Common checks
- null spikes
- negative values where not expected
- date inconsistencies
- duplicate IDs
- outlier distributions

---

## 9. Project review: table-analysis agent

Use when the user wants to study a project rather than compute data results.

### Steps
1. Identify the project’s goal and target user
2. Inspect architecture and the main execution loop
3. Review data ingestion and schema handling
4. Review planning / clarification / execution design
5. Review tool abstractions and sandboxing
6. Review memory / extensibility / multi-agent logic
7. Assess strengths, weaknesses, and production readiness
8. Extract reusable workflow patterns if appropriate

### Output focus
- what problem it solves
- how the workflow is structured
- what is reusable
- what is prototype-only
