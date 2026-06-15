# getdealtin.com — Landing Page
**Margin Ventures LLC · Na · Native · Narrative · 2026**

This is the main landing page for getdealtin.com — the entry point to the Na ecosystem and the tool suite built for families navigating financial systems they didn't have a hand in creating.

---

## Purpose

The landing page does three things:

1. **Establishes identity** — getdealtin is not a generic utility portal. It is a civic and financial platform with a specific point of view. The page communicates that immediately, before any tool is described.

2. **Routes users to tools** — Three tools currently live under the platform: Make It Stretch (food), Follow the Money (civic), Home Buying Helper (housing). Each operates as a separate application in its own GitHub repository. The landing page links out to all three.

3. **Seeds the Na narrative** — The bottom section introduces Native and Narrative — the nonprofit feedback loop infrastructure and the Substack voice — without requiring the user to already understand it. It's written to land for someone who knows nothing about Na, while rewarding those who want to go deeper.

---

## Design Philosophy

### "Grounded Resilience"

The visual language is drawn from the same design system as Make It Stretch. The two sites are meant to feel like the same family — same fonts, same greens, same gold, same sidebar dark tone — without being identical.

**Left/main column:** Stability, warmth, narrative. The open cream canvas creates breathing room. Lora serif carries the editorial weight. The user's eye moves down naturally through the hero, the tool entries, and into the Na section.

**Right sidebar:** Authority, accountability, utility. Dark forest (`#25332B` Midnight Juniper) with precise typography. The sidebar is a navigation panel that also communicates platform status at a glance. It stays with the user as they scroll.

### The Split Is Intentional

The same principle that governs Make It Stretch governs this page:

- **Left = survival tools** — what the user needs right now
- **Right = systemic context** — what they should know about why they need it

On the landing page this means: left tells the story of the tools and the mission, right shows the tools in a navigational context with status indicators.

---

## Color Palette

Matches Make It Stretch exactly. See `DESIGN_SYSTEM.md` for full token reference.

| Token | Value | Role |
|-------|-------|------|
| `--cream` | `#f5f0e4` | Page canvas |
| `--cream-dark` | `#ede8d8` | Hover tints |
| `--green-forest` | `#1B3624` | Primary text, Na highlights |
| `--gold` | `#D9822B` | Accent — section labels, arrows, quote text |
| `--text-dark` | `#1a1a18` | Headlines |
| `--text-mid` | `rgba(26,26,24,0.55)` | Body copy |
| `--text-light` | `rgba(26,26,24,0.38)` | Muted labels |
| Sidebar bg | `#25332B` | Midnight Juniper — sidebar only |
| Live badge | `#5db87a` | Same as Make It Stretch VOTED NO green |

---

## Typography

Identical font stack to Make It Stretch. The three-brain rule applies:

| Font | Role | Where used |
|------|------|-----------|
| **Playfair Display** | Emotion, gravitas | Hero h1, Na section headlines, closing statement |
| **Lora** | Editorial warmth | Section titles, tool names, Na body copy, sidebar tool names |
| **Plus Jakarta Sans** | UI clarity | Body text, tool descriptions, sidebar descriptions |
| **IBM Plex Mono** | Data, precision | Nav links, labels, eyebrows, domain tags, status badges, footer |

**Rule:** The Na section body copy uses Lora (not Plus Jakarta Sans) because it is editorial content — journalistic in register, not functional.

---

## Layout

```
┌──────────────────────────── NAV (fixed, 52px) ─────────────────────────┐

┌──────────────── HERO (full-width, split grid) ─────────────────────────┐
│  Ben Franklin image (left, faded)  │  Headline + tagline + quote       │
│                                    │  + scroll prompt                  │
└────────────────────────────────────────────────────────────────────────┘

┌── .page-container (max-width: 1200px, grid: 1fr 340px, gap: 48px) ─────┐
│                                                                          │
│  ┌──── .main-content ──────────────┐  ┌──── .sticky-sidebar ───────┐   │
│  │  Section intro                  │  │  Header: getdealtin label  │   │
│  │  Tool 01 — Make It Stretch      │  │  Tool Suite eyebrow        │   │
│  │  Tool 02 — Follow the Money     │  │  ─────────────────────     │   │
│  │  Tool 03 — Home Buying Helper   │  │  Make It Stretch           │   │
│  │                                 │  │  Follow the Money          │   │
│  │  ── Na Section ──               │  │  Home Buying Helper        │   │
│  │  We're all Native.              │  │  ─────────────────────     │   │
│  │  [editorial copy]               │  │  Footnote                  │   │
│  │                                 │  └────────────────────────────┘   │
│  │  Everyone has a Narrative.      │                                    │
│  │  [editorial copy]               │                                    │
│  │                                 │                                    │
│  │  Let's get dealt in.            │                                    │
│  │  [loop diagram]                 │                                    │
│  │  [links]                        │                                    │
│  └─────────────────────────────────┘                                    │
└──────────────────────────────────────────────────────────────────────────┘

┌──────────────────────── FOOTER ────────────────────────────────────────┐
```

**CSS grid:** `grid-template-columns: 1fr 340px; gap: 48px`

**Sidebar:** `position: sticky; top: 80px; align-self: start` — stays with the user as they scroll the left column.

**Mobile (≤900px):** Single column. Sidebar drops out of sticky and stacks below the main content. Ben Franklin image hidden. Hero scales to full width.

**Mobile (≤480px):** Second breakpoint. Headline shrinks to 36px. Padding tightens. Nav links reduce to 10px.

---

## Hero Section

