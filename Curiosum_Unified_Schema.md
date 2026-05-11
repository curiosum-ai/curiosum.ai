# CURIOSUM UNIFIED SCHEMA

**Purpose**: Single canonical reference compiled from ~16 architecture, design system, demo, and interaction artifact files. Use this as the input schema for any HTML generation, page build, or product surface.

**Compiled**: 2026-05-11 — Hamish Carr (Founder), curiosum.ai
**Status**: Snapshot of v1.2 brand tokens + v2 architecture blueprint + v4 interaction patterns

---

## 0. NORTH STAR (Read First)

> **"Curiosum exists to make people more curious than they were a minute ago. Not informed. Not impressed. More alive in their own thinking."**

Every surface, every line, every interaction is judged by the **five-second test**: *Does it induce thinking or perform authority?* If authority — it is not Curiosum.

Curiosum is a management consultancy that sells AI-native transformation. It must be **built AI-natively** — Claude generating, humans curating, AI testing/documenting/deploying at every gate.

---

## 1. BRAND & DESIGN SYSTEM

### 1.1 The 4 Archetypes (Composable, Blendable)

All four poles must be simultaneously present on every surface. Tension is the point.

| Archetype | Source | Pole | Token | Role |
|---|---|---|---|---|
| **Rigour** | BCG | Hypothesis-led, evidence, board-ready | `--strategy` `#E85A0E` | Grid, hierarchy, attribution |
| **Maverick** | Jason Fox | Wizard energy, earned rebellion | `--signal-attention` `#F0A030` | Pattern-breaking provocation |
| **Honesty** | Jimmy Carr | Truth + irreverence, precision without cruelty | `--red` `#FF4B6E` | The line that stops the reader |
| **Empathy** | Thoughtful Design AKL | Systems + human care, alongside not at | `--signal-critical` `#8B7EE8` | Makes the other three bearable |

> Staff-facing IP only — **never visible to end client**.

### 1.2 Color Tokens

#### Brand Orange (The Verb)
| Token | Value | Use |
|---|---|---|
| `--orange` / `--o` | `#E85A0E` | Primary brand, CTAs, headings, rules |
| `--orange-active` / `--o-light` | `#FF7A35` | Hover, active |
| `--orange-hover-tint` | `rgba(232,90,14,0.08)` | Hover backgrounds |
| `--orange-tint-named` | `rgba(232,90,14,0.92)` | Named IP first mention |
| `--orange-rule` | `1px solid #E85A0E` | Signature divider |

#### Dark Theme (Screens, Demos, Thinking Room)
| Token | Value | Use |
|---|---|---|
| `--ground-dark` / `--bg` | `#0E0D0B` | Page background |
| `--ground-dark-raised` / `--bg2` | `#181714` | Cards, topbars, panels |
| `--ground-dark-sunk` / `--bg3` | `#221F1A` | Inputs, sunken surfaces |
| `--bg4` | `#252522` | Deepest nested elements |
| `--paper` | `#EEEAE0` | Primary text on dark |
| `--paper-muted` | `rgba(238,234,224,0.72)` | Secondary text |
| `--paper-dim` | `rgba(238,234,224,0.40)` | Tertiary/meta |
| `--rule-dark` | `#EEEAE0` | Rules full opacity |
| `--hairline-dark` | `rgba(238,234,224,0.10)` | Default borders |
| `--hairline-dark-strong` | `rgba(238,234,224,0.20)` | Structural hairlines |

#### Cream Ground (Default Standing — Documents, Marketing)
| Token | Value | Use |
|---|---|---|
| `--ground-cream` | `#FAF7F0` | Page background |
| `--ground-cream-raised` | `#FEFCF7` | Cards, raised surfaces |
| `--ground-cream-sunk` | `#F2EDE0` | Sunken, code blocks |
| `--ink` | `#1A1814` | Primary text, body |
| `--ink-muted` | `#3D3933` | Secondary text, captions |
| `--ink-dim` | `#7A7468` | Tertiary, placeholders |
| `--rule-cream` | `#1A1814` | Rules at full opacity |
| `--hairline-cream` | `rgba(26,24,20,0.12)` | Default borders |
| `--hairline-strong` | `rgba(26,24,20,0.22)` | Structural hairlines |

#### Semantic Accents (Sparingly)
| Token | Value | Use |
|---|---|---|
| `--signal-positive` / `--grb` | `#3EC87A` | Approved, success, complete |
| `--signal-neutral` / `--blb` | `#4B9FE8` | Info, scheduled, BNZ client |
| `--signal-attention` / `--amb` | `#F0A030` | Pending, in progress, Provocateur |
| `--signal-critical` / `--pub` | `#8B7EE8` | Critical, IAG client, Labs |
| `--red` | `#FF4B6E` | Danger, urgent, board sim |
| `--asb` | `#FCBD1A` | Legacy ASB yellow (chip/badge only) |

