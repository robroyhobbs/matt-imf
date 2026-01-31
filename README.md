# Intent Management Framework (IMF)

> Unifying Intent Across Development, Marketing, and Beyond

**Version:** 0.1.0 (Draft)
**Date:** January 30, 2026

---

## What is IMF?

**IMF (Intent Management Framework)** is a meta-framework that governs how intent flows across disciplines—ensuring that development, marketing, content, and design are **parallel expressions of the same core intent** rather than sequential handoffs.

IMF builds on two methodologies:
- **IDD (Intent Driven Development)** — Already mature, production-ready
- **IDM (Intent Driven Marketing)** — Formalized in this framework

**The key insight:** Intent is the new source code for everything, not just software.

---

## The Problem

### Traditional Workflow (Sequential, Lossy)

```
Founder Vision
    ↓ (verbal/informal)
Product Requirements
    ↓ (handoff, interpretation)
Development
    ↓ (handoff, reverse-engineering)
Marketing
    ↓ (handoff, guessing)
Content/Website
```

Each handoff loses fidelity. Marketing reverse-engineers what dev built. No single source of truth.

### IMF Workflow (Parallel, Unified)

```
            ┌─────────────────────────────────────────┐
            │  L0: STRATEGIC INTENT (Leadership)      │
            │  Vision, Purpose, Market Position       │
            │  Status: LOCKED                         │
            └────────────────┬────────────────────────┘
                             │
              ┌──────────────┴──────────────┐
              ▼                              ▼
    ┌──────────────────┐          ┌──────────────────┐
    │  IDD (Dev)       │◄────────►│  IDM (Marketing) │
    │  Tech Truth      │  cross-  │  Brand Truth     │
    │  Product Intent  │  verify  │  Market Intent   │
    │  AI Code         │          │  AI Content      │
    └────────┬─────────┘          └────────┬─────────┘
             │                              │
             └──────────────┬───────────────┘
                            ▼
                  ┌──────────────────┐
                  │  UNIFIED OUTPUTS │
                  │  Docs, Website,  │
                  │  Product, Comms  │
                  └──────────────────┘
```

Dev and Marketing work from the **same L0 source**. Cross-verification ensures consistency.

---

## Layer Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│  L0: STRATEGIC INTENT                                               │
│  Owner: Leadership (any authorized leader)                          │
│  Status: LOCKED | Changes: Rarely (years)                           │
│  Contents: Vision, Category, Core Principles, Boundaries            │
├─────────────────────────────────────────────────────────────────────┤
│  L1: DOMAIN TRUTH                                                   │
│  Owner: Domain Experts | Status: LOCKED or REVIEWED                 │
│                                                                     │
│  IDD (Development)              IDM (Marketing)                     │
│  ├── Architecture               ├── Brand Voice                     │
│  ├── API Contracts              ├── Language Rules                  │
│  ├── Data Schemas               ├── Visual Identity                 │
│  └── Dependencies               └── Messaging Pillars               │
│                                                                     │
│  SHARED (The Meeting Ground)                                        │
│  ├── PRODUCT.md       What is it? What does it do?                  │
│  ├── PERSONAS.md      Who buys? When do they need it?               │
│  ├── POSITIONING.md   What problem? What solution? What NOT?        │
│  ├── COMPETITIVE.md   Why us? What objections?                      │
│  ├── VALUE-PROPS.md   Features → outcomes                           │
│  ├── EVIDENCE.md      What can we prove?                            │
│  ├── GLOSSARY.md      What do terms mean?                           │
│  └── DIAGRAMS/        How do we show it?                            │
├─────────────────────────────────────────────────────────────────────┤
│  L2: DOMAIN INTENT                                                  │
│  Owner: Team Leads | Status: REVIEWED or DRAFT                      │
│                                                                     │
│  IDD (Development)              IDM (Marketing)                     │
│  ├── Product Intent             ├── Campaign Intent                 │
│  ├── Sprint/Release Scope       ├── Content Calendar                │
│  └── Technical Decisions        └── Channel Strategy                │
├─────────────────────────────────────────────────────────────────────┤
│  L3: GENERATED OUTPUT                                               │
│  Owner: AI + Human Review | Status: DRAFT until approved            │
│                                                                     │
│  IDD: Code, Tests, Docs         IDM: Website, Blog, Campaigns       │
│                                                                     │
│  Verification: Claims traced to L1, messaging aligned with L2       │
└─────────────────────────────────────────────────────────────────────┘
```

---

## Shared Components: The Meeting Ground

The shared layer is where Product and Marketing **must agree**. Eight files answer twelve questions:

| File | Questions Answered |
|------|-------------------|
| `PRODUCT.md` | What is it? What does it do? What's the scope? |
| `PERSONAS.md` | Who buys? When do they need it? |
| `POSITIONING.md` | What problem? What solution? What do we NOT do? |
| `COMPETITIVE.md` | Why us? What will they object to? |
| `VALUE-PROPS.md` | Why do they buy? What outcomes? |
| `EVIDENCE.md` | What can we prove? |
| `GLOSSARY.md` | What do terms mean? |
| `DIAGRAMS/` | How do we show it? |

**Eight files. Twelve questions. One source of truth.**

---

## Approval States

IMF uses a three-state model across all domains:

```
┌─────────────────────────────────────────────────────────────┐
│  LOCKED (Constitutional)                                    │
│  Core truths. Modification requires leadership decision.    │
│  Examples: L0 Strategic Intent, L1 Brand Voice              │
├─────────────────────────────────────────────────────────────┤
│  REVIEWED (Accepted)                                        │
│  Human reviewed and accepted. Changes trigger notice.       │
│  Examples: L2 Campaign messaging, Feature specifications    │
├─────────────────────────────────────────────────────────────┤
│  DRAFT (Proposed)                                           │
│  Work in progress. AI and humans iterate freely.            │
│  Examples: L3 Generated content, New campaign ideas         │
└─────────────────────────────────────────────────────────────┘
```

Markup syntax:
```markdown
::: locked {by=robert reason="Company positioning"}
## Brand Category
We are an AI-Native Engineering company.
:::

