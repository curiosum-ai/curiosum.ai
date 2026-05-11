# CURIOSUM SCHEMA — ADDENDUM v1

**Compiled**: 2026-05-11 from team meeting transcripts (May 7–11 2026)
**Status**: Supplements `Curiosum_Unified_Schema.md`. Items here are gaps/clarifications/decisions from live working sessions between Hamish, Vatsalya, Jay, and Carl.

> Source: 7 transcript blocks of internal calls discussing Distil, website rebuild, Academy 10-Days Curious, ASB / IAG / PK proposals, design catalog v2, and architecture priorities.

---

## A1. CLIENT-FACING ARCHETYPE NAMES

Curiosum's 4 staff-only archetypes (Rigour / Maverick / Honesty / Empathy) **must never be exposed to clients** as "BCG / Jason Fox / Jimmy Carr / Thoughtful Design." Hamish + Vats agreed on these client-facing renames:

| Internal (Staff) | Client-facing Name | Tagline | Mapping |
|---|---|---|---|
| BCG / Rigour | **Reid** *(read for reason)* | "When trust is earned by structure" | The Rigorous |
| Jason Fox / Maverick | **Sage** *(strategist)* | "When the question needs a different shape" | The Provocateur / Strategist |
| Jimmy Carr / Honesty | **Frank** *(frank)* | "When the truth needs saying" | The Honest |
| Thoughtful Design / Empathy | **Emery** *(empathy)* | "When the room needs holding" | The Empathetic |

**Display rule**: Refer to these collectively as **"Our Voice"** (e.g., *Curiosum's four voices in one*). Never list the staff names on any external surface.

**Voice Dial component**: 4 labeled sliders → centered text readout (matches P34 in main schema). Each dial is a preset; users can adjust to blend. Used staff-side only for system prompt composition.

---

## A2. DISTIL (ProfileBuilder Implementation)

**Distil ≈ ProfileBuilder.ai** — the first white-label SaaS. Distinct from main Curiosum schema, but shares Engine + design system.

### Product
- **What**: CV + cover-letter generator. Inputs (master CV PDF + job description) → tailored CV + cover letter outputs.
- **Engine**: Claude API (primary); DeepSeek v3 evaluated as fallback (~$0.08 vs $0.30/gen, but 5–6min vs 1.5min — **stay on Claude**).
- **Web search**: Tavily API (1,000 free credits; ~5 searches per application = ~200 apps remaining as of May 7).
- **Telemetry**: Per-generation cost tracking instrumented throughout app.

### Pricing Model (Credit-based, not subscription)
- $0.75 / credit
- 1 credit = 1 CV + 1 cover letter (paired output)
- Failed attempts refund the credit (retry logic)
- Cost basis: ~$0.06–0.10 per generation in tokens → ~500% margin at $0.75
- Freemium tier: limited research (basic LLM), Paid: advanced research (Opus/equivalent)
- Tiered iteration counts (free = 3 amends, paid = unlimited)

### Premium Feature Concepts
- **Job Application Tracker** (TripIt-style): Gmail scanning → categorize Applications / Rejections / Offers / Interviews / Recruiter mails → dashboard with charts + dropdowns. Target: candidates applying to 100+ jobs.
- **Zoom/preview** for cover letter + CV (not just download)
- **Iterate/adjust** generated content after first pass (with prompt-injection guardrails)
- **Highlight/emphasis** controls for specific CV elements during retry
- **Minimum time delay** between generation attempts to prevent errors

### Bug Categories Identified (as of May 7)
- Surname missing in CV header
- Location detection (Canberra vs Wellington)
- "Available on request" rendering for empty fields (should hide)
- Job title mismatch (Portfolio Manager vs Program Manager — needs role taxonomy)
- Cover letters need extra paragraph breaks for readability
- Missing comma after "Dear Hiring Manager"
- Fonterra appearing incorrectly (pulled from CV last job into JD context)
- "Hamish Candidate" instead of full name
- Retry not working (forces new application)

### Distil UI Confirmed Wins
- Magnetic dot pattern + glowy orange background
- Cursor (dot + ring, cream paper variant)
- Status colors: tailoring (orange), finished (green)
- Pulsing/spinning progress indicators
- Step-by-step progress (color shifts + icons)
- Style guide consistency with main brand

### Distil Beta Messaging Rule
"Beta — reliant on cloud LLM provider; like phone or internet, occasional outages possible." *(Anthropic API had a 7–8h outage; team must clearly state dependency.)*

---

## A3. ACADEMY — "10 DAYS CURIOUS"

Carl's mapped two-week structure. Stored in Zoho BAT under Kira-san folder. Targeted at **senior management / C-level first** (Pete's recommendation: execs need firsthand AI experience before embedding it in org).