#### Sub-Brand Offering Colors
| Offering | Token | Value | Personality |
|---|---|---|---|
| Strategy | `--strategy` | `#E85A0E` | Orange core, Big Idea |
| Engine | `--engine` | `#2F8FD4` | Vibrant blue, Deep in Thought |
| Academy | `--academy` | `#3FB67A` | Lifted green, Open & Energetic |
| Labs | `--labs` | `#7548C7` | Vivid purple, Deep in Thought + ∞ |

### 1.3 Typography

#### Font Stacks
- **Display Serif**: `"Source Serif 4", "Instrument Serif", "GT Sectra", Charter, Georgia` (italic for brand voice)
- **Body Sans**: `"DM Sans", Inter, Söhne, "Helvetica Neue", system-ui`
- **Mono**: `"JetBrains Mono", "DM Mono", "SF Mono", "IBM Plex Mono", ui-monospace`

#### Type Scale (1.250 Major Third, Base 17px)
| Token | Size | Font | Use |
|---|---|---|---|
| `--size-display` | `clamp(3.5rem, 5.5vw+1rem, 6rem)` = 56–96px | Italic serif, -0.02em | Hero promoted lines |
| `--size-headline` | `clamp(2.25rem, 3vw+0.5rem, 3.5rem)` = 36–56px | Italic serif | Section heads |
| `--size-title` | `clamp(1.625rem, 1.5vw+0.5rem, 2.25rem)` = 26–36px | Italic serif | Sub-section |
| `--size-subtitle` | `1.375rem` (22px) | Serif roman | Lead lines |
| `--size-body` | `1.0625rem` (17px) | Sans, 65ch measure | Body copy |
| `--size-body-sm` | `0.9375rem` (15px) | Sans | Captions |
| `--size-meta` | `0.8125rem` (13px) | Sans | Metadata |
| `--size-micro` | `0.6875rem` (11px) | Sans | Footers |

#### Length-Aware Promoted Lines (v1.2)
| Token | Size | Words | Measure |
|---|---|---|---|
| `--line-short` | `clamp(2.5rem, 4vw+0.5rem, 3.75rem)` = 40–60px | ≤8 | 22ch |
| `--line-medium` | `clamp(1.75rem, 2vw+0.75rem, 2.5rem)` = 28–40px | 9–14 | 28ch |
| `--line-long` | `clamp(1.375rem, 1.25vw+0.75rem, 1.75rem)` = 22–28px | 15+ | 36ch |

#### Leading & Tracking
- Leading: `--leading-display: 1.05`, `--leading-headline: 1.15`, `--leading-title: 1.25`, `--leading-body: 1.65`, `--leading-tight: 1.4`
- Tracking: `--tracking-display: -0.02em`, `--tracking-headline: -0.015em`, `--tracking-body: 0`, `--tracking-eyebrow: 0.14em` (uppercase labels)

#### Weights
`400 regular / 500 medium / 600 semibold / 700 bold`

### 1.4 Spacing & Layout

#### Space Scale (4px base)
`--space-1: 4 / -2: 8 / -3: 12 / -4: 16 / -5: 24 / -6: 32 / -7: 48 / -8: 64 / -9: 96 / -10: 128 / -11: 192`

#### Measures
- `--measure-tight: 45ch`
- `--measure-read: 65ch` *(primary reading column — most important layout token)*
- `--measure-wide: 78ch`

#### Grid
- `--grid-max: 1280px`
- `--grid-gutter: 24px` / `--grid-gutter-lg: 48px`
- Topbar: 50px / Voice bar: 36px / Back nav: 36px / Sidebar: 260px

#### Radii
`--radius-none: 0 / -sm: 2 / -md: 6 / -lg: 12 / -pill: 999`

#### Rules
`--rule-hair: 0.5px / -thin: 1px / -orange-weight: 1px` (signature element)

### 1.5 Elevation
- `--shadow-sm: 0 1px 2px rgba(26,24,20,0.04)`
- `--shadow-md: 0 4px 16px rgba(26,24,20,0.06)`
- `--shadow-lg: 0 12px 40px rgba(26,24,20,0.08)`

### 1.6 Motion

#### Durations
`--motion-instant: 80ms / -fast: 180ms / -medium: 320ms / -slow: 600ms`

#### Easings
- `--ease-standard: cubic-bezier(0.2, 0.8, 0.2, 1)` (primary)
- `--ease-entrance: cubic-bezier(0.16, 1, 0.3, 1)`
- `--ease-exit: cubic-bezier(0.4, 0, 1, 1)`

