# Gas Turbine Explainer — Landing Page

## The Idea
A single landing page that explains how a gas turbine works.

## Who it's for
Curious people — students, engineering specialists, or anyone who has ever wondered what happens inside a jet engine or power plant turbine.

## What a visitor should understand or do
By the end of the page, a visitor should:
- Understand the four stages of a gas turbine: intake, compression, combustion, power out
- Have a mental picture of how energy is extracted from burning fuel
- Feel like the concept is approachable, not intimidating

## Constraints
- Plain HTML, CSS, optional vanilla JavaScript
- No frameworks, no build step, no external APIs, no data storage
- Deployed on Vercel (free Hobby plan)

## Process
25 versions, moving from wide exploration to a final refined design.
`index.html` in this folder is the gallery that tells the story of the process.

---

## Version Log

### Exploration — v01 to v10

| Version | Title | What was tested |
|---------|-------|-----------------|
| v01 | Plain text, no style | Raw content first — just the words, nothing else. Establishes what needs to be said before any design decisions. |
| v02 | SVG stage diagrams | Added inline SVG illustrations for each of the four stages. Tested whether simple diagrams alone could carry the explanation. |
| v03 | Real engine photos | Replaced SVGs with real Wikimedia Commons photos — Rolls-Royce intake, axial compressor GIF, combustor, and GE J79 turbine. Dark layout introduced. |
| v04 | Schematic + stage highlights | Added a clean engine schematic (text stripped) with colored overlays marking each stage, plus a 4-stage flow diagram as an overview at the top. |
| v05 | Applications section | Added a "Where Gas Turbines Are Used" grid, grouped into Thrust Production (aviation, military, missiles) and Power Production (grid, naval, helicopters, pipelines). |
| v06 | Why it matters + engine type schematics | Added a "Why It Matters" paragraph at top; replaced animation with turbofan and turboshaft schematics including a generator diagram. |
| v07 | Big numbers first | Led with four dramatic stats (1,500°C / 40× / 1 ton/s / 60% efficiency) before any explanation. Tested whether raw numbers hook attention better than narrative. |
| v08 | Interactive stage explorer | Click any of the four stage tabs to highlight that zone on the engine schematic and load the matching photo and text below. First interactive version. |
| v09 | Editorial / light mode | Tried a completely different visual direction — white background, serif body text, magazine-style pull quote. Contrasts sharply with the dark technical aesthetic of earlier versions. |
| v10 | Scroll-reveal storytelling | Each stage panel fades and slides in as you scroll into view using IntersectionObserver. Fixed progress dots on the left track which stage you're reading. |

### Refinement — v11 to v20

Each version in this phase was rewritten for a specific industry audience, testing how the same four-stage explanation changes when the reader's job changes.

| Version | Title | Audience |
|---------|-------|----------|
| v11 | Sticky nav + scroll spy | General — first version with sticky pill nav that highlights the active stage as you scroll through tall two-column stage sections. |
| v12 | Accordion stages | General — all four stages shown as collapsed cards; click to expand. Only one open at a time. |
| v13 | Split-screen — Renewable Energy & Grid | Grid operators and renewables engineers. Split-screen sticky schematic with CCGT, H₂ co-firing, and DLN content. |
| v14 | Comparison table — Power Generation | Utility engineers and plant managers. Comparison table showing gas turbine vs. piston engine across six attributes. |
| v15 | Color panels — Naval & Maritime | Naval engineers and maritime procurement. Each stage fills 100vh with a tinted panel. Content rewritten for GE LM2500, COGAG, DDG-51, and salt-spray inlet separators. |
| v16 | Type-only — Helicopters & Rotorcraft | Rotorcraft engineers and MRO technicians. No photos — diagrams and typography only. Content rewritten for GE T700, free power turbine, and VTOL UAVs. |
| v17 | Step-through — Oil & Gas Pipelines | Pipeline engineers and O&G operations. One stage per card with Prev/Next navigation. Covers pipeline compression, wellhead power, and 25,000+ hr MTBO. |
| v18 | Data chart — Emergency & Standby Power | Data center and hospital facility managers. Pressure/temperature SVG chart with stage data cards. Covers <15-second startup and Tier IV uptime. |
| v19 | Mobile-first — Industrial Manufacturing | Plant engineers reviewing on-site. Mobile-first single column with full-width photos. Covers industrial CHP, 80%+ total efficiency, and DLE combustors. |
| v20 | Best-of synthesis — Cogeneration & CHP | Energy managers and sustainability engineers. Combines sticky nav, big stats, interactive schematic, and engine schematics. |

### Final — v21 to v25

| Version | Title | What was tested |
|---------|-------|-----------------|
| v21 | Editorial + interactive synthesis | Merges v09's light-mode editorial serif aesthetic with v20's sticky nav, big stats, interactive schematic highlights, applications grid, and engine schematics. |
| v22 | For middle schoolers | Fun analogies, big colorful numbers, "Did you know?" wow facts, and a True/False quiz. Written for ages 11–14 with zero jargon. |
| v23 | For graduate students | Full Brayton cycle analysis, isentropic efficiency equations, stage loading, Zeldovich NOx, CMC blades, and hydrogen combustion challenges. Assumes thermodynamics fluency. |
| v24 | For field engineers | Operations manual aesthetic: EGT limits, EOH tracking, borescope intervals, fault symptom tables, surge warning signs, and maintenance checklists. Built for technicians on the job. |
| v25 | Application toggle — split-screen final | Dark editorial hero + pull quote, dynamic stats grid, then a split-screen sticky schematic with a 7-application toggle (Turbofan, Military Jet, Renewable Energy, Power Generation, Naval, Helicopters, Oil & Gas). Each selection rewrites all four stage headings, body text, stats, photos, and captions in place via JavaScript. |

---

## Key Design Decisions

- **Dark theme** established in v03 and carried through to the final — it suits the industrial subject matter and makes the engine schematic overlays legible.
- **Four-stage structure** (Intake → Compression → Combustion → Power Out) was fixed from v01 and became the primary navigation model by v11.
- **IntersectionObserver scroll-spy** (introduced in v10) powers the sticky stage nav and the left-pane schematic highlights in v25.
- **Audience-specific rewrites** (v11–v24) showed that the same physical stages read completely differently depending on what the reader cares about — thrust, efficiency, weight, reliability, or fuel cost.
- **7-application data-driven toggle** in v25 replaces 7 separate pages with a single JS `apps[]` array: each app carries its own stats, stage headings, body HTML, images, and captions. Swapping apps triggers a 180 ms fade across all 28 dynamic elements simultaneously.
