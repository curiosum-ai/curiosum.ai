# Curiosum Beta — Session Handoff

**Date generated**: 2026-05-13
**For**: Next session / any model (Claude, GPT, Gemini — all fine)
**Status**: Drop this whole file into a fresh chat as your first message. It contains everything the model needs to be useful without re-reading the entire history.

---

## TL;DR

You're working with **Vatsalya** (`vatsalya@curiosum.ai`), graduate AI Engineer at **Curiosum** — an Auckland-based management consultancy founded 1999, AI-powered since 2023, founder Hamish Carr. We've shipped **Beta 1.1** of the Curiosum homepage to `github.com/curiosum-ai/curiosum.ai`. The custom domain `curiosum.ai` is **not yet live** — DNS at Crazy Domains is blocked on a Distil-end issue, so the GitHub Pages default URL is the current host. Schema canon lives in four MD files in the same repo and in the Curiosum Notion KB.

---

## 1. The team

| Person | Role | Contact |
|---|---|---|
| **Hamish Carr** | Founder. 40+ years in management consulting. ISFP-A. Frequently in Auckland / Wellington / Brisbane (currently Australia). | `hamish@curiosum.ai` · +64 21 717 310 |
| **Vatsalya (Vats)** | Graduate AI Engineer. Primary point of contact. Runs the KB + product. Your direct user. | `vatsalya@curiosum.ai` · GitHub `VatsalyaB` |
| **Jay / Jalaj** | Graduate AI Engineer. Building Distil + product. | `jalaaaj@curiosum.ai` |
| **Carl** | Curriculum + Academy lead. | (in the team) |

---

## 2. What Curiosum is

**Positioning**: *"Curiosum is not just a consultancy that uses AI — it is a consulting operating system."*
**Primary tagline**: *From Curious to Capable.*
**Founded**: 1999. AI-powered since 2023.
**Where**: Auckland · Wellington · Brisbane.

The firm has four commercial offerings — the **Four Doors**:

| # | Door | What it is |
|---|---|---|
| 01 | **Strategy** | AI-inside-out advisers at 2× ahead. 2-week sprint engagements (~$15K). |
| 02 | **Engine** | Proprietary AI infrastructure that collapses 14 weeks of consulting thinking into one session. Live outputs in front of CEOs. |
| 03 | **Academy** | "10 Days Curious" — exec-level side-by-side immersion. *Learn by doing. Lead by knowing.* |
| 04 | **Labs** | Curious DNA embedded — not bolted on. **Not yet delivering** — "Coming soon" status. |

A fifth product, **Distil** (≈ ProfileBuilder), is a separate white-label SaaS for CV + cover-letter generation. **It is a different project. Do not conflate Distil with Curiosum-main work.** Both share infra, but Distil has its own roadmap and the user has explicit rules around it (see §9).

### Locked verbatim lines (canon — never change these)

> *"Intelligence was never the constraint. Curiosity is."* (hero opener)
> *"The technology was never the constraint. It was always belief."* (whitepaper closer)
> *"The AI Age is not an age. It is a toolset. Naming it an age is the mistake of the people selling the tools."*
> *"What question is your organisation most afraid to ask?"* (whitepaper back cover)

### Standing Commitment (every client-facing artefact)

> *"You hired us to hold the vision uncompromisingly. The discomfort you feel when action doesn't meet strategy — that's exactly what you paid for."*

### The four brand archetypes (staff-internal naming only — never expose to clients)
- **BCG** (rigour, evidence-led)
- **Dr Jason Fox** (energy, intellectual provocation)
- **Jimmy Carr** (honesty, willingness to say the uncomfortable thing)
- **Thoughtful Design** (empathy, human-centred)

A client-facing rename has been proposed (Reid / Sage / Frank / Emery) but is **not ratified** in Notion yet — leave the internal names alone in any canonical surface.

### The three-word operating philosophy

**Adapt · Adept · Adopt** — not sequential, a continuous state. Visualised as a continuous loop, not three columns.

---

