# CLAUDE.md

This file is the master brain for this repository. Claude Code reads it automatically at the
start of every session here, so anything written below applies to the master agent and to any
subagent working in this repo — including the four in `.claude/agents/`.

A separate orchestrator file may be added later to formally coordinate the four subagents
(sequencing, handoffs, shared state). That file does not exist yet. Until it does, this file
is where standing rules live.

## Standing Rules

1. Always explain what you are doing in plain English as you work — what each file is, why it
   exists, and what breaks if it is missing.
2. Before building anything new, run a gap analysis covering what is clear, what is implied,
   what is missing, and what is undecided, then wait for the user's answer before writing files.
3. Never assume. Ask the user before writing files if anything is ambiguous.
4. When finished, tell the user in plain English what changed and what they should do next.
