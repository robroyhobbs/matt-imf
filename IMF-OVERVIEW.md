# Intent Management Framework (IMF)

> Unifying Intent Across Development, Marketing, and Beyond

**Version:** 0.1.0 (Draft)
**Author:** ArcBlock
**Date:** January 30, 2026

---

## Executive Summary

**IMF (Intent Management Framework)** is a meta-framework that governs how intent flows across disciplines—ensuring that development, marketing, content, and design are **parallel expressions of the same core intent** rather than sequential handoffs.

IMF builds on two existing methodologies:
- **IDD (Intent Driven Development)** — Already mature, production-ready
- **IDM (Intent Driven Marketing)** — Formalized in this framework

The key insight: **Intent is the new source code for everything**, not just software. The same governance model (LOCKED → REVIEWED → DRAFT) and layer model (L1 → L2 → L3) that works for development also works for marketing, content, and cross-functional collaboration.

---

## The Problem IMF Solves

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

**Problems:**
- Each handoff loses fidelity
- Marketing reverse-engineers what dev built
- No single source of truth
- AI generates content disconnected from product reality
- Different teams use different terminology for same concepts

### IMF Workflow (Parallel, Unified)

```
        ┌─────────────────────────────────────────┐
        │  L0: STRATEGIC INTENT (Leadership)      │
        │  - Vision, Purpose, Market Position     │
        │  - Status: 🔒 LOCKED                    │
        └────────────────┬────────────────────────┘
                         │
          ┌──────────────┴──────────────┐
          ▼                              ▼
┌──────────────────┐          ┌──────────────────┐
│  IDD (Dev)       │◄────────►│  IDM (Marketing) │
│  - Tech Truth    │  cross-  │  - Brand Truth   │
│  - Product Intent│  verify  │  - Market Intent │
│  - AI Code       │          │  - AI Content    │
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

**What changes:**
- Dev and Marketing work from **same L0 source**
- Cross-verification ensures consistency
- AI content verified against product truth
- Shared terminology via GLOSSARY.md
- Changes propagate bidirectionally

---

## IMF Components

### 1. Layer Model (Expanded)

IMF extends the proven L1/L2/L3 model with a shared L0:

| Layer | Name | Owner | Approval State | Purpose |
|-------|------|-------|----------------|---------|
| **L0** | Strategic Intent | Leadership (any) | 🔒 LOCKED | Why we exist, what we stand for |
| **L1** | Domain Truth | Domain Experts | 🔒 LOCKED | Canonical facts (tech truth, brand truth) |
| **L2** | Domain Intent | Team Leads | ✓ REVIEWED | What we're doing (product intent, market intent) |
| **L3** | Generated Output | AI + Human Review | 📝 DRAFT | Actual artifacts (code, content, assets) |

### 2. Domain Standards

| Domain | Standard Document | Description |
|--------|-------------------|-------------|
| Development | `IDD-STANDARD.md` | Already exists, mature |
| Marketing | `IDM-STANDARD.md` | Parallel structure for marketing |
| Content | `ICD-STANDARD.md` | (Future) Intent-driven content |
| Design | `IDD-STANDARD.md` | (Future) Intent-driven design |

### 3. Shared Components (The Meeting Ground)

The shared layer is where Product and Marketing **must agree**. It answers the fundamental questions that shape business outcomes and enable the ability to market, sell, and respond. AI needs these to work correctly.

| File | Questions Answered | Contents |
|------|-------------------|----------|
| `PRODUCT.md` | **What is it? What does it do? What's the scope?** | Product definition, capabilities, boundaries, version scope |
| `PERSONAS.md` | **Who buys? When do they need it?** | Buyer definitions, pain points, language, use cases, triggers |
| `POSITIONING.md` | **What problem? What's the solution? What do we NOT do?** | Problem statement, solution framing, category, explicit boundaries |
| `COMPETITIVE.md` | **Why us? What will they object to?** | Alternatives, differentiators, objections and responses |
| `VALUE-PROPS.md` | **Why do they buy? What outcomes?** | Feature → Benefit mapping, outcomes delivered, promises |
| `EVIDENCE.md` | **What can we prove?** | Case studies, metrics, testimonials, certifications |
| `GLOSSARY.md` | **What do terms mean?** | Canonical definitions, technical ↔ plain language |
| `DIAGRAMS/` | **How do we show it?** | Visual explanations, architecture, flows |

**Eight files. Twelve questions. One source of truth.**

This is the **product marketing / product management intersection** — the foundation that both IDD (development) and IDM (marketing) build from.

### 4. Cross-Domain Visibility

Domains see what each other is doing — not for approval, but for **cross-pollination of perspectives**.

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
              Each can adapt their work accordingly
```