## 3. Project state — what's live

### Repository
**`github.com/curiosum-ai/curiosum.ai`** — public, default branch `main`.

Logged in as `VatsalyaB` via `gh` CLI with admin scopes. Two org admin invites are out (Hamish + Jalaaaj) — acceptance pending.

### Files in the repo

```
.
├── README.md                            # Project README — deployment, DNS, brand
├── index.html                           # Beta 1.1 homepage (single file, no build)
├── Curiosum_Unified_Schema.md           # Primary schema: design tokens, architecture, 40 patterns
├── Curiosum_Schema_Addendum.md          # May 2026 session decisions + Distil specifics
├── Curiosum_Schema_Notion_Findings.md   # Notion canon — wins on words
├── Curiosum_Admin_Summary.md            # Pre-existing admin summary
├── curiosum_handoff_2026-05-13.md       # This file
├── .gitignore
└── (no CNAME — see §4)
```

### Hosting
**Live URL**: https://curiosum-ai.github.io/curiosum.ai/
**Method**: GitHub Pages, serving from `main` branch root.
**Push to update**: any commit to `main` rebuilds Pages within ~30–60s.

### Version
**Beta 1.1** (commit `fa58477` at time of writing).

| Version | Commit | Notes |
|---|---|---|
| Beta 1.0 | `f9f731c` | Initial homepage. Single-section dot field, basic compare, no theme toggle. |
| Beta 1.1 | `495bcb2` | The current shipped version. Six feedback fixes: theme toggle, full-page dot field with reduced reactivity, age explorer with question-mark transform + 4 hotspots, shuffle-deck Adapt/Adept/Adopt, compare v2 (pyramid ↔ constellation with text in middle), CTA glow + arrow draw. |

---

## 4. What's not done / what's blocked

### Custom domain `curiosum.ai` — BLOCKED

- DNS at **Crazy Domains** needs A/AAAA records pointing to GitHub Pages IPs (full list in `README.md` § DNS setup).
- User reports the DNS update is **blocked by an issue on the Distil end** — so don't push them on it. GitHub Pages default URL is the current host.
- When DNS is ready: re-add `CNAME` file with content `curiosum.ai`, push, then `gh api repos/curiosum-ai/curiosum.ai/pages --method PUT -f "cname=curiosum.ai"`, then enforce HTTPS.
- A premature CNAME binding earlier caused the domain to redirect to a Crazy Domains parking page — we've already removed both the file and the API binding. Don't add it back until DNS resolves correctly.

### Org acceptance
Both admin invites (Hamish, Jalaaaj) were sent but acceptance status hasn't been confirmed by the user. Don't assume they've accepted.

### Possible Beta 2 directions (none committed)
- Connect homepage to a real backend (Stripe / Resend / Supabase per main schema)
- Build Thinking Room v2 demo behind sign-in
- Hook a working "Try Distil" preview from the Engine card
- Add an actual `Reverse Brief Generator` mini-product page
- Light/dark mode polish (some edge cases on the compare-v2 section)
- Mobile interaction polish

---

## 5. The schema canon — read order + priority rule

Three documents matter (plus the pre-existing admin summary):

1. **`Curiosum_Unified_Schema.md`** — the primary reference. Six-layer platform architecture, design tokens, 40 interaction patterns, demo library, build phases.
2. **`Curiosum_Schema_Addendum.md`** — Beta-period gaps from live working sessions: Distil specifics, website IA decisions, Hamish's "voice" build method.
3. **`Curiosum_Schema_Notion_Findings.md`** — distilled directly from the Curiosum Notion workspace. Includes founding-year correction (1999, not 2026), primary tagline correction (*From Curious to Capable*, not *Think differently*), the Four-Stage Delivery Model, Exemplar Intelligence™ methodology, AI Readiness six dimensions, full whitepaper outline, Hamish founder profile, and full verbatim quote list.

### Priority rule (canonical conflict resolution)

> **Notion findings win on words.**
> **Addendum wins on real-time decisions.**
> **Unified schema wins on design tokens.**
> When unsure → ask Vats.

