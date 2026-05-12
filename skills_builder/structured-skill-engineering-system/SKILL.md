---
name: structured-skill-engineering-system
description: 'Design, audit, improve, validate, and scale skills using strict structure, testing, failure analysis, versioning,
  hierarchy, modular grouping, and behavioural link control. Use this skill whenever the user wants to create a reliable skill,
  improve an existing skill, audit a skill, define cross-skill links, prevent network bloat, run evaluations, or turn a handoff
  packet into an engineered specification. Dewey: 003.100.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '003.100'
  classification_label: Systems architecture, validation, and control
---

# Structured Skill Engineering System

Use this skill to turn a handoff packet, rough skill, or existing skill into a reliable, testable, scalable specification.

This skill is the engineering table: rulers, stress tests, version history, failure labels, and a bin for pretty ideas that do not work.

## Core Principle

A skill is not complete because it sounds useful. It is complete when it can prove useful behaviour under structured pressure.

## Input Types

Accept:
- Handoff Packet from Skill Handoff Bridge
- existing SKILL.md
- rough skill notes
- skill network maps
- linking proposals
- evaluation results

## Operating Sequence

1. Identify the skill's purpose and trigger conditions.
2. Assign hierarchy layer, module, and abstraction level.
3. Define constraints and output format.
4. Build or improve the skill instructions.
5. Define evaluation tests.
6. Identify failure modes.
7. Define valid links only where they change behaviour.
8. Track version and regression risks.
9. Produce an audit-ready engineered specification.

## Hierarchy Layers

Every skill must declare one layer:

| Layer | Role | Description |
|---|---|---|
| L0: Core | Foundation | System rules, evaluation, constraints |
| L1: Domain | Purpose | Domain-specific work, e.g. Adventure Design |
| L2: Support | Enhancer | Supporting capabilities, e.g. UX, narrative depth |
| L3: Execution | Output | Formatting, rendering, implementation |
| L4: Audit | Verification | Testing, grading, validation |

## Modules

Assign one primary module:

- Creative
- Domain
- UX
- Systems
- Linking
- Evaluation
- Execution
- Audit

Skills may have secondary modules, but only one primary module.

## Abstraction Levels

Every skill must declare:

```markdown
**Abstraction Level:**
[Conceptual / Structural / Operational / Output]
```

Rules:
- Conceptual skills define meaning, themes, and principles.
- Structural skills define organisation, sequence, and relationships.
- Operational skills define behaviours and procedures.
- Output skills define final formats, files, presentations, or rendered results.

A higher abstraction skill must not directly micromanage output unless routed through a structural or operational rule.

## Skill Specification Template

Use this template when producing an engineered skill:

```markdown
# Engineered Skill Specification

## Skill Name
[Name]

## Purpose
[What it enables]

## Layer
[L0 / L1 / L2 / L3 / L4]

## Module
[Primary module]

## Abstraction Level
[Conceptual / Structural / Operational / Output]

## Trigger Conditions
[When it activates]

## Must Not Activate When
[False positive prevention]

## Core Behaviour
[What it does]

## Procedure
1. [Step]
2. [Step]
3. [Step]

## Output Format
[Exact or flexible format]

## Constraints
- [Hard rule]
- [Hard rule]

## Evaluation Tests
[Baseline / edge / ambiguity / failure tests]

## Accepted Links
[Behaviour-changing links only]

## Rejected or Deferred Links
[Rejected links and reasons]

## Failure Risks
[Known weak points]

## Version
v1.0
```

## Evaluation System

Minimum evaluation set:

| Test Type | Count |
|---|---:|
| Baseline / happy path | 3 |
| Edge cases | 3 |
| Ambiguity tests | 2 |
| Failure expectation tests | 2 |

Use this scoring model unless a domain-specific model is required:

| Metric | Weight |
|---|---:|
| Accuracy | 40% |
| Completeness | 25% |
| Consistency | 20% |
| Clarity | 15% |

Pass criteria:
- 85% or higher: Pass
- 70-84%: Improve
- below 70%: Fail

