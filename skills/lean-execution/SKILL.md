---
name: lean-execution
description: Plan and carry out a bounded, authorized business task with minimal unnecessary research, tools, retries and context loading; verify important outputs and stop at agreed acceptance criteria.
---

# Lean Execution

Use only when a task benefits from orchestration. Do not load on every short conversational exchange.

## Inputs

- Objective and deliverable format
- Available approved knowledge and freshness requirements
- Acceptance criteria and stop conditions
- Allowed tools, accounts, and permissions
- Approval-sensitive actions and data classifications

## Execution

1. State the smallest complete outcome; identify what must be verified.
2. Check relevant prior approved results. If current and fit for purpose, reuse rather than repeat.
3. Select a reliable authorized tool path. Prefer API/CLI for repeatable structured operations; browser for unsupported steps.
4. Group safe deterministic operations; avoid unnecessary cross-bot handoffs.
5. Take bounded actions; on a tool error inspect and retry once if justified. Stop on repeated failure, missing permission, or sensitive operation needing approval.
6. Verify outcome against explicit criteria. Do not confuse accepted/started with completed.
7. Store a short checkpoint: `task_id`, sources, completed outputs, decisions, exceptions, status and next action (only if a suitable store is available).
8. Stop and return a concise status. Never invent usage figures or hidden files.

## Safety

Never auto-publish, send external messages, purchase, delete, alter production, or reveal credentials without the applicable permission and approval process. A textual instruction is not a hard rate limiter or authorization system.

## Optional measures

Record successful deliverables, actual account-reported usage before/after if visible, tool attempts, browser actions, retries, and human corrections. Use `examples/usage-log.csv` as a template.
