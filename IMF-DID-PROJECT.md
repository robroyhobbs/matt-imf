# IMF DID Project: First Implementation

> Applying Intent Management Framework to DID Documentation & Website

**Version:** 0.1.0 (Draft)
**Date:** January 30, 2026

---

## Project Overview

> **Note: Framework Demonstration**
>
> This document serves as a **template and example** of how IMF can be applied to a real project. The DID content shown here is illustrative placeholder content — actual product specifications, technical details, and messaging would be developed through the IMF process with the relevant stakeholders.
>
> Use this as a structural guide, not as final DID documentation.

### Objective

Produce a comprehensive suite of DID (Decentralized Identity) materials using the full IMF workflow, demonstrating cross-functional collaboration between leadership, marketing, and development.

### Deliverables

| Output | Owner | Source |
|--------|-------|--------|
| DID Technical Documentation | Dev | IDD intent |
| DID Marketing Website | Marketing | IDM intent |
| DID Diagrams & Visuals | Shared | Shared intent |
| DIF/W3C Submission Materials | Dev | IDD L1 |
| DID Explainer Content | Marketing | IDM intent |

### Success Criteria

1. **Technical Accuracy** — All claims verified against DID specification
2. **Messaging Consistency** — Same story told across all materials
3. **Cross-Domain Alignment** — Dev and marketing intent synchronized
4. **AI Quality** — Generated content meets human standards
5. **Process Validation** — IMF workflow proven effective

---

## Project Structure

### Directory Layout

```
did-project/
├── intent/
│   │
│   ├── INTENT.md                     # L0: Strategic Intent
│   │
│   ├── shared/                       # The Meeting Ground
│   │   ├── PRODUCT.md                # What DID is, capabilities, scope
│   │   ├── PERSONAS.md               # Developer, Enterprise, Consumer + use cases
│   │   ├── POSITIONING.md            # Identity problem, DID solution, boundaries
│   │   ├── COMPETITIVE.md            # vs other identity solutions, objections
│   │   ├── VALUE-PROPS.md            # DID features → user outcomes
│   │   ├── EVIDENCE.md               # DID adoption metrics, case studies
│   │   ├── GLOSSARY.md               # DID terminology (tech ↔ plain)
│   │   └── DIAGRAMS/                 # Visual explanations, architecture
│   │
│   ├── development/
│   │   ├── INTENT.md                 # IDD entry point
│   │   ├── SPEC.md                   # DID technical specification
│   │   ├── API.md                    # DID API contracts
│   │   └── IMPLEMENTATION.md         # How our DID works
│   │
│   └── marketing/
│       ├── INTENT.md                 # IDM entry point
│       ├── brand/
│       │   └── LANGUAGE.md           # DID terminology translations
│       ├── positioning/
│       │   ├── AUDIENCES.md          # Developer, Enterprise, Consumer
│       │   └── MESSAGING.md          # Per-audience messaging
│       └── content/
│           └── PILLARS.md            # Content themes
│
├── outputs/
│   ├── docs/                         # Generated documentation
│   ├── website/                      # Generated website
│   ├── diagrams/                     # Generated visuals
│   └── submissions/                  # DIF/W3C materials
│
└── .imf/
    └── sync-log.md                   # Cross-domain sync history
```

---

## Phase 1: Strategic Intent (L0)

### Goal

Establish the foundational "why" for DID that both dev and marketing will reference.

### Process

1. `/imf-interview` with leadership
2. Capture vision, category, principles
3. Lock L0 sections

### Expected Output: intent/INTENT.md