If the task is subjective, define concrete interpretation for each metric before scoring.

## Failure Classification

Every failure must be tagged:

```markdown
Failure Type:
- Instruction Drift
- Format Error
- Hallucination / Fabrication
- Partial Completion
- Overgeneration
- Logical Inconsistency
- Inconsistent Evaluation
- System Bloat
- False Trigger
- Missed Trigger

Severity:
- Low / Medium / High
```

## Versioning and Regression

Every meaningful revision must include:

```markdown
Version: vX.X

Changes Made:
- [Change]

Score Delta:
- Accuracy: [+/-]
- Completeness: [+/-]
- Consistency: [+/-]
- Clarity: [+/-]

Regression Detected:
Yes / No

Notes:
[Explanation]
```

## Relationship Contract Delegation

When work involves creating, updating, removing, chaining, or auditing links between skills or sub-skills, route that part of the work through the `relationship-contract-engine`. The structured engineering system decides whether relationship governance is required; the contract engine applies the reciprocal, weighted, chain-aware contract rules.

Do not bury relationship-heavy work inside casual notes. Update the affected files and audit the result.

## Fixed Linking System

A skill link is valid only when it causes a defined behavioural change in at least one connected skill.

A link must never mean:
> These skills are related.

It must mean:
> This skill changes how that skill reasons, prioritises, produces, checks, or constrains output.

### Link Validity Test

Before creating a link, answer all five:

1. Does the source skill change the target skill's behaviour?
2. Does the target skill change the source skill's behaviour?
3. Is the influence direction clearly defined?
4. Is the influence strength defined?
5. Is there a concrete update to both skill instruction texts?

If any answer is unclear, reject or downgrade the link to a note.

### Relationship Types

Use one primary relationship type:

| Type | Meaning |
|---|---|
| Dependency | One skill cannot function properly without the other |
| Constraint | One skill limits or governs the other |
| Enhancement | One skill improves quality but is not required |
| Translation | One skill converts output into another usable form |
| Audit | One skill checks or verifies another |
| Creative Influence | One skill expands conceptual range |
| Execution Layer | One skill turns abstract design into practical output |

Only one primary type is allowed per link. Secondary effects may be listed separately.

### Direction of Influence

Every link must define direction:

| Direction | Meaning |
|---|---|
| A → B | A modifies B |
| B → A | B modifies A |
| A ↔ B | Both modify each other |
| A governs B | A has priority over B |
| A supports B | A improves B but does not override it |
| A audits B | A checks B after output |

Do not use “mutual” unless both directions are explicitly described.

### Influence Strength

Every link must assign strength:

| Strength | Meaning |
|---|---|
| critical | The target cannot function correctly without the linked skill |
| strong | The target is heavily shaped by the linked skill |
| moderate | The target is meaningfully influenced by the linked skill |
| weak | The target is lightly informed by the linked skill |
| contextual | The link only matters in specific situations |
| optional | Useful but not required |

### Link Budget

Each skill has a default link budget of 5 points:

| Strength | Cost |
|---|---:|
| critical | 3 |
| strong | 2 |
| moderate | 1 |
| weak | 0.5 |
| contextual | 0.5-2, depending on condition |
| optional | 0.5 |

Do not exceed the budget unless the user explicitly accepts complexity.

### Mandatory Link Record Format

```markdown
## Link: [Source Skill] → [Target Skill]

**Relationship Type:**
[Dependency / Constraint / Enhancement / Translation / Audit / Creative Influence / Execution Layer]

**Influence Direction:**
[Exact direction]

**Influence Strength:**
[critical / strong / moderate / weak / contextual / optional]

**Activation Phase:**
[Creative Phase / Bridge Phase / Structured Phase / Evaluation Phase / All]

**Reason for Link:**
[Concrete reason]

**Source Skill Update:**
[Exact instruction added or changed in source skill]

**Target Skill Update:**
[Exact instruction added or changed in target skill]

**Reverse Link Requirement:**
[How the target skill acknowledges or modifies the source skill]

**Secondary Effects:**
[Any other affected skills]

**Failure Risk if Missing:**
[What breaks if this link is absent]
```

