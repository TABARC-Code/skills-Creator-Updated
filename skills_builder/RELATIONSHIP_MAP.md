# Relationship Map

**Author:** TABARC-Code

This file records the current structured relationships in the Option B skill-builder repo.

No vague backlinking. A link exists only when it changes behaviour, execution, interpretation, constraints, audit flow, or handoff logic.

## Standard Chain

```text
Creative Exploration Engine
→ Skill Handoff Bridge
→ Structured Skill Engineering System
→ Skill Creator
```

The `Relationship Contract Engine` sits beside the chain and activates when skills, sub-skills, chains, or reciprocal relationships need to be created, updated, weighted, or audited.

```text
Structured Skill Engineering System ↔ Relationship Contract Engine
Skill Creator ↔ Relationship Contract Engine
```

Conditional side-links also exist:

```text
Creative Exploration Engine → Relationship Contract Engine
Skill Handoff Bridge → Relationship Contract Engine
```

These side-links only activate when relationship candidates or repository link updates are involved.

## Verified Direct Contracts

| Source | Target | Type | Strength | Status |
|---|---|---|---|---|
| Creative Exploration Engine | Skill Handoff Bridge | translation | strong | verified |
| Skill Handoff Bridge | Creative Exploration Engine | translation | strong | verified |
| Skill Handoff Bridge | Structured Skill Engineering System | translation | critical | verified |
| Structured Skill Engineering System | Skill Handoff Bridge | translation | critical | verified |
| Structured Skill Engineering System | Skill Creator | execution layer | critical | verified |
| Skill Creator | Structured Skill Engineering System | execution layer | critical | verified |
| Skill Handoff Bridge | Skill Creator | translation | strong | verified |
| Skill Creator | Skill Handoff Bridge | translation | strong | verified |
| Structured Skill Engineering System | Relationship Contract Engine | audit | strong | verified |
| Relationship Contract Engine | Structured Skill Engineering System | audit | strong | verified |
| Skill Creator | Relationship Contract Engine | audit | strong | verified |
| Relationship Contract Engine | Skill Creator | audit | strong | verified |

## Verified Conditional Contracts

| Source | Target | Type | Strength | Condition | Status |
|---|---|---|---|---|---|
| Creative Exploration Engine | Structured Skill Engineering System | creative influence | contextual | only direct when user bypasses bridge or asks for immediate engineering | verified |
| Structured Skill Engineering System | Creative Exploration Engine | audit | contextual | when engineering reveals a conceptual gap requiring more ideation | verified |
| Creative Exploration Engine | Skill Creator | creative influence | contextual | only indirect through bridge/engineering unless user asks for a quick draft skill | verified |
| Skill Creator | Creative Exploration Engine | audit feedback | contextual | when tests reveal the core concept needs more ideation rather than more engineering | verified |
| Creative Exploration Engine | Relationship Contract Engine | enhancement | contextual | when creative output proposes new skills, sub-skills, or links | verified |
| Relationship Contract Engine | Creative Exploration Engine | constraint | contextual | when creative relationship ideas must be formalised or rejected | verified |
| Skill Handoff Bridge | Relationship Contract Engine | orchestration | moderate | when handoff packets contain candidate relationships | verified |
| Relationship Contract Engine | Skill Handoff Bridge | orchestration | moderate | when bridge metadata must preserve relationship candidates | verified |

## Chain Propagation

### Chain: Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System → Skill Creator

- **Creative Exploration Engine** is the upstream origin. It produces recoverable drafts but cannot certify readiness.
- **Skill Handoff Bridge** is the intermediary. It converts creative material into engineering-ready packets.
- **Structured Skill Engineering System** is the ruleset and validator. It defines hierarchy, modules, evaluation standards, failure classes, and scale control.
- **Skill Creator** is the practical execution loop. It drafts `SKILL.md`, creates evals, runs or simulates tests, aggregates evidence, improves instructions, optimises descriptions, and packages finished skills.

Indirect relationships:

- Creative Exploration Engine → Structured Skill Engineering System is contextual and normally mediated by the bridge.
- Creative Exploration Engine → Skill Creator is contextual and usually mediated by both bridge and engineering.
- Skill Handoff Bridge → Skill Creator is direct when the goal is actual skill creation, because bridge packets must be buildable.
- Structured Skill Engineering System → Skill Creator is critical because the creator applies the engineering rules in practice.
- Skill Creator → Creative Exploration Engine is a feedback route, not a normal generation path. It activates when evals show the idea itself is weak or muddled.