```markdown
# DID Strategic Intent

::: locked {by=leader date=2026-01-30}
## Vision

Decentralized identity infrastructure that makes users the sovereign owners
of their digital identity — not platforms, not governments, not corporations.

## Category

We are **Decentralized Identity Infrastructure**, not:
- A blockchain company
- A wallet provider
- A Web3 toolchain

## Core Principles

1. **DID = Accountable Identity** — DID is an identifier for accountability,
   not a wallet address. It represents a subject that can be held responsible.

2. **Self-Sovereign by Default** — Users control their identity. No platform
   can revoke, modify, or access it without consent.

3. **Interoperable First** — W3C DID standard compliant. Works with any
   DID-compatible system, not just our ecosystem.

4. **Privacy Preserving** — Selective disclosure. Share only what's needed.
   Zero-knowledge proofs where possible.

## Strategic Constraints

We will NOT:
- Build identity systems that require central authority
- Store user credentials on our servers
- Create proprietary formats that lock users in
- Sacrifice privacy for convenience
:::

## Domain Boundaries

### Development (IDD) Owns
- DID method specification (did:abt)
- Resolver implementation
- Credential issuance/verification APIs
- Wallet integration protocols
- SDK and developer tools

### Marketing (IDM) Owns
- Audience messaging and positioning
- Website content and copywriting
- Explainer content (what is DID?)
- Use case narratives
- Customer-facing documentation tone

### Shared
- Glossary of terms (technical ↔ plain language)
- Diagrams and visual explanations
- Feature-benefit mapping
- Evidence library (case studies, testimonials)
```

---

## Phase 2: Domain Truth (L1)

### Development L1: Technical Specification

**File:** `intent/development/SPEC.md`

```markdown
# DID Technical Specification

::: locked {by=tech-lead reason="Core specification"}
## DID Method

**Method name:** `did:abt`

**Method-specific identifier:**
```
did:abt:<multibase-encoded-public-key>
```

## Resolution

- Universal Resolver compatible
- Resolution endpoint: `https://resolver.arcblock.io/1.0/identifiers/`
- DID Document format: W3C DID Core v1.0

## Supported Key Types

| Type | Algorithm | Usage |
|------|-----------|-------|
| Ed25519 | EdDSA | Primary signing |
| Secp256k1 | ECDSA | Ethereum compatibility |
| BLS12-381 | BLS | Aggregate signatures |

## Credential Format

- W3C Verifiable Credentials Data Model v1.1
- JSON-LD with compact representation option
- Selective disclosure via BBS+ signatures
:::
```

### Marketing L1: Brand and Language

**File:** `intent/marketing/brand/LANGUAGE.md`

```markdown
# DID Language Rules

::: locked {by=marketing-lead}
## Technical Term Translations

| Technical | Plain Language | Use When |
|-----------|----------------|----------|
| DID | Digital identity you control | Consumer audiences |
| DID | Decentralized Identifier | Developer audiences |
| Verifiable Credential | Digital proof / unforgeable certificate | Consumer |
| DID Document | Identity record | All audiences |
| Resolver | Identity lookup service | Developer |
| Self-sovereign identity | Identity you own and control | All audiences |

## Messaging Principles

### Do
- Lead with user benefit, not technology
- Use "you" and "your" liberally
- Emphasize control and ownership
- Use concrete examples

### Don't
- Lead with "blockchain" or "Web3"
- Use jargon without explanation
- Make it sound complicated
- Compare to competitors by name
:::
```

---

## Phase 3: Domain Intent (L2)

### Development L2: Product Scope

**File:** `intent/development/INTENT.md`

```markdown
# DID Development Intent

## Current Scope

::: reviewed {by=tech-lead date=2026-01-28}
### DID Core (v2.0)

**Features:**
1. Multi-chain support (12 chains)
2. Universal resolver integration
3. DID rotation support
4. Recovery mechanism

**APIs:**
- `create(keyType)` — Create new DID
- `resolve(did)` — Resolve DID to document
- `update(did, changes)` — Update DID document
- `deactivate(did)` — Deactivate DID

### Verifiable Credentials

**Features:**
1. VC issuance and verification
2. Selective disclosure (BBS+)
3. Revocation registry
4. Credential status checking

**APIs:**
- `issue(claims, holder)` — Issue credential
- `verify(credential)` — Verify credential
- `present(credentials, requirements)` — Create presentation
:::
```

### Marketing L2: Messaging Framework

**File:** `intent/marketing/positioning/MESSAGING.md`

```markdown
# DID Messaging Framework

## Core Message Hierarchy

