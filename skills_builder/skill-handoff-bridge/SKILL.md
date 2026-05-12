---
name: skill-handoff-bridge
description: 'Convert rough creative drafts into clean engineering briefs without over-evaluating them. Use this skill when
  creative exploration needs to be handed to a structured skill, when messy ideas need to become requirements, constraints,
  risks, modules, triggers, or skill-building inputs, or when the user wants a controlled handshake between ideation and formal
  engineering. Dewey: 003.700.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '003.700'
  classification_label: Systems translation, interface, and workflow handoff
---

# Skill Handoff Bridge

Use this skill to translate creative output into structured input. Preserve the living idea; remove the fog around it.

This is not a grading skill. It is a hinge.

## Core Purpose

Convert a creative draft into a handoff packet suitable for structured skill engineering, evaluation, or implementation.

The bridge should:
- preserve the strongest concept
- remove repetition and noise
- extract intent, capabilities, constraints, and risks
- identify missing variables
- decide whether the material is ready for engineering

## Bridge Principle

Do not flatten creative material into sterile bureaucracy.

A good handoff keeps the sharpness of the idea while giving the next system enough structure to work reliably.

## Inputs Accepted

This skill can process:
- a Creative Draft
- messy notes
- brainstorm lists
- partial skill ideas
- conversation excerpts
- rough product concepts
- design fragments

## Conversion Method

1. Identify the selected or strongest concept.
2. Extract the intended outcome.
3. Convert fragments into required capabilities.
4. Separate constraints from preferences.
5. Mark unresolved questions.
6. Identify risks that structured engineering must handle.
7. Decide readiness.
8. Produce a clean engineering brief.

## Readiness Rule

Use **Ready for Engineering: Yes** only when the packet contains:
- a clear selected concept
- a defined intent
- at least two required capabilities or behaviours
- known constraints
- at least one risk or uncertainty check

If these are absent, output **Ready for Engineering: No** and state what is missing.

## Output Format

Always use this structure:

```markdown
# Handoff Packet

## Selected Concept
[Chosen idea]

## Intent
[What the skill/design/system is meant to achieve]

## Source Material Preserved
- [Important phrase, mechanism, image, or design move worth keeping]

## Required Capabilities
- [Capability 1]
- [Capability 2]

## Constraints
- [Hard constraint]
- [Soft constraint, labelled if applicable]

## Open Risks
- [Risk or uncertainty]

## Missing Variables
- [Question or required decision]

## Suggested Layer
[L0 / L1 / L2 / L3 / L4, if relevant]

## Suggested Module
[Creative / Evaluation / Linking / Execution / Domain / Other]

## Suggested Abstraction Level
[Conceptual / Structural / Operational / Output]

## Ready for Engineering?
Yes / No

## Engineering Brief
[Clean brief for the structured skill]
```

## What Not To Do

Do not:
- score the idea
- reject imaginative material merely because it is incomplete
- invent missing constraints as facts
- certify production readiness
- create dense links before the structured system examines them

## Optional Compression

If the source material is long, compress it into:

```markdown
## Preserved Essence
[3-5 bullet summary]

## Discarded Noise
[What was removed and why]
```

## Failure Risks

Watch for:
- over-cleaning: killing the creative value
- under-cleaning: passing chaos forward
- false readiness
- unlabelled assumptions
- missing constraints

## Self-Check

Before final output, verify:

- The selected concept is explicit.
- The engineering brief can stand alone.
- Missing variables are not disguised as decisions.
- The packet is structured enough for evaluation.

## Repository Relationship Contracts

These contracts define how this bridge sits inside the Option B skill-builder system. They are behavioural contracts, not casual “see also” links.

### Relationship Contract: Skill Handoff Bridge → Creative Exploration Engine