::: reviewed {by=matt date=2026-01-30}
## Developer Messaging
"Build identity-aware applications without managing credentials"
:::
```

---

## Cross-Domain Visibility

Domains see what each other is doing — **visibility, not approval**.

```
┌─────────────────┐                    ┌─────────────────┐
│  IDD (Dev)      │◄──── visibility ───►│  IDM (Marketing)│
│                 │                    │                 │
│  "We're adding  │                    │  "We're shifting│
│   feature X"    │                    │   positioning"  │
└─────────────────┘                    └─────────────────┘
         │                                      │
         └──────────────┬───────────────────────┘
                        ▼
          Both informed, neither blocks the other
```

No one blocks anyone, but everyone stays informed.

---

## Directory Structure

### Full Structure

```
project/
├── intent/
│   ├── INTENT.md                     # L0: Strategic Intent
│   │
│   ├── shared/                       # The Meeting Ground
│   │   ├── PRODUCT.md
│   │   ├── PERSONAS.md
│   │   ├── POSITIONING.md
│   │   ├── COMPETITIVE.md
│   │   ├── VALUE-PROPS.md
│   │   ├── EVIDENCE.md
│   │   ├── GLOSSARY.md
│   │   └── DIAGRAMS/
│   │
│   ├── development/                  # IDD domain
│   │   ├── INTENT.md
│   │   └── [modules as needed]
│   │
│   └── marketing/                    # IDM domain
│       ├── INTENT.md
│       ├── brand/
│       │   ├── VOICE.md
│       │   └── LANGUAGE.md
│       └── campaigns/
│
├── src/                              # IDD outputs
├── website/                          # IDM outputs
└── docs/                             # Shared outputs
```

### Minimal Starting Point

```
project/
├── intent/
│   ├── INTENT.md                     # L0 + overview
│   ├── development/INTENT.md         # IDD entry
│   └── marketing/INTENT.md           # IDM entry
```

---

## Document Suite

| Document | Purpose |
|----------|---------|
| [IMF-OVERVIEW.md](IMF-OVERVIEW.md) | Executive summary |
| [IMF-SPECIFICATION.md](IMF-SPECIFICATION.md) | Full technical specification |
| [IDM-STANDARD.md](IDM-STANDARD.md) | Marketing intent standard |
| [IMF-TOOLS.md](IMF-TOOLS.md) | Tool capabilities (TBD) |
| [IMF-DID-PROJECT.md](IMF-DID-PROJECT.md) | First implementation plan |

---

## First Implementation: DID Project

The DID (Decentralized Identity) documentation and website project is the first test case for IMF.

**Outputs:**
- DID Technical Documentation (from IDD)
- DID Marketing Website (from IDM)
- DID Diagrams and Visuals (from shared)
- DIF/W3C Submission Materials (from IDD L1)

See [IMF-DID-PROJECT.md](IMF-DID-PROJECT.md) for the full implementation plan.

---

## Status

**Version 0.1.0 (Draft)** — Ready for discussion and refinement.

- Tools: TBD pending discussion about AFS, AOS, and platform integration
- First implementation: DID project

---

## License

Copyright 2026 ArcBlock. All rights reserved.
