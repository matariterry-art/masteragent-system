# Runbook

Placeholder for exact commands and invocation syntax. What follows is the full agent roster,
running order, and the one hard rule about handoffs.

## Agent roster

**Signal-to-conversion chain** (run in this order):

1. `media-contact-builder` — builds and maintains the Hollywood calendar and contact
   architecture. Run first, and keep it current — everything else depends on its dates.
2. `market-signal-researcher` — reads the calendar, researches market signals (demand, pricing,
   access), writes `outputs/market-signals.md`.
3. `offer-architect` — reads the signal report, defines or adjusts the offer. (Stub — prompt
   body not yet written.)
4. `content-angle-strategist` — reads the offer, defines content angles. (Stub — prompt body
   not yet written.)
5. `social-content-engine` — reads the content angles and the calendar, builds the Instagram
   posting calendar and website news feed.
6. `conversion-system-builder` — reads the content angles, builds the conversion mechanics.
   (Stub — prompt body not yet written.)

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

## Handoff rule

Nothing chains automatically. Each agent's output must be handed to the next agent as an
explicit file path (e.g. "read `outputs/market-signals.md` and use it as input"). There is no
orchestrator wiring these together yet, so if a file path isn't stated explicitly, the next
agent has nothing to read.
