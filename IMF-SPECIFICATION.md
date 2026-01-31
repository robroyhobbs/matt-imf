# IMF Technical Specification

> Intent Management Framework — Full Technical Reference

**Version:** 0.1.0 (Draft)
**Date:** January 30, 2026

---

## Design Goals

1. **Cross-Domain Coherence** — Single intent source serves multiple disciplines
2. **Parallel Execution** — Dev and marketing work simultaneously, not sequentially
3. **Verification at Every Layer** — AI outputs verified against known truth
4. **Progressive Formalization** — Start minimal, add structure as needed
5. **Backward Compatible** — Existing IDD projects work without changes

---

## Layer Architecture

### L0: Strategic Intent

The foundational layer owned by leadership at any level. Rarely changes. All other layers derive from this. Any authorized leader (founder, marketing lead, tech lead) can establish L0 intent for their domain.

```markdown
# Strategic Intent

::: locked {by=founder reason="Company foundation"}
## Vision
One sentence: what we're building and why it matters.

## Category
What market/space we operate in.

## Core Principles
- Principle 1
- Principle 2
- Principle 3

## Strategic Constraints
What we will NOT do. Boundaries on the vision.
:::
```

**Characteristics:**
- Status: Always 🔒 LOCKED
- Owner: Leadership (any authorized leader)
- Change frequency: Rarely (years)
- Scope: Applies to entire organization or defined domain

### L1: Domain Truth

Canonical facts within each domain. The "source of record" that all claims are verified against.

```
┌─────────────────────────────────────────────────────────────┐
│  L1: DOMAIN TRUTH                                           │
├─────────────────────────────────────────────────────────────┤
│  IDD (Development)              IDM (Marketing)             │
│  ├── Architecture               ├── Brand Voice             │
│  ├── API Contracts              ├── Language Rules          │
│  ├── Data Schemas               ├── Visual Identity         │
│  ├── Security Constraints       ├── Messaging Pillars       │
│  └── Dependencies               └── Competitive Position    │
│                                                             │
│  SHARED (The Meeting Ground)                                │
│  ├── Product (what it is, capabilities, scope)              │
│  ├── Personas (who buys, use cases, triggers)               │
│  ├── Positioning (problem, solution, boundaries)            │
│  ├── Competitive (why us, objections, responses)            │
│  ├── Value Props (features → outcomes, promises)            │
│  ├── Evidence (case studies, metrics, proof)                │
│  ├── Glossary (terms, tech ↔ plain language)                │
│  └── Diagrams (visuals, architecture, flows)                │
└─────────────────────────────────────────────────────────────┘
```

**Characteristics:**
- Status: 🔒 LOCKED or ✓ REVIEWED
- Owner: Domain experts
- Change frequency: Quarterly/annually
- Verification: All L2/L3 claims checked against L1

### L2: Domain Intent

What each team is currently working on. The "active context" for AI generation.

```
┌─────────────────────────────────────────────────────────────┐
│  L2: DOMAIN INTENT                                          │
├─────────────────────────────────────────────────────────────┤
│  IDD (Development)              IDM (Marketing)             │
│  ├── Product Intent             ├── Campaign Intent         │
│  │   (features, modules)        │   (launches, promotions)  │
│  ├── Sprint/Release Scope       ├── Content Calendar        │
│  ├── Technical Decisions        ├── Messaging Decisions     │
│  └── Implementation Plan        └── Channel Strategy        │
│                                                             │
│  CROSS-REFERENCES                                           │
│  ├── Feature → Value Prop mapping                           │
│  ├── Technical term → Plain language mapping                │
│  └── Capability → Benefit mapping                           │
└─────────────────────────────────────────────────────────────┘
```

**Characteristics:**
- Status: ✓ REVIEWED or 📝 DRAFT
- Owner: Team leads
- Change frequency: Weekly/sprint
- Notification: Changes trigger cross-domain alerts

### L3: Generated Output

AI-generated artifacts verified against L1/L2.