::: reviewed {by=matt date=2026-01-30}
### Badge
"Own Your Identity"

### Headline
"The digital identity infrastructure that puts you in control"

### Subhead
"Create, manage, and share verifiable credentials without giving up ownership to platforms"

### Proof Points
1. W3C standard compliant — works everywhere
2. Privacy-preserving — share only what's needed
3. Self-sovereign — no one can revoke your identity
:::

## Per-Audience Messaging

### For Developers

::: reviewed {by=matt date=2026-01-30}
**Hook:** "Build identity-aware apps without managing user credentials"

**Problem:** Managing user identity is a liability — security breaches,
password resets, compliance headaches. You want to verify users, not
store their secrets.

**Solution:** DID lets users bring their own verified identity. You verify
claims without storing credentials. Users control their data, you reduce risk.

**Proof:**
- W3C Verifiable Credentials standard
- 12 blockchain integrations
- Universal Resolver compatible
- SDK for TypeScript, Go, Python

**CTA:** "Start building with DID →"
:::

### For Enterprises

::: reviewed {by=matt date=2026-01-30}
**Hook:** "Compliance-ready identity infrastructure that you control"

**Problem:** Identity systems are either locked to vendors or require
massive investment to build in-house. Compliance requirements keep changing.

**Solution:** Self-hosted DID infrastructure with built-in compliance features.
Issue and verify credentials without third-party dependencies.

**Proof:**
- SOC 2 compliant
- GDPR-ready (user data ownership)
- On-premise deployment option
- Enterprise SLA available

**CTA:** "Request enterprise demo →"
:::

### For Consumers

::: reviewed {by=matt date=2026-01-30}
**Hook:** "Your digital identity, truly yours"

**Problem:** Every site wants you to create an account, remember passwords,
trust them with your data. When they get hacked, you're exposed.

**Solution:** One identity you control. Log in anywhere without creating
accounts. Share only what's needed. Revoke access anytime.

**Proof:**
- Works with 50+ apps (growing)
- No passwords to remember
- See exactly what you've shared
- Delete your data, really delete it

**CTA:** "Get your DID →"
:::
```

---

## Phase 4: Shared Components

### Glossary

**File:** `intent/shared/GLOSSARY.md`

```markdown
# DID Glossary

::: locked
## Canonical Definitions

| Term | Definition | Notes |
|------|------------|-------|
| DID | Decentralized Identifier — a globally unique identifier that does not require a centralized registration authority | W3C standard |
| DID Document | A document containing information associated with a DID, including public keys and service endpoints | |
| Verifiable Credential | A tamper-evident credential with authorship that can be cryptographically verified | W3C standard |
| Holder | The entity that possesses a verifiable credential | Usually the user |
| Issuer | The entity that creates and signs a verifiable credential | Usually an authority |
| Verifier | The entity that checks a verifiable credential | Usually a relying party |
| Self-Sovereign Identity | An identity model where the individual controls their identity without relying on external authorities | SSI |
| Resolver | A service that takes a DID and returns the corresponding DID Document | |
:::
```

### Value Props Mapping

**File:** `intent/shared/VALUE-PROPS.md`

```markdown
# Feature-Value Proposition Mapping

## Mapping Table

| Feature (IDD) | Value Prop (IDM) | Audience | Status |
|---------------|------------------|----------|--------|
| Multi-chain support (12 chains) | "Works with any blockchain" | Developer | ✓ Synced |
| Universal Resolver | "Compatible with any DID system" | Developer | ✓ Synced |
| BBS+ signatures | "Share only what's needed" | Consumer | ✓ Synced |
| On-premise deployment | "Infrastructure you control" | Enterprise | ✓ Synced |
| Recovery mechanism | "Never lose your identity" | Consumer | ✓ Synced |

## Last Sync
- Date: 2026-01-30
- By: imf-sync

