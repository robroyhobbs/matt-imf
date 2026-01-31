# IMF Tools

> Capabilities needed for Intent Management Framework

**Version:** 0.1.0 (Draft)
**Date:** January 30, 2026
**Status:** TBD — Implementation approach to be discussed

---

## Overview

IMF needs tools to help with:

1. **Creating intent** — Interviews to capture L0, IDD, IDM intent
2. **Reviewing intent** — Approving/locking sections
3. **Generating content** — AI that reads intent and produces outputs
4. **Verifying alignment** — Checking claims, cross-domain consistency

---

## Tool Types

| Type | What it is | Examples |
|------|------------|----------|
| **Skills** | Interactive workflows, human-in-the-loop | `/intent-interview`, `/marketing-review` |
| **Agents** | Autonomous tasks, run independently | `intent-validate`, `marketing-audit` |
| **Plugins** | Packaged collections of skills/agents | IDD plugin, IMF plugin |
| **Platform** | Underlying infrastructure | AFS, AOS, Blocklet Server |

---

## Platform Considerations

### AFS (Agentic File System)

Robert is building AFS as the foundational layer for AI-Native systems. IMF should consider:

- How do intent files map to AFS?
- Can AFS provide the "source of truth" layer for L0/L1?
- How does AFS handle cross-domain visibility?

### AOS (Agentic Operating System)

TBD — Need to understand how AOS relates to IMF:

- Does AOS provide the runtime for IMF tools?
- How do agents/skills run within AOS?
- What capabilities does AOS expose that IMF can use?

### Existing IDD Plugin

The IDD plugin already exists with skills like `/intent-interview`, `/intent-review`. IMF tools should:

- Extend, not replace, existing IDD tools
- Share the same approval mechanism (LOCKED/REVIEWED/DRAFT)
- Be compatible with IDD file structures

---

## Implementation Options

| Option | Pros | Cons |
|--------|------|------|
| **Claude Code Skills** | Familiar, existing IDD uses this | May not integrate with AFS/AOS |
| **ArcBlock Native** | Deeper platform integration | Needs development |
| **Hybrid** | Best of both | More complexity |
| **Manual First** | No dev needed, learn what we need | Doesn't scale |

**Recommendation:** Start manual, identify patterns, then build tools.

---

## Capabilities Needed

### For Creating Intent

| Capability | Purpose |
|------------|---------|
| Strategic Interview | Capture L0: vision, category, principles, boundaries |
| Marketing Interview | Capture IDM: personas, positioning, messaging |
| Product Interview | Capture IDD: features, architecture, constraints |

**Key questions to answer:**

**Strategic (L0):**
- What problem are we solving? For whom?
- What market category do we operate in?
- What will we always do? Never do?
- What's shared vs domain-specific?

**Product (Shared):**
- What is the product? What does it do?
- What are the capabilities and scope?
- What's in vs out of scope?

**Marketing (IDM):**
- Who is the audience? What pain do they feel?
- What's the one thing they should remember?
- How are we different? What proof do we have?
- What can we claim? What needs verification?

**Development (IDD):**
- How does it work technically?
- What are the technical constraints?
- What's the architecture?

---

### For Reviewing Intent

| Capability | Purpose |
|------------|---------|
| Section Review | Mark sections as LOCKED, REVIEWED, or DRAFT |
| Cross-Domain Check | See if claims align across IDD and IDM |

---

### For Generating Content

| Capability | Purpose |
|------------|---------|
| Content Generation | AI reads intent, produces content |
| Claim Checking | Flag statements not backed by intent |

**Principle:** AI should read shared/ first, then domain-specific intent, and not invent claims.

---

### For Verifying Alignment

| Capability | Purpose |
|------------|---------|
| Cross-Domain Visibility | See what changed in other domains |
| Sync Check | Identify stale content that needs updating |

---

## Discussion Points

Before implementing tools, we need to discuss:

### With Robert (Platform)
- How does IMF fit with AFS vision?
- What is AOS and how do agents/skills run there?
- Should intent files be AFS-native?

### Implementation Approach
- Manual first vs build tools immediately?
- Claude Code skills vs ArcBlock native vs hybrid?
- How do IMF tools extend existing IDD plugin?

### Scope
- What's v1 vs future?
- How rigorous should verification be initially?
- What's the minimum tooling needed to test IMF with DID project?

---

## Related Documents

- `IMF-OVERVIEW.md` — Framework overview
- `IMF-SPECIFICATION.md` — Full specification
- `IDM-STANDARD.md` — Marketing intent standard
- `/Users/robroyhobbs/work/arcblock-idd/` — Existing IDD tools

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 0.1.0 | 2026-01-30 | Initial draft — TBD for discussion |
