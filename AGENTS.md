# Mirra docs — writing instructions

## About this project

- Documentation for **Mirra** — drop-in mirrors for third-party APIs (Stripe, Resend, Twilio, Plaid, Auth0, and the rest of application infrastructure).
- Mintlify site. MDX with YAML frontmatter. Config in `docs.json`. Preview with `mint dev`.
- Source of truth for content: `../project_docs/` (product description, whitepaper, thesis, technical spec).

## Terminology

- **Mirror** — a faithful, stateful implementation of a third-party vendor's API that Mirra provides. Never "twin", "fake", "stub", or "mock".
- **Session** — one isolated run of one or more mirrors. Ephemeral (auto-expires) or persistent.
- **Scenario** — a markdown file with setup, prompt, and tagged success criteria that an agent or test run is evaluated against.
- **[D] criterion** — deterministic, checked programmatically against mirror state.
- **[P] criterion** — probabilistic, judged by an LLM from the trace and final state.
- **Vendor** — the real third-party service being mirrored (Stripe, Resend, etc.). Never "provider" or "upstream".
- **Seed** — the initial state a mirror starts a session with.
- **Drift** — a divergence between mirror behavior and the live vendor API.

## Style preferences

- Active voice, second person ("you point your code at the mirror", not "code can be pointed").
- Sentence case for headings (`## Request routing`, not `## Request Routing`).
- One idea per sentence. Short is better than complete.
- No marketing voice. Assume a senior engineer is reading.
- Bold for UI elements and emphasis: "Click **Settings**", "the mirror **must** verify signatures".
- Code formatting for file names, commands, paths, env vars, HTTP status codes, package names.
- Inline vendor names are plain text (Stripe, Resend). Command names are code (`mirra up`).

## Code-block conventions

- Always include a language tag.
- `bash` for shell. `ts` or `typescript` for TS. `python` for Python. `http` for raw HTTP. `json` for JSON.
- Show real Mirra output, not placeholders. Example: `session ses_a7k2 ready in 1.8s`, never `session <id> ready in <time>`.
- Prefer complete runnable snippets over fragments.

## Content boundaries

- **Public facing.** No internal architecture decisions, no competitive sniping (don't name Archal, Arga, or competitors).
- **No pricing specifics** beyond "free / Pro / Team / Enterprise" tier names — pricing lives on the landing at mirra.run/pricing.
- **No NPS claims, no case studies** until customers agree. "Teams using Mirra ship 80% fewer integration bugs" is fine — it's our measured claim, not a customer quote.
- Never document internal admin endpoints (the `/_mirra/*` admin paths).
- Never show real API keys or tokens even in examples. Use `sb_secret_...` or `stripe_sk_test_...` patterns.

## Components available

Standard Mintlify components we lean on:
- `<CardGroup>` + `<Card>` for landing cards
- `<Columns>` for 2-3 column splits
- `<Steps>` + `<Step>` for walkthroughs
- `<Tabs>` + `<Tab>` for language / platform variants
- `<AccordionGroup>` + `<Accordion>` for FAQ-style content
- `<Note>`, `<Warning>`, `<Info>`, `<Tip>` for callouts
- `<CodeGroup>` for same-content-multiple-languages
- `<ParamField>` for API parameter docs
- `<ResponseField>` for API response docs