### 4 Learning Strands (woven through every day)
1. **Personal** — human mindset, curiosity cultivation
2. **Technical** — tokens, context windows, handoffs, cold/warm/closing prompts
3. **Organizational** — applying AI to a real business problem (chosen Day 1)
4. **Enterprise Extension** — scaling learning to leadership team → broader exec / board

### Program Shape
- 10 days, side-by-side support (~1 hr daily)
- Follow-up: 4 hrs/week ongoing
- Pricing: premium content + side-by-side support tier
- Wrap-around pack: engagement letter, tracker spreadsheet, refund policy, testimonial policy, IP/confidentiality agreements
- In-room deliverables: directory structure, cold-start prompt, warm-start prompt, handoff prompt

### Inspiration Use Case (canonical story)
Kane at MSD — Hamish helped him personally → Kane asked Hamish to extend across people group leadership team → then 2-day exec immersion workshop. **The personal → leadership team → board pathway is the Academy revenue flywheel.**

### Provisional Test Subject
Te Eiheu contact at Ministry of Health (Phase 4 pilot candidate).

---

## A4. WEBSITE — CONFIRMED IA & INTERACTIONS

### Top Navigation
- **Left**: Curiosum logo (clickable → home)
- **Right**: 2–3 buttons max — `Age of Curiosity` · `Offerings` · `Evidence`
- **Byline in header**: *Lifelong Curious*
- **Sign-in**: required for gated demos (Distil, IAG, BNZ)
- Smooth scroll on click (not fast jumps)

### Page Sections (alternating black/cream)
> Light/dark mode toggle: when toggled, the alternating colors **invert** (black-section → cream, cream-section → black). Maintains contrast structure across modes.

1. **Hero / Age of Curiosity**
   - Magnetic dot pattern background (same as Distil)
   - Cursor: circular dot + ring
   - CTAs: *Start a conversation* + *See what we do* (place at bottom so visitors browse first)
   - Don't say "management consulting" anywhere

2. **The Curious Age (provocation)**
   - Static curve showing Industrial Age → Information Age → Agentic Age → **Curious Age** (leapfrog)
   - On hover: exponential curve **transforms into a question mark**
   - 4 hover points on the question mark (start of curve, end of curve, middle straight, bottom curve) reveal:
     - New labor model (AI-human hybrid workforce)
     - Knowledge worker DNA shift
     - Not engineering challenge but change program
     - What comes after?
   - Below: inverted knowledge hierarchy visual (organisation evolves from pyramid → connected/flat with knowledge at centre)

3. **Offerings — Card Shuffle**
   - 4 cards: Strategy · Engine · Academy · Labs
   - Click card → **expands on same page** (NOT a handoff to new page)
   - Expanded view: selected card + description + CTA
   - **Strategy** CTA: *Begin a Sprint* (2-week engagement ~$15K)
   - **Engine** CTA: *Try Distil* (demo) OR *Request Support* (custom Engine work)
   - **Academy** CTA: *Reserve a Place* (10 Days Curious immersion)
   - **Labs**: description only — *coming soon* (no offering yet; not ready to deliver)

4. **How We're Different — Scrollable Comparison Window**
   - Draggable vertical divider (matches V01 in main schema)
   - Left: *What others do* (static curve, traditional consulting)
   - Right: *What we do* (dynamic climbing curve, Curiosum approach)
   - 4 differentiators (see A5)

5. **Evidence (not credentials)** — 4 real projects, with images:
   - **Coffee + dollar signs** — James (40-yr coffee veteran, knowledge extraction → 2× business value)
   - **AI-powered bank** — BNZ work (real, paid as Curiosum)
   - **Government white paper** — *One citizen, one profile, services delivered before they're asked* (work-in-progress visual)
   - **Pete's stock trading bot** OR insurance moment-of-need (IAG / Simon)