### Bidirectional Rule

A bidirectional link is valid only when both sides receive distinct behavioural updates.

Bad:
> Adventure Design links to UX Design for clarity.

Good:
> Adventure Design must use UX Design to test whether player choices are readable.
> UX Design must use Adventure Design to evaluate whether clarity preserves mystery, tension, and agency.

### Cross-Link Rule

Cross-links are not automatic.

Create a cross-link only when:
1. Two supporting skills directly affect each other.
2. Their interaction changes the core skill.
3. The change can be written as a concrete instruction.

Maximum cross-links per skill: 3 by default.

### Link Rejection Rule

Reject links that are only:
- thematically similar
- aesthetically related
- loosely inspirational
- redundant with an existing skill
- too vague to change behaviour
- over budget
- hierarchy-violating

Rejected links must be listed under:

```markdown
## Rejected or Deferred Links
```

### Link Audit Checklist

Before final output, verify:

- Every declared link has a reciprocal structured update.
- Every link has one primary relationship type.
- Every link has influence direction.
- Every link has influence strength and a strength reason.
- Every link has activation phase, direct/indirect status, and chain position where relevant.
- Every source skill update is concrete.
- Every target skill update is concrete.
- Every cross-link affects the core skill.
- No link exists only as a casual reference.
- No skill appears in the map without a defined role.
- No duplicate links perform the same function.
- Sub-skills are not treated as automatic copies of parent skills.
- Relationship-heavy changes have been routed through `relationship-contract-engine`.

## Scale Control

### Modular Grouping

Group skills by module. Cross-module links require justification.

### Pruning Trigger

Run pruning:
- every 5 iterations, or
- when a network exceeds 12 skills, or
- when a skill exceeds its link budget

### Retention Test

For every skill ask:

1. Is it used in at least 20% of relevant workflows?
2. Does it provide unique behaviour?
3. Can another skill absorb its function?
4. Does it have valid behavioural links?

Outcome:
- Keep
- Merge
- Remove
- Defer

## Final Output Sections

When auditing or building a network, use:

1. Core Skill Summary
2. System Layer + Module
3. Abstraction Level
4. Trigger Conditions
5. Constraint Definitions
6. Test Set
7. Evaluation Results or Proposed Evaluation
8. Accepted Skill Links
9. Rejected or Deferred Links
10. Bidirectional Relationship Table
11. Structured Updates for Each Skill
12. Cross-Link Map
13. Influence Strength Map
14. Version History
15. Failure Analysis
16. Regression Report
17. Audit Check

## Self-Check

Before final output:

- Does the skill prove behaviour rather than merely describe intention?
- Are links behavioural, directional, weighted, and bounded?
- Is scale controlled through hierarchy, modules, pruning, and budgets?
- Are failure modes explicit?
- Is there a path from rough idea to reliable specification?

## Repository Relationship Contracts

These contracts define how this structured engineering skill sits inside the Option B skill-builder system. They are behavioural contracts, not casual “see also” links.

### Relationship Contract: Structured Skill Engineering System → Skill Handoff Bridge

