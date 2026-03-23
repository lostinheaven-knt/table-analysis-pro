# Metric Definition

Use this reference when the request depends on KPI definitions, derived metrics, or business-specific formulas.

## Core rule

Do not compute or compare a metric until its definition is explicit enough to survive scrutiny.

## Clarify when needed

Ask for clarification if any of these would materially change the answer:

- numerator or denominator choice
- gross vs net definition
- inclusion / exclusion rules
- time window
- grouping level
- treatment of null or zero values

## Metric design checklist

Before computing a metric, confirm:

- formula
- source columns
- units
- aggregation level
- valid value range
- null and zero handling
- whether the metric is comparable across tables or periods

## Common metric traps

- percentage vs decimal confusion
- averaging ratios instead of recomputing from base values
- mixing daily and monthly windows
- using counts where distinct counts are needed
- dividing by zero or near-zero values without comment
- comparing metrics built from different business definitions

## Safe workflow

1. Write the formula in plain language
2. Map the formula to actual columns
3. Check units and data types
4. Define null / zero handling
5. Compute a few spot checks
6. Aggregate only after the metric logic is confirmed
7. State caveats if the definition is inferred rather than confirmed

## Output guidance

When the metric matters to the conclusion, report:

- formula used
- important assumptions
- exclusions or edge-case handling
- whether the metric is fully comparable across tables / periods