---

## 6. Voice & visual at-a-glance

For anything you generate (HTML, copy, deck, proposal), honour:

### Voice rules
- Not corporate-sterile. Not buzzword AI evangelism. Not academic-impenetrable.
- All four archetypes present simultaneously on every surface. The tension is the point.
- Whitespace earns its keep. Body is 17 px, not 16.
- *"Specific over general · Honest over diplomatic · Active over passive · Their words, made precise."*
- The five-second test: *does it induce thinking or perform authority?* If authority, it is not Curiosum.

### Visual tokens (full list in Unified Schema §1)
- **Brand orange** `#E85A0E` — the verb. Used for promoted lines, rules, signal. Never decoration.
- **Dark theme** ground `#0E0D0B`, paper text `#EEEAE0`.
- **Cream theme** ground `#FAF7F0`, ink text `#1A1814`.
- **Display**: Instrument Serif italic. **Body**: DM Sans (17 px / 1.65 leading / 65ch measure). **Mono**: JetBrains Mono.
- The orange rule (1px solid `#E85A0E`) is the signature divider — beneath promoted lines and section titles, never as fill.

### Sub-brand colours (per offering)
- Strategy: `#E85A0E` (orange) · Engine: `#2F8FD4` (blue) · Academy: `#3FB67A` (green) · Labs: `#7548C7` (purple)

---

## 7. The Beta 1.1 interaction inventory

So you know what's already on the page:

| Section | Interaction |
|---|---|
| **Topbar** | Theme toggle (sun/moon), persists via localStorage |
| **Hero** | Magnetic dot field across full viewport (calm — MAX_PULL 24, FIELD 130, SPACING 50). Custom dot+ring cursor, surface-aware. Orange rule draw on load. |
| **Age explorer** | 4 era tabs (Stone / Industrial / Information / AI). AI click triggers reveal: title strikes through → *Curiosity Age* (orange exp curve). Click curve → morphs to question mark with 4 positioned hotspots (top of hook · base · bottom of stroke · dot) → tooltip on hover/focus/click. |
| **Adapt · Adept · Adopt** | Shuffle deck. Cards enter staggered with rotation+scale on scroll-in. Click → 3D flip reveals description + failure-mode line. One open at a time. |
| **Four Doors offerings** | Card-shuffle expansion on same page (no handoff). Click a door → expanded panel reveals with description + bullets + primary CTA. |
| **Compare v2** | Drag handle. Middle = readable text comparison. Drag left → pyramid graphic (CEO top, frontline bottom). Drag right → constellation graphic (orange `?` knowledge centre, distributed nodes). Auto-demo sweep on first scroll-in. |
| **Evidence** | 4 static cards (coffee / BNZ / IAG / government) with inline SVG art. |
| **White paper** | Cover mock + email-gated form ("I am more curious — give it to me now" / "No thanks, just looking"). |
| **Final CTA** | Centred question + email input. "If you read this far…" hook block beneath. |
| **Footer** | Standing Commitment quote block + 4-col contact grid. |

All buttons get a cursor-following radial highlight via `::before` + orange glow + lift on hover. Arrow icons bob/slide on hover.

---

## 8. Tools you (the model) have available

- **`gh` CLI** — authed as `VatsalyaB`, full repo + admin:org scopes. Use for all GitHub work (repo edits, Pages config, invitations, etc.).
- **Notion MCP** — connected to the Curiosum workspace. Use `notion-search` then `notion-fetch` to read canon pages. Don't write to Notion without explicit instruction.
- **Bash, Read/Edit/Write, Grep, Glob** — standard local file tools.
- **Other MCPs available** — Hermes (cross-platform messaging), Chrome browser, Preview, context-mode search, etc. (See system tool list when starting.)
- **Working directory**: `/home/warren/curiosum.ai/.claude/worktrees/compassionate-golick-07400b/` (a git worktree off the main `curiosum.ai` repo).
- **Git branch**: `claude/compassionate-golick-07400b` — tracks `origin/main` on `github.com/curiosum-ai/curiosum.ai`.