#### Signature Animations
- **Underline reveal** — width 0→100%, 180ms standard
- **Card lift + glow** — translateY(-4px), orange shadow, 250ms
- **Magnetic button** — translates toward cursor
- **SVG stroke→fill** — dasharray/offset
- **Border progress sweep** — circular border progress
- **Engine dot pulse** — `ringPulse 2.5s infinite`
- **Glow ring** — concentric ring expansion
- **Orange rule draw** — 1.4s `cubic-bezier(0.4,0,0.2,1)`
- **Word rise** — translateY(110%→0), 1s standard, per-word stagger
- **Typographic gravity field** — words float toward cursor
- **Magnetic dot field** — dots attracted to cursor
- **Audio frequency bars** — height animation, 120ms ease-out per bar
- **fadeIn** / **scaleIn** — opacity/scale entrance

### 1.7 Breakpoints
`--bp-sm: 640 / -md: 860 / -lg: 1100 / -xl: 1400`

### 1.8 Core Components

#### Identity
- **North Star block** — left border 18pt orange, fill `#FFF4EF`, Instrument Serif italic 16–20px. Required in all demos, reverse briefs. Variants: Standard / Wide-Document
- **Archetype strip — all four** — BCG (orange) · Provocateur (amber) · Visionary (blue) · Thoughtful Design (purple). Staff-only.
- **Back nav** — 36px dark2, dim text, hover→orange, `← Back` pattern

#### Status Badges
- Approved (green `#3EC87A` filled + check)
- Scheduled (blue `#4B9FE8` filled)
- In Progress (amber `#F0A030` filled)
- Pending (transparent + dim)
- Live (cyan `#00D4FF`, Star Trek demo only)

#### Typographic Patterns
1. **Promoted line + orange rule** — 1px orange rule (32–48px wide) + italic serif display, always paired
2. **Earned build** — long-form sans body (17/1.65, 65ch) building to a key line
3. **Orange bold inline** — 700 weight, ≤12 words, once per section
4. **Orange tint mention** — named IP (Curiosum Engine, Exemplar Intelligence) at 92% orange, 500 weight, first mention only
5. **Verbatim line** — display italic serif, 96px top/bottom, source attribution
6. **Type scale display** — all sizes rendered with specs

#### Frame & Layout
- Page header (eyebrow + title + subtitle + warning banner)
- Section label (9–11px DM Sans 700, 0.14em tracking, UPPERCASE, orange, with rule below)
- Diagram node (circular SVG, hover reveals)
- Topbar (50px fixed, dark2, brand mark + section + view toggle Staff/Client)
- Sidebar (260px fixed, nav + search + filter chips)
- Content grid (2-col → 1-col <860px)
- Tray (fixed bottom: selected item + copy code + actions)

#### Form
- Search input (12px, border transition, 6px radius, dark3 bg)
- Filter chip (9px DM Sans 700, 0.12em tracking, 0.2s all, 20px radius)
- Toggle button (9px mono, 0.12em tracking, 0.2s all)
- Code input (mono 10px, border + bg transitions)
- Candidate tab (orange bottom border on active, 180ms)

#### Interaction Demos
- Cursor variants (Dot + Ring; Cream Paper)
- Magnetic cursor
- Eye pupil follower
- Audio frequency bars
- Living diagram
- Forty eyes grid
- Drag compare slider
- Token meter (orange gradient fill, 450ms)
- QM Lightbulb (stroked SVG reveal)

### 1.9 Document Standards (DOCX/PDF)

#### Body
- DM Sans 11pt `#111110`, leading 1.65, measure 65ch

#### Headings
- Georgia italic `#111110`
- First mention: all-caps orange label + 2pt orange rule + 6pt space

#### North Star Block (DOCX)
- Left border 18pt `#E85A0E` / fill `#FFF4EF` / Georgia italic
- Appears in every reverse brief & proposal

#### Page Layout (DOCX)
- Margins 1 inch (1440 DXA), A4 (11906×16838)
- Header: *Curiosum* (italic orange) + Document Type · Confidential (right-aligned), orange bottom rule
- Footer: *Curiosum Management Consulting · curiosum.ai · Page N* (DM Sans 8pt `#888880` centered)
- Surfaces: `#FFFFFF` page, `#F7F6F2` section, `#111110` primary text, `#888880` meta, `#E8E7E0` border

#### Web Report PDF (Apr 2026)
- Playwright HTML→PDF, `print_background=true`
- A4, margins T14mm/B12mm/L0mm/R0mm
- Header: dark2 bg, primary left, muted subtitle right, 9px Helvetica
- Footer: dark2 bg, muted left, page right, 8px Helvetica
- Filename suffix `_Web_Style_v2.pdf`
- Wait 2000ms for fonts before render
- Nav bars hidden via `@media print { display:none }`

### 1.10 Voice & Tone Rules