**Key principle:** Visibility, not gatekeeping. Marketing doesn't approve dev work. Dev doesn't approve marketing. But both see changes so they can stay aligned.

---

## Document Suite

IMF consists of the following specifications:

| Document | Purpose | Status |
|----------|---------|--------|
| `IMF-OVERVIEW.md` | This document — executive summary | Draft |
| `IMF-SPECIFICATION.md` | Full technical specification | Draft |
| `IDM-STANDARD.md` | Marketing intent standard | Draft |
| `IMF-TOOLS.md` | Skills and agents for IMF | Draft |
| `IMF-DID-PROJECT.md` | First implementation (DID docs/website) | Draft |

---

## How It Works Together

### Step 1: Strategic Intent (L0)

Leadership defines the immutable core:

```markdown
::: locked {by=leadership date=2026-01-30}
## Strategic Intent

**Vision:** [What we're building and why it matters]

**Category:** [The market space we operate in]

**Core Principles:**
- [Foundational truth that won't change]

**Boundaries:**
- We do NOT [explicit constraint]
:::
```

### Step 2: Domain Truth (L1)

Each domain maintains its canonical facts:

**Development (L1 Tech Truth):**
```markdown
::: locked
## Technical Specification
- Architecture decisions
- API contracts
- Security constraints
:::
```

**Marketing (L1 Brand Truth):**
```markdown
::: locked
## Brand Voice
- Tone and personality
- Language rules (use/avoid)
- Visual identity principles
:::
```

### Step 3: Domain Intent (L2)

Teams define what they're building/communicating:

**Development (L2 Product Intent):**
```markdown
::: reviewed {by=tech-lead date=2026-01-28}
## Product v2.0 Intent
- Feature scope for this release
- Technical approach
- Success criteria
:::
```

**Marketing (L2 Market Intent):**
```markdown
::: reviewed {by=marketing-lead date=2026-01-29}
## Messaging Intent

### For [Persona 1]
"[Value proposition in their language]"

### For [Persona 2]
"[Different angle for different audience]"
:::
```

### Step 4: Generated Output (L3)

AI generates artifacts, verified against L1/L2:

```
┌─────────────────────────────────────────────────────────────┐
│ AI generates content (docs, website, campaigns)             │
│                                                             │
│ Verification checks:                                        │
│ ✓ Technical claims match L1 (product specs)                │
│ ✓ Messaging aligns with L2 (target persona)                │
│ ✓ Language follows brand voice (L1)                        │
│ ✗ Claim "[unverified statement]" — not in L1, flagged      │
└─────────────────────────────────────────────────────────────┘
```

---

## Workflow Summary

### The Reality: Overlapping, Not Linear

In practice, these phases overlap. You don't finish all of "Define" before starting "Generate." The key is knowing **what must be stable before what can proceed**.

```
DEPENDENCIES (what blocks what):

L0 Strategic Intent ──────────────────────────────────────────►
   │                                                    (stable early)
   ├── Shared Components (Personas, Positioning, etc.) ──────►
   │      │                                        (evolves, visible to both)
   │      ├── IDD L2 (Product Intent) ────────────────────────►
   │      │      │                              (dev works here)
   │      │      └── L3 Code ─────────────────────────────────►
   │      │
   │      └── IDM L2 (Marketing Intent) ──────────────────────►
   │             │                           (marketing works here)
   │             └── L3 Content ──────────────────────────────►
   │
   └── Cross-domain visibility throughout ◄──────────────────►
```