## Reverse and Non-Linear Links

No automatic reverse links are assumed.

Current explicit reverse or non-linear links:

- Structured Skill Engineering System → Creative Exploration Engine: contextual audit feedback when engineering exposes a conceptual failure.
- Skill Creator → Creative Exploration Engine: contextual feedback when tests show the concept needs another creative pass.
- Relationship Contract Engine → Creative Exploration Engine: contextual constraint when creative work proposes repository relationships.
- Relationship Contract Engine → Skill Handoff Bridge: moderate orchestration for preserving candidate relationship metadata.
- Relationship Contract Engine → Skill Creator: strong audit constraint when skill creation or improvement changes relationships.

## Sub-Skill Status

`relationship-contract-engine` is treated as a sub-skill of the broader skill-building system, but it has its own contracts and weights. Its relationship strength is not inherited automatically from the structured engineering skill.

`skill-creator` is also treated as a sub-skill of the broader system. It is heavier than the others because it bundles scripts, agents, schemas, and assets. Its links are not assumed from the parent system; they are explicitly recorded above.

## Rejected or Deferred Links

None currently recorded.

If future links are only thematic, decorative, loosely inspirational, or too vague to change behaviour, list them here instead of pretending they are real contracts.

## Audit Check

- Direct links have reciprocal contracts.
- Chain positions are recorded.
- Conditional links are explicitly labelled.
- Relationship strengths include practical reasons in the relevant skill files.
- Sub-skills are not treated as automatic copies of parent skills.
- No “see also” style links are counted as contracts.


---

## Relationship Contract: Skill Classification Engine → Skill Manifest

**Source:** Skill Classification Engine  
**Target:** Skill Manifest  
**Relationship Direction:** Skill Classification Engine assigns and maintains Dewey-style codes used by the manifest.  
**Reciprocal Direction:** Skill Manifest exposes those codes as the public listing layer for humans and future tooling.  
**Relationship Type:** enhancement  
**Relationship Strength:** strong  
**Strength Reason:** future listing and skill linking need stable identity metadata; without it, the repo relies on names alone, which gets brittle fast.  
**Direct or Indirect:** direct  
**Chain Position:** sidecar catalogue governance layer  
**Reason for Relationship:** classification codes help group, browse, and link skills without confusing taxonomy with behavioural dependency.  
**Behavioural Impact:** new or updated skills should receive identity metadata and be added to the classification index.  
**Source Update Requirement:** assign/update Dewey-style codes and labels.  
**Target Update Requirement:** display codes consistently in the manifest.  
**Affected Files:** `skill-classification-engine/SKILL.md`, `SKILL_MANIFEST.md`, `CLASSIFICATION_INDEX.md`  
**Audit Status:** verified

## Relationship Contract: Skill Classification Engine → Relationship Contract Engine

**Source:** Skill Classification Engine  
**Target:** Relationship Contract Engine  
**Relationship Direction:** Skill Classification Engine supplies identity codes that can support relationship maps, chain views, and future skill-linking.  
**Reciprocal Direction:** Relationship Contract Engine prevents classification from being mistaken for an actual behavioural link.  
**Relationship Type:** constraint  
**Relationship Strength:** moderate  
**Strength Reason:** classification improves discovery, but relationship contracts still decide whether one skill changes another's behaviour.  
**Direct or Indirect:** conditional direct  
**Chain Position:** sidecar-to-sidecar governance link  
**Reason for Relationship:** future linking benefits from stable IDs, but those IDs must not become lazy backlinks.  
**Behavioural Impact:** when a classification change affects routing, hierarchy, or maps, relationship contracts must be checked.  
**Source Update Requirement:** include identity codes without asserting behavioural influence.  
**Target Update Requirement:** reference codes only as identifiers, not proof of dependency.  
**Affected Files:** `skill-classification-engine/SKILL.md`, `relationship-contract-engine/SKILL.md`, `RELATIONSHIP_MAP.md`, `CLASSIFICATION_INDEX.md`  
**Audit Status:** verified