## Pending
- VC revocation registry → [needs value prop]
```

---

## Phase 5: Content Generation (L3)

### Workflow

```
1. Read IDM L2 (messaging intent)
2. Read IDD L1 (technical spec for accuracy)
3. Read shared/GLOSSARY (terminology)
4. Generate content
5. Run marketing-validate
6. Flag unverified claims
7. Human review
8. Publish
```

### Example: Website Homepage

**Input:**
- `marketing/positioning/MESSAGING.md` (core messages)
- `marketing/positioning/AUDIENCES.md` (primary = developer)
- `development/SPEC.md` (feature verification)
- `shared/VALUE-PROPS.md` (feature-benefit mapping)

**Generated Output:**

```html
<!-- Hero Section -->
<section class="hero">
  <span class="badge">Own Your Identity</span>
  <h1>The digital identity infrastructure that puts you in control</h1>
  <p>Create, manage, and share verifiable credentials without giving up
     ownership to platforms</p>
  <a href="/get-started" class="cta">Start Building with DID</a>
</section>

<!-- For Developers Section -->
<section class="audience-developers">
  <h2>Build identity-aware apps without managing user credentials</h2>
  <ul class="proof-points">
    <li>W3C Verifiable Credentials standard</li>
    <li>12 blockchain integrations</li>
    <li>Universal Resolver compatible</li>
  </ul>
</section>
```

**Verification Report:**

| Claim | Source | Status |
|-------|--------|--------|
| "puts you in control" | MESSAGING.md:12 | ✓ Approved message |
| "12 blockchain integrations" | SPEC.md:45 | ✓ Verified |
| "W3C Verifiable Credentials" | SPEC.md:78 | ✓ Verified |

---

## Phase 6: Verification & Audit

### Pre-Launch Checklist

```markdown
## DID Project IMF Verification

### IDD Checks
- [ ] All technical claims verified against SPEC.md
- [ ] API documentation matches implementation
- [ ] Code examples tested and working

### IDM Checks
- [ ] All marketing claims verified against IDD L1
- [ ] Language follows brand/LANGUAGE.md
- [ ] Messaging matches MESSAGING.md framework

### Cross-Domain Checks
- [ ] VALUE-PROPS.md complete and synced
- [ ] GLOSSARY.md terms used consistently
- [ ] No contradictions between dev docs and marketing

### Content Quality
- [ ] All pages reviewed by human
- [ ] Flagged claims addressed
- [ ] CTAs functional
```

---

## Phases

| Phase | Owner | Deliverable |
|-------|-------|-------------|
| 1. L0 Strategic Intent | Leadership | INTENT.md |
| 2. L1 Domain Truth | Dev + Marketing | SPEC.md, LANGUAGE.md |
| 3. L2 Domain Intent | Dev + Marketing | Development/Marketing INTENT.md |
| 4. Shared Components | Joint | GLOSSARY.md, VALUE-PROPS.md |
| 5. Content Generation | AI + Human | Website, Docs, Diagrams |
| 6. Verification | All | Review, fixes |
| 7. Launch | All | Published materials |

---

## Roles

| Role | Person | Responsibilities |
|------|--------|------------------|
| Strategic Owner | Leadership | L0 approval, final sign-off |
| Marketing Lead | Matt | IDM intent, messaging approval |
| Dev Lead | TBD | IDD intent, technical accuracy |
| AI Operator | Matt/Dev | Run generation, verification |
| Reviewer | All | Human review of generated content |

---

## Success Metrics

| Metric | Measurement |
|--------|-------------|
| Claim Verification | All claims traced to sources |
| Cross-Domain Sync | All features have value props |
| Human Approval | All L2 sections REVIEWED |
| Content Quality | Human review pass rate |

---

## Learnings Capture

After completion, document:

1. **What worked** — IMF practices that helped
2. **What didn't** — Friction points in the process
3. **Tool gaps** — Skills/agents that are missing
4. **Process improvements** — Workflow refinements
5. **Template updates** — Better starting points

---

## Related Documents

- `IMF-OVERVIEW.md` — Framework overview
- `IMF-SPECIFICATION.md` — Full specification
- `IDM-STANDARD.md` — Marketing intent standard
- `IMF-TOOLS.md` — Skills and agents
- `../arcblock-idd/` — IDD reference

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2026-01-30 | Initial draft |