| Rule | Example / Mechanism |
|---|---|
| **Specific over general** | "BNZ's Head of Risk becomes the biggest champion — the moment he sees AI makes risk visible in real time, not quarterly." |
| **Honest over diplomatic** | Name fears directly. Use *Tension: [uncomfortable truth]*, then reframe. |
| **Active over passive** | "Curiosum designs and facilitates" not "The workshop will be designed to…" |
| **Their words, made precise** | North Star always client language, sharpened by Curiosum. |
| **All four archetypes always present** | Evidence · Uncomfortable truth · North Star · People first |
| **Standing Commitment** | "You hired us to hold the vision uncompromisingly. The discomfort you feel when action doesn't meet strategy — that's exactly what you paid for." |
| **Orange as typographic verb** | `#E85A0E` is canon. It signals *this has been considered* — never decoration. |
| **Whitespace as confidence** | Body is 17px not 16px. Reading bigger signals trust in the prose. |

### 1.11 Core IP Lines (verbatim, never lose)

> "You are not making a financial decision. You are making a civilisational decision."
>
> "This is not what consultants produce after a meeting. This is what the Engine produces during one."
>
> "Not three weeks later. Not hours later. Now."
>
> "The technology was never the constraint. It was always belief."
>
> "We are in our Star Trek ship, going where no one's gone before."

### 1.12 Identity & Contact

- **Domain**: curiosum.ai (as of Apr 12 2026; supersedes curiosum.co.nz)
- **Founder**: Hamish Carr — hamish@curiosum.ai — +64 21 717 310
- **Firm**: Curiosum Management Consulting (long) / Curiosum (short)
- **Signature line**: *"Think differently. Transform deliberately."*

### 1.13 Version Stamps
- Brand Master v1.1 (Apr 2026) — text brightness corrected, domain updated
- Curiosum Tokens v1.2 (27 Apr 2026) — ink-muted/dim, paper-muted/dim lifted; hairline-strong added
- Typography Specimen v1.1 — light cream lifted, 1px orange rule
- Web Report Style v2 — Playwright dark theme preservation

---

## 2. PLATFORM ARCHITECTURE (6 LAYERS)

### Layer 1 — Presentation Surfaces
- **Public Website** (curiosum.ai) — Marketing, blog, lead capture
- **Thinking Room** — Staff-only workspace (v1: Hamish + team, full Engine access)
- **Client Room** — Per-client slug, session transcripts, document delivery, commenting
- **ProfileBuilder** — First white-label SaaS product (CV/cover letter/LinkedIn)
- **B2B Engine API + Partner Portal** — Metered access for partner firms
- **Academy LMS** — Courses → modules → lessons, progress tracking, certificates

### Layer 2 — Identity & Access
- **Supabase Auth** — Magic link, 7 role types
- **RLS on every client-facing table** — Database-level security
- **7 user types**: Admin, Staff, Client, Subscriber, Consultant, B2B Partner, Guest
- **Engine Mode toggle** — Curiosum (full IP stack) vs Open (model-only, context-only)

### Layer 3 — Curiosum Engine (Core IP)
- **Model router abstraction** — `packages/engine/model-router.ts` only. System-agnostic. Anthropic / OpenAI / Google supported.
- **Prompt library** — Database-driven, Hamish-editable (no code deploy required)
- **Archetype blender** — Composable system prompts (BCG / Maverick / Honesty / Empathy)
- **Engine Mode flag** — Every call carries mode: `curiosum` or `open`
- **Server-side proxy** — API key NEVER in browser

### Layer 4 — Intelligence Layer
- **Learning Engine** — Quality signals → promotion queue → Hamish approves → master library
- **Personal Playbook** — Per-user living record, auto-populated from Engine activity, feeds master library with consent
- **Exemplar Intelligence™** — Find the exemplar first, never start blank
- **Semantic search** — pgvector across all content
- **Session transcript pipeline** — Audio → Whisper → Engine context injection

### Layer 5 — Commercial Layer
- **Stripe Checkout** — One-off purchases ($9–15 ProfileBuilder)
- **Stripe Billing** — Subscriptions by tier
- **Stripe Metered** — B2B Engine API usage
- **Zoho CRM** — Lead → opportunity → client lifecycle (already live)
- **Document versioning** — Draft → Internal Review → Client Review → Approved → Delivered

### Layer 6 — Infrastructure & Integrations