**Source:** Structured Skill Engineering System  
**Target:** Skill Handoff Bridge  
**Relationship Direction:** Structured Skill Engineering System ← Skill Handoff Bridge for preferred input; Structured Skill Engineering System → Skill Handoff Bridge when a packet is incomplete  
**Reciprocal Direction:** Skill Handoff Bridge → Structured Skill Engineering System with handoff packets  
**Relationship Type:** translation  
**Relationship Strength:** critical  
**Strength Reason:** structured engineering is most reliable when the bridge supplies intent, capabilities, constraints, risks, and readiness status.  
**Direct or Indirect:** direct  
**Chain Position:** downstream end of the standard chain  
**Reason for Relationship:** engineering must not guess what the bridge should have clarified.  
**Behavioural Impact:** this skill must validate the handoff packet before treating it as engineering-ready.  
**Source Update Requirement:** return unclear or incomplete packets to the bridge with missing variables listed.  
**Target Update Requirement:** bridge outputs must include a standalone engineering brief and readiness decision.  
**Affected Files:** `structured-skill-engineering-system/SKILL.md`, `skill-handoff-bridge/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Structured Skill Engineering System → Creative Exploration Engine

**Source:** Structured Skill Engineering System  
**Target:** Creative Exploration Engine  
**Relationship Direction:** Structured Skill Engineering System → Creative Exploration Engine when failures require more ideation; Creative Exploration Engine → Structured Skill Engineering System only through bridge by default  
**Reciprocal Direction:** Creative Exploration Engine provides upstream creative material but does not certify it  
**Relationship Type:** audit  
**Relationship Strength:** contextual  
**Strength Reason:** engineering only needs to send work back to creative exploration when tests reveal a conceptual gap or the design has narrowed too early.  
**Direct or Indirect:** indirect by default; conditional direct for re-ideation requests  
**Chain Position:** downstream feedback to upstream origin  
**Reason for Relationship:** failed or over-constrained engineering should reopen exploration instead of overfitting bad structure.  
**Behavioural Impact:** this skill may request fresh variants, but must state the failure type or missing design need.  
**Source Update Requirement:** include concrete failure reason when sending work back upstream.  
**Target Update Requirement:** creative output must respond to the stated failure, not restart randomly.  
**Affected Files:** `structured-skill-engineering-system/SKILL.md`, `creative-exploration-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Structured Skill Engineering System → Relationship Contract Engine

**Source:** Structured Skill Engineering System  
**Target:** Relationship Contract Engine  
**Relationship Direction:** Structured Skill Engineering System governs when relationship validation is required; Relationship Contract Engine audits and applies the relationship layer  
**Reciprocal Direction:** Relationship Contract Engine → Structured Skill Engineering System by supplying verified contracts, maps, and audit results  
**Relationship Type:** audit  
**Relationship Strength:** strong  
**Strength Reason:** structured engineering defines when links matter, but the contract engine prevents those links from becoming vague or one-sided.  
**Direct or Indirect:** direct  
**Chain Position:** governance side-link from engineering into relationship management  
**Reason for Relationship:** link logic is too important to remain buried inside general engineering instructions.  
**Behavioural Impact:** this skill must call the contract engine whenever creating, updating, or auditing skill relationships.  
**Source Update Requirement:** route relationship-heavy work to the contract engine and respect its audit result.  
**Target Update Requirement:** provide structured contracts, reciprocal updates, weights, chain logic, and repository audit notes.  
**Affected Files:** `structured-skill-engineering-system/SKILL.md`, `relationship-contract-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified


### Relationship Contract: Structured Skill Engineering System → Skill Creator

**Source:** Structured Skill Engineering System  
**Target:** Skill Creator  
**Relationship Direction:** Structured Skill Engineering System → Skill Creator  
**Reciprocal Direction:** Skill Creator → Structured Skill Engineering System  
**Relationship Type:** execution layer  
**Relationship Strength:** critical  
**Strength Reason:** the structured system defines reliability, hierarchy, failure logic, scale control, and evaluation standards; Skill Creator turns those standards into actual drafts, evals, iterations, description optimisation, and packages.  
**Direct or Indirect:** direct  
**Chain Position:** downstream handoff after the structured engineering rules are defined  
**Reason for Relationship:** architecture without an execution loop becomes neat theory with no tyres. Skill Creator supplies the practical workflow.  
**Behavioural Impact:** this skill should route hands-on skill creation, test running, benchmark aggregation, description optimisation, and packaging into Skill Creator while preserving the engineering standards here.  
**Source Update Requirement:** define the standards Skill Creator must apply.  
**Target Update Requirement:** implement those standards in practical skill-building and eval work.  
**Affected Files:** `structured-skill-engineering-system/SKILL.md`, `skill-creator/SKILL.md`, `RELATIONSHIP_MAP.md`, `SKILL_MANIFEST.md`  
**Audit Status:** verified

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 003.100  
**Classification:** Systems architecture, validation, and control

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.