- **Ben Franklin image** — embedded as base64 in the HTML (no external dependency). Masked with a right-facing gradient so it dissolves into the cream background. Opacity 0.22, sepia filter. Maintains the visual identity from the original getdealtin design.
- **Headline** — Playfair Display 700, `clamp(42px, 5vw, 72px)`. "Let's get you dealt in" in italic green.
- **Tagline** — "Free tools for people navigating a financial system they didn't have a hand in designing. Know what's shaping your budget, your home, your future — and use it."
- **Quote** — Benjamin Franklin, rendered in `#D9822B` gold italic. Border-left in same gold. Not decorative — it's the philosophical anchor.
- **Scroll prompt** — "SEE THE TOOLS" in IBM Plex Mono with a gold arrow. On hover the text shifts to gold and the arrow nudges down 3px. Scrolls to `#tools` on click.

---

## Sidebar Design

The sidebar is a dark card (`#25332B`, `border-radius: 12px`, two-layer shadow) that communicates platform status without being purely navigational.

### Each Tool Entry Contains:
1. **Domain tag** — `FOOD · CIVIC` in IBM Plex Mono 8px with a subtle background tint
2. **Status badge** — inline right, pill-shaped: green `Live` or dim `Beta`
3. **Tool name** — Lora 700 with inline right arrow
4. **Description** — Plus Jakarta Sans 11.5px at 52% cream opacity

### Hover Behavior:
- Slot background lifts to `rgba(255,255,255,0.04)`
- Tool name shifts to `#D9822B` gold
- Arrow translates 4px right with `ease` transition

### Status Indicators:
- **Live** — `#5db87a` green dot with glow + green pill background
- **Beta** — dim dot + muted pill

---

## Na Section

The Na section is a long-form editorial section at the bottom of the left column. It is not marketing copy — it is journalism about the system.

### Structure:

**`We're all Na*tive.*`** — Playfair Display headline with `Na` in `#1B3624` italic. Followed by two paragraphs: (1) the system was built before you arrived and wasn't designed with you in mind, (2) once you see it clearly you can move through it differently.

**`Everyone has a Na*rrative.*`** — Same headline treatment. Followed by two paragraphs: (1) your situation is specific — your zip code, your senator, your wages — no median captures it, (2) the data loop explained in plain terms: your signal comes back as community intelligence.

**`Let's get dealt in.`** — Closing statement in Playfair Display italic, `#1B3624` green. Same visual weight as the headlines. Both a callback to the brand name and an invitation.

**Loop diagram** — `getdealtin → Na → Native → Narrative → community ↩` in IBM Plex Mono with gold arrows.

**Links** — Substack, Contact (`getdealtin.hq@gmail.com`), Data Sources.

### Tone:
Write like the New York Times editorial board, not like a startup. No hype words. No "revolutionary" or "empowering." State the facts about the system plainly and trust the reader to feel the weight of them.

---

## Tool Entries (Main Column)

Each tool entry has:
- **Number** — `Tool 01` in IBM Plex Mono, muted
- **Name** — Lora 700 26px
- **Tags** — e.g. `Food` · `Live` in IBM Plex Mono pill tags, `#EEF3EE` background, `#1B3624` text
- **Description** — editorial framing of what the tool does and why it exists
- **Link** — IBM Plex Mono uppercase with animated gap-widening on hover

Entries are separated by `border-top: 1px solid var(--border)` — not cards, not boxes. The border reinforces that these are items in a unified list, not separate products.

---

## Separate Repositories

Each tool operates independently:

| Tool | Repo | URL |
|------|------|-----|
| Make It Stretch | `make-it-stretch` | food.getdealtin.com |
| Follow the Money | `follow-the-money` | money.getdealtin.com |
| Home Buying Helper | `homebuying` | homebuying.getdealtin.com |
| Landing page | `getdealtin` | getdealtin.com |

The landing page links to each tool externally. No shared build system. No monorepo. Each tool is self-contained and can be deployed independently.

---

## Files

```
getdealtin/
├── index.html          ← this page (single file, self-contained)
├── homebuying.html     ← home buying tool
└── README.md           ← this file
```

The Ben Franklin image is embedded as base64 in `index.html` — no `/images/` directory needed.

---

## Hosting & DNS

The landing page is served as a **static site on Render** (no cold start — static sites are always-on even on the free tier).

Each tool runs as a separate Node.js service on Render and is mapped to a subdomain via CNAME records in Squarespace DNS.

### DNS Records (Squarespace)

| Type | Name | Target |
|------|------|--------|
| `A` | `@` | `216.24.57.1` |
| `CNAME` | `www` | `getdealtin.onrender.com` |
| `CNAME` | `food` | `make-it-stretch.onrender.com` |
| `CNAME` | `money` | `follow-the-money.onrender.com` |
| `CNAME` | `homebuying` | `homebuying.onrender.com` |

### Cold Start Prevention

Node.js services on Render's free tier sleep after 15 minutes of inactivity (50-second cold start on first request). UptimeRobot is configured to ping both services every 5 minutes to keep them warm:

- `https://food.getdealtin.com` — pinged every 5 min
- `https://money.getdealtin.com` — pinged every 5 min

Static sites (getdealtin.com) are not affected — they don't sleep.

---

## What Not To Do

- Don't add cards or a question flow — that was the old design, intentionally removed
- Don't use Space Mono — the font was replaced with IBM Plex Mono across the entire system
- Don't use `#2e5e1e` — the old getdealtin green. The correct primary is `#1B3624`
- Don't use `#c9a84c` — the old gold. The correct accent is `#D9822B`
- Don't add more tools to the sidebar without adding them to the main content first
- Don't link directly to `.onrender.com` URLs — always use the `getdealtin.com` subdomains
- Don't write marketing copy in the Na section — it should read like journalism
- Don't add a separate "about" page — the Na section at the bottom of this page is the about

---

*Na · Native · Narrative · getdealtin · 2026*
