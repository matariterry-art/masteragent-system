# Runbook

Placeholder for exact commands and invocation syntax. What follows is the full agent roster,
running order, and the one hard rule about handoffs.

## Agent roster

**Signal-to-conversion chain** (run in this order):

1. `media-contact-builder` — builds and maintains the Hollywood calendar and the trade
   journalist/editor and event-partner contact architecture. Run first, and keep it current —
   everything else depends on its dates. (Talent-booking-route research now lives in
   `booking-desk`, not here.)
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
- `media-desk` — invoke whenever a press release, media alert, booking notice, product
  announcement, or a batch of personalized pitches needs to be written. Writes only — never
  sends. Reads targets from `outputs/contacts/` once `contact-database` exists; researches its
  own targets until then, always deferring to any contact the founder supplies directly.
- `client-desk` — invoke for day-to-day client work: appearance prep, materials, outreach briefs
  (handed to `media-desk` for the actual copy), and campaign timelines. Always reads the relevant
  `clients/<client-slug>.md` file first. First active client: Freda Payne.
- `booking-desk` — maintains booking intelligence and routes across TV, radio, podcasts, live
  events, red carpets, and the separate music-radio/chart lane. Run continuously to keep it
  current. Founder-supplied contacts (including personal numbers) go in
  `outputs/booking/private-contacts.md`, kept apart from professionally-researched contacts.
  Works against Freda Payne by name in the live-booking lane; flags relevant finds to
  `client-desk`.
- `industry-intelligence` — run weekly, standing brief across craft standard, AI in PR/
  entertainment, distribution shifts, the business, and tools. Every finding sorted into
  shipped/demoed/announced-only, with a plain-English "what this means for PR STARPOWER" line.
  Surfaces findings; doesn't act on them — flags relevant ones to the agent that owns that area.

## Handoff rule

Nothing chains automatically. Each agent's output must be handed to the next agent as an
explicit file path (e.g. "read `outputs/market-signals.md` and use it as input"). There is no
orchestrator wiring these together yet, so if a file path isn't stated explicitly, the next
agent has nothing to read.