6. **CTAs / Call-to-Action Patterns** (1–2 per page)
   - Email-capture for **gated white paper** download
   - Question-based prompt → live email preview
   - "Borrow our brain" — single free engine query
   - AI readiness assessment for teams
   - Pre-filled email subjects to reduce friction
   - "Yes / No" with curious decline (No → reveals follow-up list)
   - Countdown timer (urgency without pressure)
   - "If you read this far, you'll probably enjoy what we send next"

### Design Refinements (mandatory)
- **Cream**: too creamy currently → shift toward off-white
- **Brown**: remove from designs entirely (or minimise)
- **Gray text**: 20% brighter for readability
- **Font sizes**: increase smallest by 1–1.5 steps
- **Orange**: brand orange `#E85A0E` (not the saturated bright orange); must not overshadow typography
- **Italic vs roman**: use **color differentiation** (not mixed italic) for emphasis
- **Token counter**: representative only — resets to zero, conveys *thinking is happening*, not actual count
- **Question mark cursor**: when hovering over learn-more / curious elements

---

## A5. THE FOUR DIFFERENTIATORS (Curiosum vs Traditional Consultancy)

Not in main schema as a clean list:

1. **Find the Exemplar** — Never start blank. Someone has already done a version of this. (Cf. Exemplar Intelligence™)
2. **Stay Invested with Loops** — Many short loops, not one big deliverable handoff.
3. **Deliver Uncomfortable Truth** — Big firms filter, soften, manage to protect relationship; we don't.
4. **Measure Outcomes** — Big firms refuse to measure their own work to avoid being held accountable. We measure: Customer Effort Score · Staff Effort Score · Conversion Rate.

### Visual Pattern (proposed)
- Two circles overlapping in centre — left circle = Client, right circle = Curiosum (we sit *with* them, not separate)
- Contrasted with traditional: client + consultancy as separate distant blobs with arrows
- Caption: *No matter what words PwC or Deloitte use, they're always separate to you.*

---

## A6. CURIOUS ORGANIZATIONS — Real Exemplars

For *"Some organisations are already on the journey"* footnote in white paper and proof points:

| Org | Why | Use Case |
|---|---|---|
| **Main Freight** (NZ) | Values knowledge workers; flat structure | Curious-org exemplar |
| **Fisher & Paykel Health** (NZ) | Connection of knowledge over hierarchy | Curious-org exemplar |
| **eBoss** (NZ) | Curious-by-design org | Curious-org exemplar |
| **SoFi** (NASDAQ) | Innovative financial institution | Bank-of-future reference (used in ASB pitch) |

---

## A7. CONSULTING OUTPUT TEMPLATES (Canonical Interactive HTML)

Goal: every traditional consulting deliverable rendered as **interactive HTML**, not PDF/PPT. These are first-class Curiosum IP (templates the Engine fills with context).

| Template | Purpose | Pattern Match |
|---|---|---|
| **North Star** | Canonical positioning statement | Left-border orange block |
| **Operating Model** | Org running mechanics | Layered diagram (E01) |
| **Roadmap** | Future state journey | Timeline with clickable phases |
| **Business Case** | Investment justification | Live updates from decision flow |
| **Risk Register** | Risk tracking with severity | Interactive heat map (clickable scenarios) |
| **RACI** | Responsibility matrix | Click pod → reveal role badges (E05) |
| **Decision Framework** | Approval flow | Scenario modeling slider |
| **Architecture Blueprint** | Tech stack layers | E01 — clickable seam reveals |
| **Delivery Plan** | Sprint timeline | E04 — sprint bars + release borders |
| **Programme Org** | Team structure | 3-pod grid (E05) |
| **Sourcing Model** | Build/buy/borrow split | Stacked area (E06) |
| **Stakeholder Map** | Power/interest matrix | TBD |

> **Rule**: When the Engine produces these *during* a session (not after), that's the moment of differentiation: *"This is not what consultants produce after a meeting. This is what the Engine produces during one."*

---

## A8. AI-NATIVE BUILD METHODS (Hamish's Discovered Practices)

Not in main schema; these are Hamish's working methods worth codifying:

### "Hamish Voice" Method
Record raw thinking by walking around and talking to Claude (voice → text). Creates a **voice MD file** as a reference / North Star to keep Claude grounded across long sessions. Antidote to over-constraining via documentation.

