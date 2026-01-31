# IDM: Intent Driven Marketing Standard

> Marketing Intent Standard — Parallel to IDD for Development

**Version:** 0.1.0 (Draft)
**Date:** January 30, 2026

---

## Design Goals

1. **Brand Consistency** — All marketing outputs reflect same voice and positioning
2. **Claim Verification** — Every marketing claim traceable to evidence
3. **Audience Alignment** — Messaging tailored to specific personas
4. **AI-Ready** — Structure that AI can read and generate from
5. **Cross-Domain Integration** — References to IDD product truth

---

## Core Principle

> **Marketing Intent is the source of truth for all customer-facing content.**
> AI generates content. Humans verify intent.

```
Traditional:  Write copy → Review → Publish → Hope it's consistent
IDM:          Intent → Generate → Verify → Publish → Sync
```

---

## Directory Structure

### Relationship to Shared

The **shared/** folder contains the meeting ground — things product and marketing must agree on (personas, positioning, value props, etc.).

The **marketing/** folder contains marketing-specific execution — how we bring those shared foundations to life (voice, campaigns, content calendar).

```
shared/                    →  What we agree on (with product)
├── PERSONAS.md                Who buys, use cases
├── POSITIONING.md             Problem, solution, boundaries
├── VALUE-PROPS.md             Features → outcomes
└── ...

marketing/                 →  How we execute (marketing-owned)
├── brand/VOICE.md             How we sound
├── campaigns/                 Specific initiatives
└── content/                   What we publish where
```

### Standard Layout

```
project/
├── intent/
│   └── marketing/                    # IDM root
│       ├── INTENT.md                 # Entry point: overview + index
│       │
│       ├── brand/                    # L1: Brand Truth
│       │   ├── VOICE.md              # Tone, style, personality
│       │   ├── VISUAL.md             # Colors, typography, imagery
│       │   └── LANGUAGE.md           # Terminology rules
│       │
│       ├── campaigns/                # L2: Active Campaigns
│       │   └── <campaign>/
│       │       └── INTENT.md
│       │
│       └── content/                  # L2: Content Strategy
│           ├── PILLARS.md            # Content themes
│           ├── CHANNELS.md           # Channel strategy
│           └── CALENDAR.md           # Content calendar
```

**Note:** Personas, positioning, and competitive info live in **shared/**, not here. Marketing references them but doesn't own them alone.

---

## What Lives Where

```
┌─────────────────────────────────────────────────────────────┐
│  shared/ (Joint ownership with product)                     │
│  - Personas, positioning, value props, evidence             │
│  - The "meeting ground" — both teams reference this         │
├─────────────────────────────────────────────────────────────┤
│  marketing/brand/ (Marketing-owned, stable)                 │
│  - Voice and tone                                           │
│  - Visual identity                                          │
│  - Language rules                                           │
│  - Changes rarely, with leadership input                    │
├─────────────────────────────────────────────────────────────┤
│  marketing/campaigns/ (Marketing-owned, active)             │
│  - Specific initiatives                                     │
│  - Key messages for this campaign                           │
│  - Timeline and channels                                    │
│  - Evolves frequently                                       │
├─────────────────────────────────────────────────────────────┤
│  marketing/content/ (Marketing-owned, operational)          │
│  - Content pillars and themes                               │
│  - Channel strategy                                         │
│  - Calendar                                                 │
└─────────────────────────────────────────────────────────────┘
```

---

## File Formats

### INTENT.md (Marketing Entry Point)

```markdown
# Marketing Intent

> One-line positioning statement

## Brand Summary
- Voice: [brief voice description]
- Category: [market category]
- Primary Audience: [main persona]

## Active Campaigns
| Campaign | Status | Launch Date |
|----------|--------|-------------|
| DID Launch | In progress | 2026-02-15 |

## Key Metrics
- [North star metric]
- [Supporting metrics]

## Related
- brand/VOICE.md
- positioning/MESSAGING.md
```

### VOICE.md (Brand Voice)

```markdown
# Brand Voice

::: locked {by=founder}
## Personality
[3-5 adjectives that define the brand]

## Tone Spectrum
| Context | Tone |
|---------|------|
| Technical docs | Professional, precise |
| Marketing | Approachable, confident |
| Error messages | Helpful, calm |
| Social | Conversational, witty |

## Writing Principles
1. [Principle 1]
2. [Principle 2]
3. [Principle 3]
:::
```

### LANGUAGE.md (Terminology Rules)

```markdown
# Language Rules

::: locked {by=marketing-lead}
## Words to Use
| Term | Context | Why |
|------|---------|-----|
| Share | Action | More approachable than "deploy" |
| Creator | Person | Not "developer" - our audience |

## Words to Avoid
| Avoid | Use Instead | Why |
|-------|-------------|-----|
| Easy | [describe benefit] | Subjective, dismissive |
| Simply | [just remove] | Implies user is stupid |
| Blockchain | Decentralized | Implementation detail |

## Technical Term Translations
| Technical | Plain Language |
|-----------|----------------|
| DID | Digital identity you control |
| Verifiable Credential | Proof that's unforgeable |
:::
```

### AUDIENCES.md (Persona Definitions)

```markdown
# Audiences

## Primary: [Persona Name]

::: reviewed {by=marketing-lead date=2026-01-25}
### Demographics
- Role: [job title/role]
- Company: [company type/size]
- Technical level: [low/medium/high]

### Pain Points
1. [Pain point 1]
2. [Pain point 2]

### Goals
1. [Goal 1]
2. [Goal 2]

### Language
- Uses terms like: [terms they use]
- Responds to: [emotional triggers]
- Avoids: [turnoff terms]

### Channels
- Primary: [channel]
- Secondary: [channels]
:::

## Secondary: [Persona Name]
...
```

### MESSAGING.md (Messaging Framework)

```markdown
# Messaging Framework

## Core Message Hierarchy

::: reviewed {by=marketing-lead date=2026-01-28}
### Badge (5 words max)
[Short memorable phrase]

### Headline (10 words max)
[Primary value proposition]

### Subhead (20 words max)
[Supporting detail]

### Proof Points
1. [Proof point 1]
2. [Proof point 2]
3. [Proof point 3]
:::

## Per-Audience Messaging

### For [Persona 1]

::: reviewed {by=marketing-lead date=2026-01-28}
**Hook:** [What gets their attention]

**Problem:** [The pain they feel]

**Solution:** [How we solve it]

**Proof:** [Why they should believe us]

**CTA:** [What we want them to do]
:::

### For [Persona 2]
...
```

### Campaign INTENT.md

```markdown
# [Campaign Name] Intent

## Objective
[Single clear objective]

## Audience
- Primary: [Persona]
- Secondary: [Persona]

## Key Messages
::: reviewed {by=campaign-owner date=2026-01-30}
### Primary Message
[Main thing we want them to remember]

### Supporting Messages
1. [Message 1]
2. [Message 2]
:::

## Channels
| Channel | Content Type | Frequency |
|---------|--------------|-----------|
| LinkedIn | Thought leadership | 3x/week |
| Email | Nurture sequence | Weekly |

## Success Metrics
| Metric | Target | Measurement |
|--------|--------|-------------|
| [Metric 1] | [Target] | [How measured] |

## Constraints
::: locked
### Must Include
- [Required element]

### Must Avoid
- [Prohibited element]
:::

## Timeline
| Phase | Dates | Deliverables |
|-------|-------|--------------|
| Prep | Feb 1-7 | Assets, copy |
| Launch | Feb 15 | Go live |
```

---

## Claim Verification

Simple principle: **Don't claim what you can't back up.**

| If you're claiming... | Check it against... |
|-----------------------|---------------------|
| Product capability | Development specs (IDD) |
| Metrics/numbers | shared/EVIDENCE.md |
| Comparisons | Competitive research (be careful) |
| Certifications | shared/EVIDENCE.md or company records |

If a claim isn't backed by a source, flag it for discussion before publishing.

---

## How AI Should Use These Files

When generating marketing content, AI should:

1. **Start with shared/** — Understand personas, positioning, value props
2. **Read the relevant marketing intent** — Campaign, messaging, voice
3. **Stay in bounds** — Use approved language, don't invent claims
4. **Flag uncertainty** — If unsure about a claim, say so

The goal is AI that sounds like us and doesn't make things up.

---

## Cross-Domain Integration

Marketing doesn't work in isolation. The connection points:

| Marketing needs... | Which comes from... |
|--------------------|---------------------|
| What the product actually does | Development (IDD) |
| Who we're selling to | shared/PERSONAS.md |
| What problems we solve | shared/POSITIONING.md |
| What we can claim | shared/EVIDENCE.md |
| Feature → benefit translation | shared/VALUE-PROPS.md |

**The shared/ folder is the bridge.** Both teams contribute to it, both teams reference it.

---

## Minimalism Principle

### Start With

- `shared/PERSONAS.md` — Who we're talking to
- `shared/POSITIONING.md` — Problem we solve
- `marketing/INTENT.md` — Marketing overview
- `marketing/brand/VOICE.md` — How we sound

### Add When Needed

- `shared/VALUE-PROPS.md` — When features need benefit translation
- `marketing/brand/LANGUAGE.md` — When terminology gets complex
- `marketing/campaigns/` — When running structured campaigns

### Don't Overthink

- You don't need a file for everything
- If it's a one-off, just do it
- Add structure when patterns emerge

---

## Evolution Path

Start simple, add when needed:

```
Stage 1: Minimal
├── shared/PERSONAS.md            # Who we're talking to
├── shared/POSITIONING.md         # What problem we solve
├── marketing/INTENT.md           # Marketing overview
└── marketing/brand/VOICE.md      # How we sound

Stage 2: Add Depth
├── shared/VALUE-PROPS.md         # Features → benefits
├── marketing/brand/LANGUAGE.md   # Terminology rules
└── marketing/content/PILLARS.md  # Content themes

Stage 3: Add Campaigns
└── marketing/campaigns/<name>/INTENT.md
```

**Principle:** Add files when you have content for them.

---

## Related Documents

- `IMF-OVERVIEW.md` — Framework overview
- `IMF-SPECIFICATION.md` — Full IMF specification
- `IMF-TOOLS.md` — Skills and agents
- `../arcblock-idd/docs/intent-standard.md` — IDD reference

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2026-01-30 | Initial draft |