```
┌─────────────────────────────────────────────────────────────┐
│  L3: GENERATED OUTPUT                                       │
├─────────────────────────────────────────────────────────────┤
│  IDD (Development)              IDM (Marketing)             │
│  ├── Code                       ├── Website content         │
│  ├── Tests                      ├── Blog posts              │
│  ├── Documentation              ├── Email campaigns         │
│  └── API docs                   └── Social content          │
│                                                             │
│  VERIFICATION                                               │
│  ├── Claims traced to L1 sources                            │
│  ├── Messaging aligned with L2 intent                       │
│  ├── Language follows L1 rules                              │
│  └── Flagged items for human review                         │
└─────────────────────────────────────────────────────────────┘
```

**Characteristics:**
- Status: 📝 DRAFT (until human approves)
- Owner: AI + Human reviewer
- Change frequency: Continuous
- Verification: Automated checks + human spot-check

---

## Directory Structure

### Full IMF Project Structure

```
project/
├── intent/                           # IMF root
│   │
│   ├── INTENT.md                     # L0: Strategic Intent
│   │
│   ├── shared/                       # The Meeting Ground
│   │   ├── PRODUCT.md                # What it is, capabilities, scope
│   │   ├── PERSONAS.md               # Who buys, use cases, triggers
│   │   ├── POSITIONING.md            # Problem, solution, boundaries
│   │   ├── COMPETITIVE.md            # Why us, objections, responses
│   │   ├── VALUE-PROPS.md            # Features → outcomes, promises
│   │   ├── EVIDENCE.md               # Case studies, metrics, proof
│   │   ├── GLOSSARY.md               # Terms, tech ↔ plain language
│   │   └── DIAGRAMS/                 # Visuals, architecture, flows
│   │
│   ├── development/                  # IDD domain
│   │   ├── INTENT.md                 # Entry point
│   │   ├── architecture/
│   │   │   ├── DEPENDENCIES.md
│   │   │   └── BOUNDARIES.md
│   │   └── modules/
│   │       └── <module>/INTENT.md
│   │
│   ├── marketing/                    # IDM domain
│   │   ├── INTENT.md                 # Entry point
│   │   ├── brand/
│   │   │   ├── VOICE.md              # Tone, style, language
│   │   │   ├── VISUAL.md             # Colors, typography
│   │   │   └── LANGUAGE.md           # Use/avoid terms
│   │   ├── positioning/
│   │   │   ├── AUDIENCES.md          # Persona definitions
│   │   │   └── MESSAGING.md          # Per-audience messaging
│   │   └── campaigns/
│   │       └── <campaign>/INTENT.md
│   │
│   └── content/                      # ICD domain (future)
│       └── ...
│
├── src/                              # IDD outputs
├── website/                          # IDM outputs
└── docs/                             # Shared outputs
```

### Minimal IMF Structure (Starting Point)

```
project/
├── intent/
│   ├── INTENT.md                     # L0 + high-level overview
│   ├── development/INTENT.md         # IDD entry
│   └── marketing/INTENT.md           # IDM entry
```

---

## Approval Mechanism

IMF uses the same three-state model as IDD, extended to all domains.

### States

```
┌─────────────────────────────────────────────────────────────┐
│  🔒 LOCKED (Constitutional)                                  │
│                                                              │
│  Core truths that define the organization/product.           │
│  Modification requires explicit leadership decision.         │
│                                                              │
│  Examples:                                                   │
│  - L0 Strategic Intent                                       │
│  - L1 Brand Voice                                            │
│  - L1 Technical Architecture                                 │
├─────────────────────────────────────────────────────────────┤
│  ✓ REVIEWED (Accepted)                                       │
│                                                              │
│  Human has reviewed and accepted. Changes trigger notice.    │
│                                                              │
│  Examples:                                                   │
│  - L2 Campaign messaging                                     │
│  - L2 Feature specifications                                 │
│  - Cross-domain mappings                                     │
├─────────────────────────────────────────────────────────────┤
│  📝 DRAFT (Proposed)                                         │
│                                                              │
│  Work in progress. AI and humans can freely iterate.         │
│                                                              │
│  Examples:                                                   │
│  - L3 Generated content                                      │
│  - L2 New campaign ideas                                     │
│  - Brainstorming sections                                    │
└─────────────────────────────────────────────────────────────┘
```