| Layer | Tool | Why |
|---|---|---|
| Frontend | Next.js 14 (App Router) | SSR + API routes, Vercel-native |
| Auth + DB | Supabase | Auth + Postgres + Storage + Realtime + pgvector in one |
| AI | Anthropic API (Claude) | Server-side only, model-agnostic router |
| Payments | Stripe | Checkout + Billing + Metered |
| Email | Resend (transactional), Zoho Campaigns (marketing) | Zoho already live |
| Testing | Vitest (unit/integration), Playwright (E2E + PDF) | AI-generatable |
| CI/CD | GitHub Actions | Tests, lint, type-check, deploy |
| Deploy — site | Netlify | Already set up |
| Deploy — app | Vercel | Best Next.js |
| Analytics | PostHog | OSS, generous free tier |
| CRM | Zoho CRM | Already live |
| Transcription | Whisper API | Best accuracy |
| Web search | Brave Search / Tavily | Real-time exemplar grounding |
| Video (Phase 2) | HeyGen | API-driven |
| Voice (Phase 2) | ElevenLabs | Hamish persona |

### Critical Architectural Rules (ADRs)
1. **Monorepo** — schema + API + frontend + tests + docs = atomic
2. **Model router abstraction** — only path to AI providers
3. **Supabase as primary platform** — replaces Auth0, RDS, S3, Pusher, vector DB
4. **Engine Mode flag** — required on every Engine call
5. **RLS on all client tables** — database-level, not app-level
6. **IP timestamping** — `created_at` + Git commit hash, automatic on every output
7. **Test-driven development** — test spec before feature
8. **ProfileBuilder as first white-label** — forces white-label infra proof in 3–4 weeks

### AI-Native SDLC (5 stages)
1. **Generate** — Claude Code 80%, human 20%
2. **Review** — AI-assisted (naming, security, test coverage, RLS)
3. **Test** — AI-generated unit / integration / E2E
4. **Document** — As-built docs from schema changes, API endpoints, prompts
5. **Deploy** — Auto: branch → tests → staging → production

### Claude's Three Roles (until tech lead onboards)
- **Architect** — schemas, API contracts, structures + rationale
- **Generator** — first-pass scaffolding: SQL, routes, tests, docs
- **Reviewer** — naming, security, testing, RLS conformance

**Claude cannot do**: deploy decisions alone, approve production schema changes, override human product judgment.

---

## 3. FEATURE CATALOGUE

### 3.1 Seven User Types
1. **Admin** — Hamish + ops; manages prompts, people, billing, learning queue
2. **Staff** — Consultants; full Engine access, Thinking Room, exemplar library
3. **Client** — Per-client room access, document review/comment, session replay
4. **Subscriber** — Paid SaaS access (ProfileBuilder, micro-products)
5. **Consultant** — Contracted; visa flags, IP assignment, scoped access
6. **B2B Partner** — White-label tenant; API key, metered billing, partner portal
7. **Guest** — Public site, lead capture, gated content

### 3.2 Five Offerings (Four commercial + one white-label)

1. **Strategy** — Helps orgs ask different questions. *Reverse Brief, North Star, capability mapping.*
2. **Engine** — AI-native transformation infrastructure. *Live outputs in front of CEOs. Exemplar Intelligence™.*
3. **Academy** — Builds knowledge-worker DNA. *Four-week hands-on, fully supportive.*
4. **Labs** — Injects curiosity DNA. *Pace, nimbleness, right thinking patterns.*
5. **ProfileBuilder** *(white-label)* — Personality / CV / cover-letter SaaS. Week 3–4 launch.

### 3.3 Named Products & Core IP

| Name | What It Is |
|---|---|
| **Exemplar Intelligence™** | Find the exemplar first, never start blank |
| **Reverse Brief** | First SaaS product; structured input → output guide |
| **ProfileBuilder** | White-label personality/CV product (Week 3–4) |
| **North Star** | Canonical positioning statement (per client, per surface) |
| **Engine** | The Curiosum core; AI model router; never Claude-locked |
| **Engine Mode** | Curiosum / Open toggle |
| **Thinking Room** | Staff-only workspace |
| **Client Room** | Per-client workspace |
| **Age of Curiosity** | Master white paper; canon source for all language |
| **The Felt Centre** | Non-negotiable centre beneath all disciplines |

### 3.4 The 5 Tensions (Bias-to-Action Honesty)

| # | Pole | What It Means |
|---|---|---|
| 1 | Curious — not whimsical | Sharp enough for a Head of Transformation to table in a board meeting |
| 2 | Provocative — not edgelord | Describes reader's actual situation; no deflection |
| 3 | Rigorous — not corporate | Discipline without distance; no hedging into "considerations" |
| 4 | Caring — not soft | Made with care but will not soften the work; duty to truth |
| 5 | Generous — not wasteful | Whitespace earns weight, not effort; no page-filling |

