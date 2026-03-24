# Related Projects

Use this reference when you want external examples of table-analysis agents, adjacent systems, or comparable product patterns.

## TabClaw

- Repo: https://github.com/fishsure/TabClaw
- Positioning: a local AI agent for conversational table analysis with an interactive UI

### Notable patterns

- clarification-first flow when the request is ambiguous
- editable execution plan shown before acting
- parallel per-table analyst agents with a synthesizing aggregator
- uncertainty-aware synthesis (`CONSENSUS` vs `UNCERTAIN` style framing)
- persistent user memory/preferences across sessions
- post-task skill distillation / reusable skill learning
- automatic context compaction for long conversations

### Why it matters for this skill

TabClaw is useful as a concrete comparison point when reviewing or designing table-analysis systems because it combines:

- product UX patterns for table agents
- multi-table orchestration patterns
- memory / skill-learning / compaction ideas
- an end-user-facing presentation layer rather than a pure back-end workflow

### How to use it

Reference TabClaw when the task involves:

- reviewing a table-analysis product or agent design
- comparing workflow choices across table-agent systems
- extracting reusable patterns from an existing table-analysis project
- discussing tradeoffs in clarification, planning, orchestration, memory, or output presentation

### Caution

Treat TabClaw as an external inspiration/reference point, not as normative truth. Re-check implementation claims against the repository when details matter.