**Source:** Skill Handoff Bridge  
**Target:** Creative Exploration Engine  
**Relationship Direction:** Skill Handoff Bridge ← Creative Exploration Engine for source material; Bridge → Creative Exploration Engine when the draft is not ready  
**Reciprocal Direction:** Creative Exploration Engine → Skill Handoff Bridge with parseable Creative Drafts  
**Relationship Type:** translation  
**Relationship Strength:** strong  
**Strength Reason:** the bridge depends on creative drafts as its normal input, while creative work depends on the bridge to become buildable.  
**Direct or Indirect:** direct  
**Chain Position:** intermediary in `Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System`  
**Reason for Relationship:** the bridge turns creative material into a structured packet without pretending to evaluate it fully.  
**Behavioural Impact:** when the source draft is too loose, this skill must return it for another creative pass rather than inventing missing structure.  
**Source Update Requirement:** preserve source material that matters and state what was removed.  
**Target Update Requirement:** creative drafts must expose constraints, unresolved questions, and a recommended direction.  
**Affected Files:** `skill-handoff-bridge/SKILL.md`, `creative-exploration-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Skill Handoff Bridge → Structured Skill Engineering System

**Source:** Skill Handoff Bridge  
**Target:** Structured Skill Engineering System  
**Relationship Direction:** Skill Handoff Bridge → Structured Skill Engineering System  
**Reciprocal Direction:** Structured Skill Engineering System ← Skill Handoff Bridge  
**Relationship Type:** translation  
**Relationship Strength:** critical  
**Strength Reason:** the bridge is the controlled handshake that prevents raw creative noise from becoming false structure inside the engineering skill.  
**Direct or Indirect:** direct  
**Chain Position:** middle link in the standard chain  
**Reason for Relationship:** engineering needs a clean brief with intent, capabilities, constraints, risks, and readiness status.  
**Behavioural Impact:** this skill must output an engineering brief that can stand alone and must not certify production readiness.  
**Source Update Requirement:** include readiness status, risks, missing variables, and a standalone engineering brief.  
**Target Update Requirement:** accept bridge packets as preferred structured input and verify readiness before engineering.  
**Affected Files:** `skill-handoff-bridge/SKILL.md`, `structured-skill-engineering-system/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Skill Handoff Bridge → Relationship Contract Engine

**Source:** Skill Handoff Bridge  
**Target:** Relationship Contract Engine  
**Relationship Direction:** Skill Handoff Bridge → Relationship Contract Engine when a handoff packet includes skills, sub-skills, or links  
**Reciprocal Direction:** Relationship Contract Engine → Skill Handoff Bridge by defining what relationship metadata the packet should preserve  
**Relationship Type:** orchestration  
**Relationship Strength:** moderate  
**Strength Reason:** bridge packets frequently identify modules and dependencies, but the contract engine performs the real link validation.  
**Direct or Indirect:** conditional direct  
**Chain Position:** side-link from bridge phase into relationship governance  
**Reason for Relationship:** relationship candidates need to survive the handoff without being accepted prematurely.  
**Behavioural Impact:** this skill must separate candidate relationships from accepted contracts.  
**Source Update Requirement:** list proposed links as candidates unless already audited.  
**Target Update Requirement:** convert candidate relationships into accepted, rejected, or deferred contracts.  
**Affected Files:** `skill-handoff-bridge/SKILL.md`, `relationship-contract-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified


### Relationship Contract: Skill Handoff Bridge → Skill Creator

**Source:** Skill Handoff Bridge  
**Target:** Skill Creator  
**Relationship Direction:** Skill Handoff Bridge → Skill Creator  
**Reciprocal Direction:** Skill Creator ← Skill Handoff Bridge  
**Relationship Type:** translation  
**Relationship Strength:** strong  
**Strength Reason:** Skill Creator works best when it receives a clean packet containing intent, capabilities, constraints, risks, and expected outputs rather than raw creative noise.  
**Direct or Indirect:** direct  
**Chain Position:** bridge-to-build transition in `Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System → Skill Creator`  
**Reason for Relationship:** handoff packets give Skill Creator enough structure to draft `SKILL.md`, create evals, and identify missing variables.  
**Behavioural Impact:** the bridge must produce packets that are buildable; Skill Creator should preserve bridge constraints and ask only for missing information.  
**Source Update Requirement:** include skill-building details such as trigger conditions, expected output format, risks, and test suitability.  
**Target Update Requirement:** consume bridge packets as preferred input for skill creation.  
**Affected Files:** `skill-handoff-bridge/SKILL.md`, `skill-creator/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 003.700  
**Classification:** Systems translation, interface, and workflow handoff

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.