### 3.5 The Operating Rule (4 non-negotiable paragraphs)
1. North Star + AoC voice trump the kit. Felt centre wins. Editorial restraint is one tone available, never the default.
2. Surfaces judged by *reach*, not output. Do they reach for curious-moments, or default to WSJ patterns?
3. If a pattern needed for curiosity doesn't exist in kit, **build it**. Kit grows by insufficiency.
4. Five-second test: Does it induce thinking or perform authority? If authority, it is not Curiosum.

### 3.6 Design Signature Moves
- **Orange Rule** — beneath promoted lines and section titles, never as fill
- **Promoted Line** — held in serif italic, paired with orange = canon status
- **Threshold** — opening moment of restraint on every surface
- **Earned Reveal** — core argument held back until build earns it
- **Cream Ground** — default standing (not corporate-white, not agency-black)
- **Whitespace as Confidence** — silence that makes the next line land

---

## 4. DEMO LIBRARY & INTERACTION PATTERNS

### 4.1 Existing Demos (8)

| # | Name | Purpose | Layout | Theme |
|---|---|---|---|---|
| 1 | **BNZ Academy** | Educational content presentation | Center-column doc, accent bars | Dark, orange + green + cyan |
| 2 | **BNZ Reverse Brief** | Strategic brief document | Max 800px doc, North Star + Tension Cards + First Moves | Dark, orange |
| 3 | **BNZ Thinking Space** | Real-time collaboration workspace | 260px sidebar + main, status dashboard, doc grid | Dark, BNZ blue `#4B9FE8` |
| 4 | **Engine Demo BNZ** | AI engine processing visualization | 3-col split: transcript / engine column / output | Dark, orange gradients |
| 5 | **Engine Demo IAG** | AI engine processing (insurance) | 3-col split (identical structure) | Dark, IAG purple `#8B7EE8` |
| 6 | **IAG Board Brief** | Executive narrative document | Centered 860px doc, Simon Voice, pull quotes, North Star | Dark, purple + orange + green |
| 7 | **IAG Thinking Space** | Real-time collab workspace (IAG) | Sidebar + main (matches BNZ) | Dark, purple |
| 8 | **IAG Use Case 1** | Light-mode future vision card | Card 860px, dark head + light body, scenario cards | **Light cream `#F7F6F2`**, orange |

### 4.2 The 40 Interaction Patterns (P01–P40)

#### Pattern Gallery v3 (Dark, Category-Based) — P01–P21
21 patterns arranged in card grid. Categories tagged (AoC / Assurance / Edgy). Anchor:
- **P21 — Token Test Live**: Q&A scorecard, orange meter ring (SVG stroke-dashoffset), chosen/unchosen states, nav buttons

#### Pattern Gallery v4 (Language-Led, Dark) — P31–P40
- **P31 — Token Meter (fillable)**: Prompt → checkboxes → live fill bar 0–100% + tick marks + numerical readout
- **P32 — Hierarchy Collapse**: SVG nodes in tiers; hover triggers tier flip with orange borders; caption updates
- **P33 — Exemplar Search**: Centered question → search field → cascading staggered result rows
- **P34 — Voice as Dials**: 4 labeled sliders (poles at extremes) driving centered text readout
- **P35 — Pyramid Breaks**: SVG pyramid; CTA breaks into scattered pieces
- **P36 — Script to Discretion**: Split (scripted left | arrows | natural language right), toggle switches
- **P37 — Many Loops**: SVG feedback loops + 3-stat animated readout
- **P38 — The Crossing**: Draggable vertical divider splitting "from" (dark) and "to" (warm)
- **P39 — Standing Commitment**: Document preview + rotated stamp overlay; toggle reveals/hides
- **P40 — Be Interesting**: Text input + submit → animated claim reveal + meta attribution

#### CTAs v1 (Dark, 8 CTA Interactions)
- **C01 — Question Back**: Large serif question → underlined input → arrow button reveal on fill
- **C02 — 90-Second Test**: Corner timer, multi-choice chips, animated progress, result reveal
- **C03 — Two Doors**: Centered question → 2 doors (1fr | auto | 1fr) → hover brightens
- **C04 — Held Breath**: Countdown (MM:SS:cs) → orange dot separator → action button
- **C05 — Mirror**: Input controls → live serif text mirror below + flash animation
- **C06 — Curious Decline**: Yes/No → reveals follow-up list on no
- **C07 — Conversation Starter**: Serif prompt + italic input → live email preview → send
- **C08 — Self Diagnostic**: Multi-step questionnaire (display:none step toggle)

#### Engagement v1 (Dark, 7 Engagement Visuals)
- **M00 — Connective Map**: SVG node graph, animated lines (dashed → solid)
- **E01 — Architecture Blueprint**: Stacked clickable layers reveal "seams"
- **E02 — SDLC Pipeline**: Horizontal 5-stop track, blob slides L→R, meta cards
- **E03 — Product Lifecycle**: Curved SVG line on grid, stroke-dasharray, band reveal
- **E04 — Delivery Plan**: Sprint bars on timeline, "DEMO" label reveals, release borders
- **E05 — Programme Org**: 3-pod grid, RACI table reveal, role-colored badges (R/A/C/I)
- **E06 — Sourcing Model**: Stacked area chart (build/buy/borrow), hover fills

