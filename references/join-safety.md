# Join Safety

Use this reference when a task involves joining, merging, aligning, or comparing multiple tables.

## Core rule

Do not merge until you understand grain, key behavior, and duplication risk.

## Pre-join checklist

Before joining, establish:

- what one row represents in each table
- the intended join key(s)
- whether keys are unique on either side
- whether null keys exist
- whether one side should be aggregated first
- whether time windows and metric definitions are aligned

## Join patterns

### 1. One-to-one
Safe when the key is unique on both sides.

### 2. One-to-many
Usually valid, but be explicit about duplication after the join.

### 3. Many-to-many
High risk. Avoid unless it is clearly intended. Usually aggregate or deduplicate first.

## Common failure modes

- row explosion after join
- silent duplication of metrics
- joining on weak text fields
- misaligned time ranges
- mixing gross and net metrics
- null keys dropping records unexpectedly

## Safe workflow

1. Inspect grain on both sides
2. Inspect key uniqueness and nulls
3. Decide whether pre-aggregation is needed
4. Choose join type deliberately
5. Validate post-join row counts
6. Check whether key metrics changed unexpectedly
7. State any remaining caveats

## Output guidance

When reporting results after a join, mention:

- join key used
- join type used
- whether duplication risk existed
- whether unmatched records were present
- whether comparability limits remain
