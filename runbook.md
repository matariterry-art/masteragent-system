# Runbook

Placeholder for exact commands and invocation syntax. What follows is the full agent roster,
running order, and the one hard rule about handoffs.

## Agent roster

**Signal-to-conversion chain** (run in this order):

1. `media-contact-builder` — builds and maintains the Hollywood calendar and the trade
   journalist/editor and event-partner contact architecture. Run first, and keep it current —
   everything else depends on its dates. (Talent-booking-route research now lives in
   `global-spotlight`, not here.)
2. `market-signal-researcher` — reads the calendar, researches market signals (demand, pricing,
   access), writes `outputs/market-signals.md`.
3. `social-content-engine` — reads the calendar, builds the Instagram posting calendar and
   website news feed.

`offer-architect`, `content-angle-strategist`, and `conversion-system-builder` were removed
(August 2026) — generic stubs from before PR STARPOWER's specifics existed, never written, and
nothing in the business needed them.

**Standing / on-demand agents** (not part of the linear chain):

- `crisis-reputation-command` — invoke immediately whenever a reputation event occurs. PR
  STARPOWER's flagship specialist.
- `influencer-crossover-division` — run periodically to keep the growth division current. Feeds
  creator-economy signals to `market-signal-researcher` and reputation-risk signals to
  `crisis-reputation-command`.
- `media-desk` — PR STARPOWER's senior press operation, not just a writer. Produces outreach
  (bespoke + mail-merge lanes) paired with a newsroom entry for prstarpower.com/newsroom.html,
  proposes story angles proactively from client files and the calendar, tracks what's changed in
  the media landscape each run, and pulls contacts from `outputs/spotlight/` first. Writes and
  proposes only — never sends, never publishes.
- `client-desk` — invoke for day-to-day client work: appearance prep, materials, outreach briefs
  (handed to `media-desk` for the actual copy), and campaign timelines. Always reads the relevant
  `clients/<client-slug>.md` file first. First active client: Freda Payne.
- `industry-intelligence` — run weekly, standing brief across craft standard, AI in PR/
  entertainment, distribution shifts, the business, and tools. Every finding sorted into
  shipped/demoed/announced-only, with a plain-English "what this means for PR STARPOWER" line.
  Surfaces findings; doesn't act on them — flags relevant ones to the agent that owns that area.
- `global-spotlight` — the firm's standing intelligence desk and its most valuable long-term
  asset. Owns and maintains `outputs/spotlight/`: the categorized contact database (genre,
  function, geography), the LA/NY newsroom map, TV/talk-circuit route profiles, the
  streaming/studio lane, the music-radio chart lane, live-events, a placement-pattern library
  (which publicists place with which journalists), `sources.md`, and mail-merge-ready
  `distribution/` lists. Run continuously — a stale profile is worse than none. **`booking-desk`
  was retired and merged into this agent August 16, 2026** — everything it produced (the gospel
  radio lane, Taste of Soul research, TV/podcast maps) was preserved and folded in under the
  correct lanes, each entry keeping its own original verification date. `media-desk` and
  `client-desk` both read targets from here first.
- `press-room` — a working newsroom, not a media relations tool. Four standing beats: the pulse
  (what's happening now), the business of the business (power players and moves), AI and
  technology in entertainment (priority beat, three-bucket sorted), and the money (Wall Street's
  effect on the industry). Every item disclosed if it touches a client or a firm relationship,
  sourced, and produced as a real publish-ready HTML file with structured data — but never
  published; the founder publishes. Full doctrine in `prompts.md`. **Known overlap, not yet
  resolved:** Beat 3 covers nearly identical ground to `industry-intelligence`'s existing AI area
  — see the flag in `press-room`'s own file.

## Handoff rule

Nothing chains automatically. Each agent's output must be handed to the next agent as an
explicit file path (e.g. "read `outputs/market-signals.md` and use it as input"). There is no
orchestrator wiring these together yet, so if a file path isn't stated explicitly, the next
agent has nothing to read.