#### Geometries v1 (Dark, 10 Geometric Patterns)
- **G01 — Concentric Rings**: Hover-scaled SVG rings, readout updates
- **G02 — Squares → Star**: Rotating squares (transform-origin center), state toggle
- **G03 — Flipping Tiles**: 3D flip (rotateY 180), front/back, staggered click
- **G04 — Exploded Stack**: 5 layers in 3D perspective; toggle translates outward
- **G05 — Pyramid → Constellation**: Nodes scatter from pyramid to random positions
- **G06 — Collapsing Panels**: 4-col → 1-col with centered merge
- **G07 — Stepping Forward**: 5 numbered steps reposition on track, "lit" styling
- **G08 — Hexagonal Grid**: Clip-path hexagons, glow spread on hover/click
- **G09 — Hierarchy Ring**: Nodes move from vertical tree → circular layout
- **G10 — Circle Split**: 5 arc segments translate outward

#### Experience Visuals v2 (Dark, 7 Movement-Led)
- **V01 — Slide vs Stop**: Draggable vertical divider (ew-resize), clips reveal L/R
- **V02 — Eight Seconds**: Countdown auto-advances states, progress fills, text fades
- **V03 — Four Poles**: Side dials + output, draggable handles (left:% on drag)
- **V04 — Five Tensions**: Draggable puck on each track, middle zone dashed, settles to center
- **V05 — Surfaces Grammar**: Tab-based screen cycles, staggered fade in/out
- **V06 — Whitespace as Confidence**: Two full-screen states, whitespace decreases on toggle
- **V07 — Reading Test**: Auto-walking 5-state sequence (time + feeling + action), animated progress

### 4.3 Animation Philosophy (6 Beats)
1. **Page as Pitch** — every page is a sales argument, not a brochure
2. **Curiosity as Control Surface** — interactions invite, never demand
3. **Every Motion Carries Argument** — no decorative motion
4. **Restraint as Signal** — less motion = more trust
5. **Language Earns Animation** — animations bow to copy
6. **Visitor Leaves Trace** — interactions leave residue (selection, history, state)

### 4.4 Dosage Principle
- ≤1 hero animation per surface
- ≤3 micro-interactions per scroll-depth
- Animations must hold up to **second view** (no novelty-only delight)

### 4.5 Unified Pattern Summary

#### Recurring Interaction Patterns
1. Animated status indicators (orange/green/blue pulse)
2. Left-border accent blocks (3px + soft bg)
3. Hover-brightening (border + bg)
4. Dashed lines & separators (rgba transparencies)
5. SVG-driven visualizations (`stroke-dasharray`, `cx`/`cy`, `fill`)
6. 3D transforms (`rotateX/Y`, `translateZ`)
7. Draggable controls (`cursor-grab` + listeners)
8. Staggered animations (nth-child delays)
9. State class toggles (`.on`, `.active`, `.lit`, `.chosen`, `.flipped`)
10. Full-screen overlays (modal-like step sequences)

#### CTA Styling (Deduped)
```css
/* Primary */
background: var(--orange); color: var(--ink); border: 1px solid var(--orange);
:hover { opacity: 0.88; }

/* Secondary */
border: 1px solid var(--line); color: var(--muted);
:hover { border-color: var(--orange); color: var(--orange); }

/* Toggle/Chip */
border: 1px solid var(--line); background: transparent;
.on { background: var(--orange); color: var(--ink); border-color: var(--orange); }

/* Input Focus */
border-bottom: 1px solid var(--orange);

/* Disabled */
opacity: 0.3; cursor: not-allowed;
```

#### Layout Archetypes
1. **Center-Column Document** — max 800–860px, padding 3–6rem
2. **Sidebar + Main** — 260px sidebar, flex layout
3. **3-Column Split** — left | center engine | right
4. **Card Grid** — 3–6 cols, gap 8–20px, breakpoint 720–760px
5. **Full-Screen State Machine** — flex column, opacity/transform on state class

---

## 5. BUILD PRIORITIES (Phased Roadmap)

### Phase 0 — NOW (Day 1)
- Deploy website to Netlify + DNS
- GitHub repo + IP timestamping ritual
- Supabase project live
- All graduates sign IP assignment
- Naming conventions doc written