### Practical Flow

| Phase | What Happens | Who | Depends On |
|-------|--------------|-----|------------|
| **1. Foundation** | Create L0 + Shared components | Leadership | Nothing |
| **2. Domain Intent** | IDD and IDM create L2 in parallel | Dev + Marketing | L0 + Shared |
| **3. Generate + Iterate** | AI generates, humans refine | AI + Teams | L2 |
| **4. Verify** | Check claims against truth | AI + Human | L1 + L2 |
| **5. Learn** | Update intent from results | Teams | Completed work |

**Key insight:** Phases 2-4 run continuously. You're always defining, generating, and verifying. L0 and Shared are the stable foundation that makes parallel work possible.

---

## Tools Overview

> **Note:** Tooling is TBD — could be Claude Code skills, ArcBlock native tools, or a combination. The concepts below describe *what* the tools do, not *how* they're implemented.

### Capabilities Needed (Interactive)

| Capability | Domain | Purpose |
|------------|--------|---------|
| IMF Interview | IMF | Create L0 Strategic Intent |
| Intent Interview | IDD | Create product intent |
| Marketing Interview | IDM | Create marketing intent |
| Intent Review | IDD | Approve dev sections |
| Marketing Review | IDM | Approve marketing sections |
| Cross-Domain Sync | IMF | Sync and notify across domains |

### Capabilities Needed (Autonomous)

| Capability | Domain | Purpose |
|------------|--------|---------|
| Intent Validate | IDD | Format and constraint check |
| Intent Audit | IDD | Project health report |
| Marketing Validate | IDM | Messaging consistency check |
| Marketing Audit | IDM | Brand compliance report |
| IMF Verify | IMF | Cross-domain alignment check |

---

## First Implementation: DID Project

The DID documentation and website project will be the first test case for IMF:

**Objective:** Produce top-notch technical and marketing materials for ArcBlock's DID technology using the full IMF workflow.

**Outputs:**
1. DID Technical Documentation (from IDD)
2. DID Marketing Website (from IDM)
3. DID Diagrams and Visuals (from shared)
4. DID for DIF/W3C Submission (from IDD L1)

**Success Criteria:**
- Technical accuracy verified against DID spec
- Messaging consistency across all materials
- Cross-functional collaboration without handoff gaps
- AI-generated content meets human standards

See `IMF-DID-PROJECT.md` for detailed implementation plan.

---

## Benefits

### For Leadership
- Write intent once, both teams understand
- Changes propagate automatically
- Single source of truth for vision
- Any leader can define strategic intent for their domain

### For Marketing
- No more reverse-engineering dev specs
- Clear boundaries on what claims are verified
- AI content that matches product reality

### For Development Team
- Marketing speaks same language
- Value props tied to actual features
- Less "what does this mean?" meetings

### For AI Collaboration
- Clear context for generation
- Verification against known truth
- Consistent outputs across domains

---

## What's Next

1. **Finalize IDM Standard** — Complete the marketing intent specification
2. **Build IMF Tools** — Skills and agents for cross-domain work
3. **DID Pilot Project** — Apply IMF to produce DID materials
4. **Iterate and Refine** — Learn from first implementation
5. **Expand Domains** — Add ICD (content), IDD (design) as needed

---

## Related Documents

- `IMF-SPECIFICATION.md` — Full technical specification
- `IDM-STANDARD.md` — Marketing intent standard
- `IMF-TOOLS.md` — Skills and agents
- `IMF-DID-PROJECT.md` — First implementation plan
- `/Users/robroyhobbs/work/arcblock-idd/` — IDD reference implementation

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2026-01-30 | Initial draft |
