# Curiosum

> *Intelligence was never the constraint. **Curiosity is.***

A consulting operating system for the Age of Curiosity. **From Curious to Capable.**

This repository is the public face of [Curiosum Management Consulting](https://github.com/curiosum-ai) — an Auckland-based management consultancy, founded 1999, AI-powered since 2023. The homepage in this repo is the firm's primary digital surface. The accompanying schema documents are the canonical reference for everything else built under the brand.

---

## What this is

A single-page, single-file homepage (`index.html`) that introduces:

- **The Age of Curiosity** thesis — AI is a tool, not an age.
- **Adapt · Adept · Adopt** — the three-word operating philosophy.
- **The Four Doors** — Strategy · Engine · Academy · Labs.
- **Evidence** — four live engagements, told plainly.
- **The Age of Curiosity** white paper (gated download).

Everything else in the repo is **schema canon**: the design system, language master extract, build addendum, and Notion findings that any future page, demo, or proposal should draw from.

---

## Live site

| URL | Status |
|---|---|
| https://curiosum-ai.github.io/curiosum.ai/ | **Live now** — GitHub Pages default |
| https://curiosum.ai | Off until DNS is configured (see [DNS setup](#dns-setup)) |

---

## Local development

No build step. The page is a self-contained `index.html` with inline CSS and JS.

```bash
git clone https://github.com/curiosum-ai/curiosum.ai.git
cd curiosum.ai
# Just open it
open index.html
# Or serve locally if you want a real http origin (recommended for fonts)
python3 -m http.server 8080
# → http://localhost:8080
```

Browser support: any evergreen browser (Chrome / Firefox / Safari / Edge from 2023 onwards). Uses `color-mix()`, `aspect-ratio`, and CSS custom properties. No polyfills.

---

## Deployment (GitHub Pages)

Already enabled on this repo, serving from the `main` branch root.

To rebuild after changes, just push to `main`:

```bash
git add index.html
git commit -m "Update homepage"
git push origin main
```

GitHub Pages picks up the change within 30–60 seconds.

If you ever need to re-enable or change the source:

```bash
# Enable Pages from main branch root
gh api repos/curiosum-ai/curiosum.ai/pages \
  --method POST \
  -f "source[branch]=main" \
  -f "source[path]=/"

# Check status
gh api repos/curiosum-ai/curiosum.ai/pages
```

---

## DNS setup

To serve the site at the custom domain `curiosum.ai`, two things have to happen:

### 1. Add DNS records at Crazy Domains

Log into Crazy Domains → DNS settings for `curiosum.ai` → add the following:

| Type  | Name | Value                            |
|-------|------|----------------------------------|
| A     | @    | `185.199.108.153`                |
| A     | @    | `185.199.109.153`                |
| A     | @    | `185.199.110.153`                |
| A     | @    | `185.199.111.153`                |
| AAAA  | @    | `2606:50c0:8000::153`            |
| AAAA  | @    | `2606:50c0:8001::153`            |
| AAAA  | @    | `2606:50c0:8002::153`            |
| AAAA  | @    | `2606:50c0:8003::153`            |
| CNAME | www  | `curiosum-ai.github.io`          |

DNS propagation usually takes 15 min – 24 h. You can check progress with:

```bash
dig +short curiosum.ai
# Should return the four 185.199.x IPs above
```

### 2. Re-add the CNAME binding

Once DNS resolves to GitHub Pages:

```bash
# Create the CNAME file (binds Pages to your custom domain)
echo "curiosum.ai" > CNAME
git add CNAME
git commit -m "Bind Pages to curiosum.ai"
git push origin main

# Tell GitHub to use the custom domain
gh api repos/curiosum-ai/curiosum.ai/pages \
  --method PUT \
  -f "cname=curiosum.ai"

# Once DNS verifies, enforce HTTPS
gh api repos/curiosum-ai/curiosum.ai/pages \
  --method PUT \
  --raw-field 'https_enforced=true'
```

GitHub will auto-provision a free Let's Encrypt cert. Allow up to 24 h after DNS is correct.

### Why this isn't enabled right now

The CNAME was set initially, but with no DNS records pointing to GitHub, all traffic was being redirected to a domain-parking landing page. We've unset the CNAME so the github.io URL serves the actual site immediately. Re-enable once DNS is configured.

---

## Repository structure

```
.
├── README.md                            # You are here
├── index.html                           # The homepage (Beta 1.1)
├── Curiosum_Unified_Schema.md           # Canonical schema — design tokens, architecture, 40 interaction patterns
├── Curiosum_Schema_Addendum.md          # May 2026 session decisions + Distil specifics
├── Curiosum_Schema_Notion_Findings.md   # Notion canon — corrections, methodology, IP lines
├── Curiosum_Admin_Summary.md            # Admin / repo-level summary
├── .gitignore                           # Standard ignores
└── .git/                                # ⋯
```

### The four schema documents (read in this order)

1. **`Curiosum_Unified_Schema.md`** — the primary reference. Design system tokens, six-layer platform architecture, demo library, 40 interaction patterns, build phases.
2. **`Curiosum_Schema_Addendum.md`** — Beta-period gaps captured from live working sessions: Distil product specifics, website IA decisions, "Hamish voice" build methods.
3. **`Curiosum_Schema_Notion_Findings.md`** — **Notion canon wins on words.** Founding year (1999), primary tagline (*From Curious to Capable*), Adapt·Adept·Adopt, Four-Stage Delivery, Exemplar Intelligence™, AI Readiness six dimensions, the locked verbatim lines.
4. **`Curiosum_Admin_Summary.md`** — repo / organisational summary.

When the three documents conflict, the priority rule is:

> **Notion findings win on words. Addendum wins on real-time decisions. Unified schema wins on design tokens.**

---

## Versioning

| Version | Tag | Notes |
|---------|-----|-------|
| Beta 1.0 | `f9f731c` | Initial homepage push (schema canon + first homepage). |
| Beta 1.1 | `495bcb2` | Six feedback fixes: theme toggle, full-page dot field, age explorer with question-mark transform, shuffle-deck tenets, pyramid↔constellation compare, CTA upgrades. |

Future versions live on `main`. Tag a release when one's worth distinguishing.

---

## Brand at a glance

For full canon, see `Curiosum_Schema_Notion_Findings.md`. The bare minimum any future page needs to honour:

### Voice
- Not corporate-sterile. Not buzzword-laden AI evangelism. Not academic.
- Four archetypes always present (staff-internal naming): BCG · Jason Fox · Jimmy Carr · Thoughtful Design.
- Whitespace earns its keep. The body is 17 px, not 16 — reading bigger signals trust.

### Visual
- **Orange `#E85A0E`** is the verb. Used for promoted lines, rules, and signal — never decoration.
- **Dark `#0E0D0B`** and **cream `#FAF7F0`** alternate as surface tokens. Theme toggle swaps them.
- **Display**: Instrument Serif italic. **Body**: DM Sans. **Mono**: JetBrains Mono.
- The dot field is atmospheric, not aggressive. Calm reactivity. Always behind.

### Locked verbatim lines
> *Intelligence was never the constraint. Curiosity was.*
> *The technology was never the constraint. It was always belief.*
> *The AI Age is not an age. It is a toolset. Naming it an age is the mistake of the people selling the tools.*
> *What question is your organisation most afraid to ask?*

### Standing Commitment (every client-facing artefact)
> *You hired us to hold the vision uncompromisingly. The discomfort you feel when action doesn't meet strategy — that's exactly what you paid for.*

---

## Contact

- **Founder**: Hamish Carr — hamish@curiosum.ai · +64 21 717 310
- **Where**: Auckland · Wellington · Brisbane
- **Repo**: https://github.com/curiosum-ai/curiosum.ai

---

## License & IP notice

All content — copy, design, schema documents, interaction patterns — is the intellectual property of Curiosum Management Consulting. The following marks are filed or pending at IPONZ:

- **The Age of Curiosity™**
- **The Curious Age™**
- **The Age of Actualisation™**
- **Exemplar Intelligence™**
- **The Token Test™**
- **The 2× Ahead Principle™**

This repository is public so the homepage can be served via GitHub Pages and so contributors can be invited transparently. Reuse of the canon content for derivative branding is not permitted. The HTML/CSS/JS scaffolding is offered as a reference for how a Curiosum surface is constructed — not as a template to clone.

If in doubt, ask Hamish.