### Phase 1 — Week 1 (Foundation)
- Full database schema (multi-tenancy, RLS on all tables)
- Auth (Supabase magic link, 7 role types)
- Model router abstraction (single `engine/model-router.ts`, no provider lock-in)
- Prompt library DB (Hamish-editable, no code deploy)
- Server-side Engine proxy (API key never in browser)
- People/HR system (contracts, visa flags, onboarding)

### Phase 2 — Week 1–2 (Internal Intelligence)
- Thinking Room v1 (staff login, Engine chat, mode toggle, exemplar library)
- Personal Playbook (auto-populated from Engine activity)
- Admin dashboard (people, CRM sync, PostHog embed)
- IP timestamping pipeline (`created_at` + Git hash)

### Phase 3 — Weeks 2–4 (First External Product)
- **ProfileBuilder.ai** (white-label routing, domain, branding config)
- Input pipeline (6-step flow, PDF extraction, web search)
- Output templates (CV, cover letter, LinkedIn)
- Stripe Checkout ($9–15, watermarked free tier)
- Launch checklist (payment, mobile, all personas)

### Phase 4 — Weeks 3–6 (Client Engagement)
- Client Room v1 (per-client slug, RLS verified, doc display, commenting)
- Session transcript pipeline (audio → Whisper → Engine context)
- Document versioning (Draft → Internal Review → Client Review → Approved → Delivered)
- Learning Engine v1 (quality signals, promotion recs, exemplar extraction)

### Phase 5 — Weeks 5–10 (SaaS Scale)
- Stripe Billing (subscription tiers)
- Usage metering
- White-label micro-products (Reverse Brief Gen, Board Narrative, Exemplar Finder, Zombie Pilot Killer)
- Semantic search (pgvector)
- Academy foundation (courses → modules → lessons, progress, certificates)
- B2B Engine API (keys, partner portal, metered billing)

### Phase 6 — Months 2–3 (Intelligence & Content)
- Content automation (Hamish persona → LinkedIn, articles)
- AI video gen (HeyGen)
- AI Boardroom product (calendar + meeting capture)
- Full Academy (all content, all courses)
- Business process builder
- Sustainability parameter
- Consultant portal (white-label tenants for other firms)

---

## 6. OPEN QUESTIONS & RISKS (Master Tracker — 14 Apr 2026)

### Product / Commercial
- Offerings heading unresolved ("Four ways in / One system forward")
- Reverse Brief Generator product brief shape
- GTM plan (speaker circuit? micro-content? Minister Collins outreach?)
- Pricing model (day rates? retainers? SaaS tiers?)
- "Kostia equivalent" key hire

### Legal / IP
- **IPONZ filings OVERDUE**: Curiosum™, Engine™, Exemplar Intelligence™, Thinking Room™, Age of Curiosity™
- Company structure (trading entity? holding? directorship?)

### Financial
- R&D tax credit setup (15% RDTI + loss credit, min $50k/yr spend)
- Accountant brief before Year 1 closes
- P&L / financial model not built

### Operational
- Daily operating rhythm not structured
- Offramp definition ("don't become Charlie" — exit ceiling?)
- Kostia-like operations scaler

---

## 7. SCHEMA INDEX (Source Files)

| File | Role | Status |
|---|---|---|
| `curiosum_platform_architecture.html` | Interactive 6-layer diagram (v2, 15 Apr 2026, 57 components) | Canonical |
| `curiosum_platform_architecture_blueprint.html` | v1 blueprint (5 layers) | Superseded |
| `Curiosum_Platform_Architecture_Blueprint_v2.md` | Canonical markdown, 22 gaps folded in | **Source of truth** |
| `curiosum_feature_catalogue.html` | 3-tab catalogue (Why/By user/By offering), 7 users, 5 offerings | Canonical |
| `curiosum_architecture_review_extended.html` | Gap analysis (8 tabs: Gaps/ProfileBuilder/Archetypes/Realtime/B2B/Docs/HR/Matrix) | Canonical |
| `curiosum_design_catalog_v2.html` | Design tokens + components catalog | Canonical |
| `curiosum_design_system_master.html` | Master design system reference | Canonical |
| `Curiosum_Brand_Master.html` | Brand standards (v1.1 Apr 2026) | Canonical |
| `Claude Design Kit/foundations/curiosum-tokens.css` | Token definitions (v1.2, 27 Apr 2026) | Canonical |
| `Claude Design Kit/foundations/typography-specimen.html` | Type specimens (v1.1) | Canonical |
| Interaction Artifacts v1–v4 (40 patterns) | Pattern gallery, CTAs, engagement, geometries, experience visuals | Canonical |
| ASB demos × 8 (BNZ + IAG variants) | Existing reference implementations | Canonical |

---

**END OF SCHEMA**

This document is the canonical reference for any HTML page, demo surface, deck, or document generated for Curiosum. When in doubt: **North Star + AoC voice trump the kit.** The five-second test is the only test that matters.