### Cold Start / Warm Start / Handoff Prompts
Three discrete prompt types:
- **Cold Start** — fresh context, references canon
- **Warm Start** — continues a previous session, loads handoff context
- **Handoff Prompt** — end-of-session summary that bootstraps the next session

### A/B Testing Across LLM Configurations
Render N versions of same artifact at different context depths:
- Version A: bare Claude (no project context)
- Version B: + voice MD
- Version C: + voice + language master
- Version D: + voice + language master + KB
- Version E: + voice + language master + KB + content_source
- Compare side-by-side; highest signal version wins

### "North Star" Context Maintenance
Tell Claude to **return to the North Star at every decision point** during a long session. Prevents drift into over-constrained rule systems.

### Lesson Learned (don't repeat)
- Don't try to canonically describe the experience exhaustively before building — over-constrained Experience Master MD broke practical generation. **Use the canon as reference, not as law.**
- Don't try to drive Claude Desktop from Claude Browser. They use the same model. (Cost 2 days of confusion.)
- Don't overuse "Claude design" — it's the same model as Claude desktop; the design context lives in the canon, not the interface.

### Token Limit Strategy
- Single account hits daily/weekly resets; **plan for limits**
- Fallback: ChatGPT Teams / Enterprise for offload (fewer limits)
- For production: enterprise API pay-as-you-go agreement
- Track per-generation cost via telemetry

---

## A9. WHITE PAPER — STRUCTURE & NEW HOOKS

The canonical white paper has these provocations:

### Title Hooks
- **"AI has no tact"** — paired with two memos side-by-side (left: crossed-out human memo with corrections; right: clean AI memo)
- **Organizational Evolution** — Neanderthal → Human styled visual: Pyramid → Connected/flat → Knowledge at Centre
- **The Curious Age** — leapfrog past AI / Agentic age
- **One Citizen, One Profile** — gov't services delivered before being asked (future white paper, separate)

### Government White Paper (planned, separate)
- NZ has ~150 government departments, each with own ID, eligibility logic, IT spend (billions duplicated)
- Argument: smart AI + smart citizen-centric design = consolidated services + huge savings
- Audience: Ministers (specifically Minister Collins outreach)
- Use case: triggers like job loss, health event → services proactively offered
- Guardrails: privacy by user-owned rules; verify-before-execute; triage by stakes (auto: coffee; verify: $10k shares)

### "Standing Commitment" (verbatim, canon)
> *"You hired us to hold the vision uncompromisingly. The discomfort you feel when action doesn't meet strategy — that's exactly what you paid for."*

### Insurance Future-State Story (Simon / IAG)
- Real-time, micro-moment insurance — insurance triggered by life moments (sky-tower-jump, new laptop purchase)
- Auto-cancels when risk passes
- Optional, privacy-first, user-controlled

### Closing CTAs for White Paper
- *I am more curious — give it to me now* (preferred over "No thanks")
- *I'm still curious — want to know more* (post-no follow-up)
- Hold-a-seat-at-the-CuriouSm CTA

---

## A10. ADDITIONAL CORE IP LINES (add to verbatim list)

Already-canonized verbatim quotes in main schema (Section 1.11). Adding:

> *"Helping organisations thrive in the Curiosity Age."* — alternate positioning (use when "Curiosum exists to make people more curious…" is too internal)

> *"We are not an AI company. We are a curiosity company."*

> *"Most consultancies don't measure outputs because they're scared of being sued."*

> *"We work alongside you. Not 10 steps ahead — half a step ahead."*

> *"AI has no tact."*

> *"Think differently. Transform deliberately."* (signature line, already canon)

> *"You don't know what good looks like until you see it."* — implicit theme for novice→medium learner journey

> *"Be interesting for people to be interested."* — Hamish-coined; CTA pattern

---

## A11. PROPOSAL & DEMO INVENTORY (As of 2026-05-11)

