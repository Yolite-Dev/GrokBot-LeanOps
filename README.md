# GrokBot-LeanOps

**A lean operating playbook for Grok Bot: fewer redundant actions, clear approvals, and measurable task outcomes.**

> Community-created guidance, not affiliated with or endorsed by xAI. No measured token-saving percentage is claimed. Features, quotas, and tool availability can vary by account; verify against the current [Grok Bot documentation](https://docs.x.ai/grok-bot/skills-routines-and-automations).

[中文说明](README.zh-CN.md)

## What this is

A lightweight **instruction + skill + measurement** starter kit, rather than an application or a magical token-reduction switch. It aims to reduce needless tool actions, repeat searches, excessive bot handoffs, and high-frequency routines while maintaining quality and safety.

## Quick start

1. Read [`instructions/LEAN_GLOBAL.md`](instructions/LEAN_GLOBAL.md). Copy the section between `BEGIN` and `END` into **one test Bot**'s instructions, using the currently supported Grok Bot UI. Keep the Bot's existing role and business constraints.
2. Run a **read-only** inventory of current routines, tools, and a representative recent task. Do not change routines or permissions yet.
3. For an actual task, provide the input, desired output, acceptance criteria, and approval boundaries. Use [`skills/lean-execution/SKILL.md`](skills/lean-execution/SKILL.md) as a *workflow reference*; ask Grok Bot to save/adapt it as a private skill if supported in your account. Do not assume GitHub `SKILL.md` files auto-install.
4. Compare five matched tasks **before and after** using [`examples/usage-log.csv`](examples/usage-log.csv) and [`docs/MEASUREMENT.md`](docs/MEASUREMENT.md).
5. Only then test a low-frequency scheduled routine. Keep all external publication, messages, purchases, and production writes behind the appropriate approval mechanism.

## Default operating pattern

```text
Task -> Check prior approved results -> Identify gaps -> Select least expensive reliable method
     -> Execute in bounded steps -> Verify -> Store concise result + status -> Stop
```

- **Reuse** relevant recent work, but refresh stale facts when the task requires currency.
- **Prefer supported authorized APIs/CLI** over repetitive screenshots for repeatable structured operations; browser automation remains a fallback.
- **Don't repeatedly read long histories**; maintain concise task checkpoints.
- **Keep skills on-demand**. Do not load a large library into every prompt.
- **Do not start new scheduled routines** without a real need or a baseline measurement.
- **Measure outcomes**, not just raw token counts: successful and accepted deliverables per unit of measured usage, error rate, and human revision time.

## Repository layout

| Path | Purpose |
|---|---|
| `instructions/LEAN_GLOBAL.md` | Short copy/paste Bot instructions |
| `skills/lean-execution/SKILL.md` | Reusable on-demand workflow (no internal paths assumed) |
| `docs/MEASUREMENT.md` | 7-day A/B testing method and limitations |
| `docs/SECURITY.md` | Permission boundaries and shared-computer caveat |
| `docs/SOURCES.md` | Official documentation and community inspiration |
| `examples/usage-log.csv` | Blank usage and quality measurement template |

## What this cannot do

It **cannot change underlying model selection**, bypass quota limits, guarantee lower costs, enforce hard run limits via prompts, or create security boundaries between bots. Hard limits, deduplication, and safe writes require reliable code or platform controls.

## License

[MIT](LICENSE). The original text in this repository is authored for this project; other projects are **linked, not copied or bundled**. Follow the respective licenses before reusing third-party material.
