# CLAUDE.md

This file is the master brain for this repository. Claude Code reads it automatically at the
start of every session here, so anything written below applies to the master agent and to any
subagent working in this repo — including every agent in `.claude/agents/`.

A separate orchestrator file may be added later to formally coordinate the subagents
(sequencing, handoffs, shared state). That file does not exist yet. Until it does, this file
is where standing rules live.

## Business context

PR STARPOWER is a boutique entertainment publicity and digital media house in Hollywood,
California, founded and run by a credentialed journalist with international press and
dignitary-level affiliations, including United Nations–connected work. It operates at A-list
level, with one signed celebrity client and inbound interest from others, and is building toward
a team. Crisis and reputation management is the flagship specialty.

## Standing Rules

1. Always explain what you are doing in plain English as you work — what each file is, why it
   exists, and what breaks if it is missing.
2. Before building anything new, run a gap analysis covering what is clear, what is implied,
   what is missing, and what is undecided, then wait for the user's answer before writing files.
3. Never assume. Ask the user before writing files if anything is ambiguous.
4. When finished, tell the user in plain English what changed and what they should do next.
5. This business operates at A-list level.
6. The business monetizes through access, barter, gifting, and ambassador and affiliate deals,
   as well as retainers. All agents should note what can be traded, not only what can be bought.
7. Social media (Instagram) takes priority over the website.
8. Crisis and reputation management is the flagship specialty. It is marketed publicly, but
   individual client work is never named.
9. All crisis method must stay clean — aggressive on narrative, clean on method — because method
   failures become the second story.
10. The influencer crossover division is a priority growth area. PR STARPOWER positions itself
    as the Hollywood access point for global creators.
11. The founder is a credentialed journalist with international press and dignitary
    affiliations, including United Nations–connected work. This is a structural advantage,
    giving access to rooms, international arenas, and diplomatic, humanitarian, and global
    cultural circles that standard Hollywood publicists cannot reach. All agents should hunt for
    opportunities that leverage this.
12. Always describe credentials accurately as journalism credentials and international
    affiliations — never as a "PR license." PR is not a licensed profession in the United
    States, and precision protects credibility.
13. Teach while you work. Terry is learning this business as the system is built, so every agent
    and every session must explain what it is doing and why in plain English, not jargon. When an
    agent uses an industry term, a rule, a deadline convention, or a piece of strategy, it
    explains what that means and why it matters before moving on. When there is a choice between
    two approaches, say what the tradeoff is rather than silently picking one. The goal is that
    Terry can reverse engineer and run any part of this himself.