### Markup Syntax

Same fenced div format as IDD:

```markdown
::: locked {by=leader reason="Company positioning"}
## Brand Category
We are an AI-Native Engineering company, not a blockchain company.
:::

::: reviewed {by=marketing-lead date=2026-01-30}
## Developer Messaging
"Build identity-aware applications without managing credentials"
:::

::: draft
## Social Campaign Ideas
- LinkedIn thought leadership series
- Twitter thread on DID benefits
:::
```

---

## Cross-Domain Verification

The core idea: **AI can't make claims that aren't backed by the shared truth.**

When generating content (L3), AI should:
1. Read from shared/ to understand personas, positioning, value props
2. Read from the relevant domain L2 for current intent
3. Only make claims that can be traced to L1/shared sources
4. Flag anything it's unsure about for human review

This isn't a rigid checklist — it's a principle: **if it's not in the intent, don't invent it.**

---

## Cross-Domain Visibility

When content changes, the other domain can see it. **Visibility, not approval** — no one blocks anyone, but everyone stays informed.

### What Each Domain Sees

| When this changes... | The other domain sees... |
|---------------------|--------------------------|
| L0 Strategic Intent | Foundation shifted — check alignment |
| IDD L1/L2 (product) | Marketing sees what's being built |
| IDM L1/L2 (marketing) | Dev sees how it's being positioned |
| shared/* | Both see the common ground evolving |

The goal is **cross-pollination of perspectives**, not gatekeeping.

---

## How AI Should Behave

Simple rules:

| Section Type | AI Behavior |
|--------------|-------------|
| 🔒 LOCKED | Don't touch without explicit human approval |
| ✓ REVIEWED | Can modify, but flag the change |
| 📝 DRAFT | Work freely |

When generating content:
- Read the shared/ files first — that's the foundation
- Stay within the boundaries defined in POSITIONING.md
- Use the language defined in GLOSSARY.md
- Only claim what's in EVIDENCE.md or the product specs

---

## Evolution Path

Start simple, add structure when you need it.

### Stage 1: Minimal

```
intent/
├── INTENT.md              # L0 + overview
├── shared/PERSONAS.md     # Start with who buys
├── development/INTENT.md  # What we're building
└── marketing/INTENT.md    # How we talk about it
```

### Stage 2: Build Out Shared

```
intent/
├── INTENT.md
├── shared/
│   ├── PRODUCT.md         # What it is, capabilities
│   ├── PERSONAS.md        # Who buys, use cases
│   ├── POSITIONING.md     # Problem, solution, boundaries
│   ├── VALUE-PROPS.md     # Features → outcomes
│   └── GLOSSARY.md        # What terms mean
├── development/
└── marketing/
```

### Stage 3: Full Structure

```
intent/
├── INTENT.md
├── shared/
│   ├── PRODUCT.md
│   ├── PERSONAS.md
│   ├── POSITIONING.md
│   ├── COMPETITIVE.md
│   ├── VALUE-PROPS.md
│   ├── EVIDENCE.md
│   ├── GLOSSARY.md
│   └── DIAGRAMS/
├── development/
│   └── [as needed]
├── marketing/
│   └── [as needed]
```

**Principle:** Add files when you have content for them, not before.

---

## Related Documents

- `IMF-OVERVIEW.md` — Executive summary
- `IDM-STANDARD.md` — Marketing intent standard
- `IMF-TOOLS.md` — Skills and agents
- `../arcblock-idd/docs/intent-standard.md` — IDD reference

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2026-01-30 | Initial draft |