### Live Pitches in Flight
| Name | Type | Value | Status |
|---|---|---|---|
| **ASB** | Strategy 5-day workshop | ~$15K | Proposal sent; targeting 19 May workshop |
| **Paul / PK (RIC, Melbourne)** | Engine RFI assessment | ~$10K | Under discussion; 1 day–2 weeks scope |
| **Paul (Australian construction insurer)** | RFI vendor curation | TBD | Side-by-side support, US expansion |
| **Andrew Stevens / BNZ** | AI roadmap (6-month) | TBD | To be re-engaged |
| **James (coffee veteran)** | Knowledge extraction → business sale | Contract | Active; reference case |
| **MSD / Kane** | (Historical) People-group AI immersion | Closed | Reference story for Academy |

### Demos to Maintain (8 in main schema + planned)
- ASB demo HTML (new, in progress) — Vats building
- IAG Use Case 2 (planned)
- BNZ Use Case 2 (planned)
- White-paper interactive HTML (gated)

### Target: 2 customer demos / day for next month (post May 11)

---

## A12. PLATFORM BUILD — IMMEDIATE PRIORITIES

### "Profile Builder as Canary in the Mineshaft"
Distil is the **proof of full-stack platform**:
- Billing flow (Stripe Checkout) → works
- Login flow → works
- Document save/version → works
- → Then replicate for Engine, Client Room, Academy

### Next-Week Decisions Needed
- **CRM**: Zoho CRM capabilities not yet explored — decide
- **Billing**: Stripe (likely) — confirm
- **Transcription**: Whisper (likely)
- **Voice on demos**: ElevenLabs/HeyGen for Phase 2
- **HTTPS / payments**: confirm Crazy Domains supports HTTPS + Stripe gateway
- **GitHub repo** for design elements (single source of truth for component reuse)

### Operational Wishlist (Phase 5–6)
- Voice-recorded meeting → auto-update CRM with actions + owners
- HTML proposals (not PDF) sent as gated URLs
- Per-client "Client Room" Notion-or-bespoke (currently considering Notion for ASB)

---

## A13. CONTACT INFO + PROVENANCE

### Domains
- `curiosum.ai` (primary, registered at **Crazy Domains**)
- `distil.curiosum.ai` (or `curiosum.ai/distil`) — Distil hosting

### Team Emails Status
- Hamish: hamish@curiosum.ai ✓
- Carl: pending email setup
- Vats / Jay: pending email setup
- Email signature standard already in main schema

### Test Recruiter / Reference
- **Calvin (Kelvin)** — recruiter; testing Distil + opportunities pipeline for team

---

## A14. RULES & DECISIONS LOG (from these sessions)

| # | Decision | Source | Date |
|---|---|---|---|
| 1 | Archetype names never exposed externally | Vats raised, Hamish agreed | May 8 |
| 2 | Card-shuffle expansion on same page (no handoff) | Vats proposed | May 8 |
| 3 | Cream → off-white shift | Hamish observed | May 8 |
| 4 | Brown color removed from palette | Hamish observed | May 8 |
| 5 | Light/dark mode inverts alternating sections | Vats proposed | May 8 |
| 6 | Labs = "coming soon" — no CTA | Hamish | May 8 |
| 7 | Distil = credit model (not subscription) | Team agreed | May 7 |
| 8 | Stay on Claude (vs DeepSeek) despite cost | Team agreed | May 9 |
| 9 | Academy targets senior management first | Pete+Carl | May 10 |
| 10 | HTML proposals, not Word/PDF | Hamish | May 9 |
| 11 | Profile Builder = canary platform proof | Hamish | May 9 |
| 12 | Get website published before perfecting | Hamish | May 8 |
| 13 | Daily action items posted to Discord | Team | May 9 |
| 14 | GitHub repo for design elements | Vats | May 9 |
| 15 | "Hamish Voice" MD as North Star anchor | Hamish discovery | May 11 |

---

## A15. NOT-FOR-MAIN-SCHEMA (Distil-Only Details)

Items below stay in Distil's own product spec, not the Curiosum master schema:
- Tavily API credits + cost mechanics
- DeepSeek vs Claude per-generation cost comparisons
- Specific Distil bug list (above in A2)
- Job application tracker premium feature
- Distil-specific font/color tweaks (handled in Distil's own design pass)
- Hamish's individual job applications used as test cases

---

**END ADDENDUM v1**

Next step: ingest Notion KB for language style + content. Schema will continue to grow as Hamish drops more files. When in doubt, refer back to main `Curiosum_Unified_Schema.md` + this addendum together.
