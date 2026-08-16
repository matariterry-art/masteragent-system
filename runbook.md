# Runbook

Placeholder. Operational detail (exact commands, invocation syntax, error handling) is not
written yet. What follows is the agent order and the one hard rule about handoffs.

## Agent order

1. `market-signal-researcher`
2. `offer-architect`
3. `content-angle-strategist`
4. `conversion-system-builder`

## Handoff rule

Nothing chains automatically. Each agent's output must be handed to the next agent as an
explicit file path (e.g. "read `outputs/market-signals.md` and use it as input"). There is no
orchestrator wiring these together yet, so if a file path isn't stated explicitly, the next
agent has nothing to read.
