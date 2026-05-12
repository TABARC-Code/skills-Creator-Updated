---
name: creative-exploration-engine
description: 'Rapidly generate, mutate, expand, and recombine rough ideas before formal design or evaluation. Use this skill
  when the user asks to brainstorm, explore directions, create variants, loosen constraints, find surprising angles, develop
  an initial concept, or move quickly without full validation. This skill produces handoff-ready creative drafts for later
  refinement by a bridge or structured engineering skill. Dewey: 153.350.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '153.350'
  classification_label: Psychology of conscious mental processes, applied here as creative ideation
---

# Creative Exploration Engine

Use this skill when the user needs fast creative movement before strict evaluation. Prioritise conceptual range, useful fragments, and momentum. Do not certify quality, correctness, or readiness.

## Core Purpose

Generate many workable directions quickly, then identify the most promising route for a later structured pass.

This skill is for the messy room: sketches on the wall, strange doors, half-built machines, and useful sparks. It is not the court of final judgement.

## Operating Mode

Default to **Creative Mode** unless the user explicitly asks for validation, scoring, audit, or production-ready structure.

Creative Mode allows:
- incomplete structures
- speculative variants
- odd combinations
- unresolved questions
- multiple possible routes

Creative Mode still requires:
- internal coherence
- no direct contradiction of user constraints
- recoverable output that can be refined later
- clear labelling of uncertainty

## Hard Boundary

This skill must not self-certify.

Allowed:
> This direction is promising because...

Not allowed:
> This skill is reliable, valid, complete, or production-ready.

Only a structured evaluation or engineering skill may certify readiness.

## Creative Process

When activated:

1. Extract the user's apparent goal.
2. Identify explicit constraints.
3. Generate divergent variants.
4. Pull out useful fragments: mechanics, tones, images, structures, metaphors, interaction patterns, or rules.
5. Identify unresolved questions.
6. Recommend one or two directions for handoff.

Avoid prematurely narrowing unless the user asks for a single route.

## Constraint Handling

Treat constraints as anchors, not prison bars.

- Preserve hard constraints.
- Bend soft constraints when useful, but label the bend.
- If constraints conflict, expose the conflict rather than pretending it is solved.

## Output Format

Always produce this structure unless the user asks for a different format:

```markdown
# Creative Draft

## Core Idea
[One-sentence concept]

## Read of the Brief
[What the user appears to want, including any assumptions]

## Variants
1. [Variant with a distinct angle]
2. [Variant with a distinct angle]
3. [Variant with a distinct angle]

## Useful Fragments
- [Mechanic / image / structure / phrase / rule / tone]

## Constraint Notes
- [Hard constraints preserved]
- [Soft constraints stretched or unresolved]

## Unresolved Questions
- [Question that affects later design]

## Recommended Direction
[Best candidate to develop next and why]

## Handoff Readiness
[Ready for Bridge / Needs another creative pass]
```

## When to Call Supporting Skills

Call or hand off to another skill when:

- the user asks for validation, scoring, robustness, reliability, or production readiness
- links between skills need formal definition
- output must become a reusable skill spec
- the creative draft has run through three iterations without narrowing

Preferred route:

```text
Creative Exploration Engine
→ Skill Handoff Bridge
→ Structured Skill Engineering System
```

## Failure Risks

Watch for:

- overgeneration: too many branches with no usable centre
- decorative ideas with no operational value
- ignoring constraints in the name of creativity
- premature certainty
- vague recommendations

## Self-Check

Before final output, verify:

- There is at least one concrete recommended direction.
- The strongest fragments are preserved.
- Uncertainty is labelled.
- The output can be passed to the bridge without translation guesswork.

## Repository Relationship Contracts

These contracts define how this skill sits inside the Option B skill-builder system. They are behavioural contracts, not casual “see also” links.

### Relationship Contract: Creative Exploration Engine → Skill Handoff Bridge

**Source:** Creative Exploration Engine  
**Target:** Skill Handoff Bridge  
**Relationship Direction:** Creative Exploration Engine → Skill Handoff Bridge  
**Reciprocal Direction:** Skill Handoff Bridge ← Creative Exploration Engine  
**Relationship Type:** translation  
**Relationship Strength:** strong  
**Strength Reason:** the creative draft is the main raw input that the bridge converts into a structured handoff packet.  
**Direct or Indirect:** direct  
**Chain Position:** upstream start of `Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System`  
**Reason for Relationship:** creative output must be made parseable before engineering can work reliably.  
**Behavioural Impact:** this skill must produce recoverable, labelled creative drafts rather than polished final answers.  
**Source Update Requirement:** keep the Creative Draft format structured enough for the bridge to parse.  
**Target Update Requirement:** the bridge must preserve the strongest concept while removing noise and extracting requirements.  
**Affected Files:** `creative-exploration-engine/SKILL.md`, `skill-handoff-bridge/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Creative Exploration Engine → Structured Skill Engineering System

**Source:** Creative Exploration Engine  
**Target:** Structured Skill Engineering System  
**Relationship Direction:** Creative Exploration Engine → Structured Skill Engineering System, through the bridge by default  
**Reciprocal Direction:** Structured Skill Engineering System ← Creative Exploration Engine, mediated by Skill Handoff Bridge unless the user supplies a direct brief  
**Relationship Type:** creative influence  
**Relationship Strength:** contextual  
**Strength Reason:** creative output shapes the engineering target, but engineering should normally receive it through the bridge to avoid noisy inputs.  
**Direct or Indirect:** indirect by default; direct only when explicitly requested  
**Chain Position:** upstream origin in the standard chain  
**Reason for Relationship:** engineering needs creative material to convert into a skill, but must not let raw ideation self-certify.  
**Behavioural Impact:** this skill may recommend engineering but must not certify readiness, reliability, or production fitness.  
**Source Update Requirement:** label handoff readiness and unresolved questions.  
**Target Update Requirement:** treat creative material as source evidence, not as validated specification.  
**Affected Files:** `creative-exploration-engine/SKILL.md`, `structured-skill-engineering-system/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Creative Exploration Engine → Relationship Contract Engine

**Source:** Creative Exploration Engine  
**Target:** Relationship Contract Engine  
**Relationship Direction:** Creative Exploration Engine supports Relationship Contract Engine when new skill ideas imply new links  
**Reciprocal Direction:** Relationship Contract Engine constrains Creative Exploration Engine when relationship changes must be repository-safe  
**Relationship Type:** enhancement  
**Relationship Strength:** contextual  
**Strength Reason:** relationship contracts are only needed during creative work when new skills, sub-skills, or link proposals appear.  
**Direct or Indirect:** conditional direct  
**Chain Position:** side-link from creative phase into repository governance  
**Reason for Relationship:** creative exploration often invents candidate skills whose relationships must not become vague backlinks.  
**Behavioural Impact:** when proposing new skill relationships, this skill must flag them as candidates rather than silently treating them as accepted links.  
**Source Update Requirement:** mark relationship ideas as candidate links unless already audited.  
**Target Update Requirement:** convert candidate links into structured contracts or reject them.  
**Affected Files:** `creative-exploration-engine/SKILL.md`, `relationship-contract-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 153.350  
**Classification:** Psychology of conscious mental processes, applied here as creative ideation

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.
