# 7-day measurement protocol

The goal is to improve **accepted task outcomes per unit of real observed usage**, not to claim that prompt text alone cuts tokens.

## Baseline versus LeanOps

- Select at least five matched task pairs with similar complexity and data freshness requirements.
- Run baseline workflow and LeanOps workflow with the same quality criteria and comparable permissions.
- Record actual usage from the platform where available. If unavailable, set `usage_*` to `UNKNOWN` and compare operational proxies instead; **do not infer token counts** from run counts.
- Capture task success, number of retries, browser interactions, wall-clock time where observed, and human revision minutes.
- Repeat across different task types only after the first workflow is stable.

## Fields

The CSV header describes a simple log:

- `date`, `variant`, `task_id`, `task_type`, `accepted`.
- `usage_before`, `usage_after`, `usage_unit`: platform-reported figures and units; beware weekly resets and other simultaneous jobs.
- `tool_calls`, `browser_actions`, `retries`, `human_revision_minutes`, `output_ref`, `notes`.

Do not compare a baseline day with a later day if the remaining allowance reset or unrelated tasks consumed allowance in between. If only total remaining usage is visible, take closely bracketed readings and mark uncertainty.

## Decision gate

Keep the configuration only if quality stays at least as good, accepted-task yield improves or unnecessary work falls, and no new security regressions appear. Roll back confusing instructions, over-aggressive caching, or unapproved tool changes.