---

## 9. Behaviour rules the user has set

These came from earlier sessions or memory and should not be violated:

1. **Always ask before acting on Distil work.** Clarifying questions first. Distil is a separate product with its own ProductBuilder concerns — do not conflate it with Curiosum-main work.
2. **Don't push to git or change shared state without confirmation.** Destructive ops require explicit go-ahead.
3. **Trust but verify.** Before claiming work is done, confirm the artifact actually contains what you described. (Earlier session: a commit was labelled "Beta 1.1" with feature descriptions that weren't actually in the code — that's the failure mode to avoid.)
4. **No emojis in files unless requested.** Code/markdown/HTML stays unemojied unless the user explicitly asks.
5. **Don't create unsolicited markdown / READMEs.** Only when asked.
6. **Generate a handoff doc as context fills.** (This document is one. Convention: `curiosum_handoff_<date>.md` or `distil_handoff_<date>.md`.)

---

## 10. How to resume cleanly

When you start a new session and have this file pasted in:

1. **Skim §3** (project state) to know what's live.
2. **Skim §4** (what's blocked) so you don't push on DNS.
3. **Open `index.html`** in the worktree to see the current shipped artifact. Don't assume what's in the commit messages — read the actual file.
4. **Open `README.md`** for deployment + DNS instructions.
5. **Spot-check the schema MDs** only if the user's task touches their domain (design tokens, voice, methodology, etc.).
6. **For brand/canon questions**, fetch Notion via MCP before writing — Notion canon wins.
7. **Ask the user what they want to do next.** Don't assume.

---

## 11. Quick reference

### Locked verbatim lines
- *Intelligence was never the constraint. Curiosity is.*
- *The technology was never the constraint. It was always belief.*
- *The AI Age is not an age. It is a toolset. Naming it an age is the mistake of the people selling the tools.*
- *What question is your organisation most afraid to ask?*
- *You hired us to hold the vision uncompromisingly. The discomfort you feel when action doesn't meet strategy — that's exactly what you paid for.*

### Key facts to never get wrong
- Curiosum was **founded in 1999**, AI-powered since 2023. (Not founded 2026.)
- Primary tagline is **"From Curious to Capable."** Secondary is "Learn by doing. Lead by knowing." Legacy (still active) is "Think differently. Transform deliberately."
- Offices: **Auckland, Wellington, Brisbane** — not just Auckland.
- The Age sequence: Industrial → Information → **Curiosity** *(NOW)* → Actualisation.
- The brand archetypes' internal names stay (BCG / Jason Fox / Jimmy Carr / Thoughtful Design). Don't rename them unless explicitly told.
- The Five Brakes: Compliance · Security · Risk · Ethics · Operational readiness.
- The Four-Stage Delivery Model: Discovery → Solution Design → Build → Train.

### Trademarks (filed or pending at IPONZ)
The Age of Curiosity™ · The Curious Age™ · The Age of Actualisation™ · Exemplar Intelligence™ · The Token Test™ · The 2× Ahead Principle™ · Curiosum Engine™ · Thinking Room™

---

## 12. Where to look if something feels off

- **Hosting / DNS questions** → `README.md` § DNS setup.
- **Design system / token questions** → `Curiosum_Unified_Schema.md` § 1.
- **Voice / language / canon corrections** → `Curiosum_Schema_Notion_Findings.md` — and the Notion workspace itself via MCP.
- **Distil-specific** → `Curiosum_Schema_Addendum.md` § A2 (treat as reference, don't act without asking).
- **Founder backstory / history** → `Curiosum_Schema_Notion_Findings.md` § N10, or Notion page "Founder — Hamish Carr".
- **Whitepaper details** (13 sections, pull-quotes, distribution) → `Curiosum_Schema_Notion_Findings.md` § N4.

---

**End of handoff. You're up to speed.** Drop into Vats' next message with a clear "OK — what's the move?" rather than recapping. They know where they left off.
