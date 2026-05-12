---
name: relationship-contract-engine
description: 'Create, update, audit, and maintain structured relationship contracts between skills and sub-skills. Use this
  skill when a skill is created, updated, linked, cross-linked, chained, inherited, or reciprocally connected to another skill
  or sub-skill. This skill prevents vague backlinking by enforcing direction, reverse logic, link weight, chain propagation,
  behavioural impact, and reciprocal contract updates. Dewey: 003.500.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '003.500'
  classification_label: Systems relationships, dependency control, and network governance
---

# Relationship Contract Engine

Use this skill whenever skills, sub-skills, or their relationships are created, updated, linked, chained, split, merged, inherited, or audited.

This is not casual backlinking. It is a structured, auditable linking system. A link only counts if it changes behaviour, execution, interpretation, constraints, audit flow, or handoff logic.

## Core Purpose

Maintain the relationship layer of a skill repository so the system does not quietly turn into spaghetti with nice headings.

This skill ensures that:

- every direct link has a reciprocal structured update
- every relevant chain relationship is recorded with reduced or qualified weight
- reverse and cross-chain links are explicit, not assumed
- sub-skills are handled as first-class skills, not as automatic copies of their parent
- every relationship has a reason, weight, and behavioural effect
- repository notes, maps, manifests, and indexes stay consistent

## Activation Conditions

Use this skill when:

- a skill or sub-skill is created
- an existing skill changes its purpose, trigger, output, or dependency behaviour
- a link is added, removed, weakened, strengthened, or redirected
- a chain such as `A → B → C` matters to execution
- a parent skill and sub-skill relationship needs defining
- the user asks for backlinking, cross-linking, reciprocal links, relationship maps, or skill network updates
- repository consistency must be audited after edits

## Must Not Activate When

Do not activate this skill for loose inspiration, thematic similarity, or casual references unless those references are being promoted into real behavioural contracts.

If a relationship does not change behaviour, execution, interpretation, checking, or constraints, reject it or downgrade it to a note.

## Relationship Principle

A relationship contract must answer the practical question:

> What changes because this link exists?

Avoid empty terms such as:

- related to
- linked with
- see also
- connected
- associated

These are only acceptable inside a structured contract that defines direction, weight, reason, and behavioural effect.

## Relationship Strengths

Use these categories. Do not assign them mechanically.

| Strength | Meaning |
|---|---|
| critical | The target cannot function correctly without the linked skill |
| strong | The target is heavily shaped by the linked skill |
| moderate | The target is meaningfully influenced by the linked skill |
| weak | The target is lightly informed by the linked skill |
| contextual | The link only matters under specific conditions |
| optional | Useful, but not required |

Each strength must include a reason. A formatting skill may be strong for document generation but weak for planning. Context matters; pretend otherwise and the map lies.

## Relationship Types

Use one primary type per contract:

- dependency
- constraint
- enhancement
- translation
- audit
- creative influence
- execution layer
- orchestration
- inheritance
- specialisation
- chain propagation
- reciprocal contract

Secondary effects may be listed, but the primary type must stay singular.

## Structured Relationship Contract

Every skill-to-skill, sub-skill-to-sub-skill, parent-to-sub-skill, or chain relationship must use this contract:

```markdown
## Relationship Contract: [Source] → [Target]

**Source:**
[Skill or sub-skill name]

**Target:**
[Skill or sub-skill name]

**Relationship Direction:**
[A → B / B → A / A ↔ B / A governs B / A supports B / A audits B / chain position]

**Reciprocal Direction:**
[How the target records the relationship back to the source]

**Relationship Type:**
[dependency / constraint / enhancement / translation / audit / creative influence / execution layer / orchestration / inheritance / specialisation / chain propagation / reciprocal contract]

**Relationship Strength:**
[critical / strong / moderate / weak / contextual / optional]

**Strength Reason:**
[Why this weight is appropriate]

**Direct or Indirect:**
[direct / indirect / chained / conditional]

**Chain Position:**
[None / upstream / downstream / intermediary / terminal / A → B → C position]

**Reason for Relationship:**
[Concrete reason the link exists]

**Behavioural Impact:**
[What changes in reasoning, execution, checking, output, constraints, or interpretation]

**Source Update Requirement:**
[Exact instruction or metadata the source must include]

**Target Update Requirement:**
[Exact instruction or metadata the target must include]

**Affected Files:**
[Files that must be changed]

**Audit Status:**
[pending / applied / verified / rejected]
```

Do not leave placeholders in committed repository files.

## Direct Link Rule

If `A → B`, then:

- A must record that it links forward into B
- B must record how it is affected by A
- B must not merely say “linked back”
- the behavioural meaning must be explicit on both sides

## Chain Propagation Rule

For chains such as:

```text
A → B → C → D → E
```

record direct relationships strongly and indirect relationships only where they matter.

Guidance:

- A records direct link to B and any meaningful downstream dependency beyond B
- B records upstream A and downstream C
- C records its intermediary position where relevant
- D records its position between C and E
- E records relevant upstream relationships, with reduced or qualified weight

Indirect relationships usually have weaker or contextual weight unless the chain logic makes them decisive.

## Reverse and Non-Linear Relationship Rule

Do not assume all reverse links exist.

Only encode reverse-direction or cross-chain links when they are logically valid, structurally useful, or required by the system.

Examples:

```text
A → B → C → D → E
B → E
D → A
E → C
```

Each non-linear link must be written as its own contract with its own strength, reason, behavioural impact, and reciprocal update.

## Sub-Skill Handling

Sub-skills follow the same rules as parent skills.

If a sub-skill links to another sub-skill, both sides must be updated.

If a sub-skill links to a parent skill, both the sub-skill and parent skill must be updated.

If a parent skill links to a sub-skill, the contract must state whether the sub-skill is:

- inherited
- required
- optional
- specialised
- conditional
- supportive
- overriding
- downstream
- upstream

Do not assume the parent’s relationship weight applies to every sub-skill.

## Repository Update Standard

When operating on repository files:

1. Edit the actual affected files.
2. Create new files when needed.
3. Update relationship maps, indexes, manifests, notes, and README material where relevant.
4. Do not claim a file changed unless it changed.
5. Do not describe an ideal system while leaving the repository untouched.
6. After editing, audit the repository.

## Notes Style

Update notes must be brief, casual, and human-sounding.

Good:

- Tightened the skill links and added proper reciprocal relationships.
- Added weighted links so not every connection is treated as equally important.
- Updated the chain logic so indirect relationships are recorded properly.

Bad:

- Performed comprehensive bidirectional relational architecture enhancement.
- Implemented synergistic linkage optimisation.
- Updated stuff.

## Audit Checklist

After updates, check:

- every direct link has a reciprocal structured update
- every relevant chain relationship is represented
- every reverse-direction relationship is explicitly encoded where it exists
- every relationship has a strength or weight
- every weight has a reason
- sub-skills are not treated as automatic copies of parent skills
- no vague backlinking language substitutes for structure
- repository notes and indexes are updated where needed
- no files were skipped silently
- no claims are made that cannot be verified from the actual files

## Output After Execution

After repository edits, report:

1. concise summary of what changed
2. files updated or created
3. brief explanation of relationship logic added
4. short audit report
5. unresolved issues or limitations

Be plain about what was actually changed. The audit is there to catch fantasy, not decorate it.

## Repository Relationship Contracts

These contracts define how this sub-skill interacts with the existing Option B system.

### Relationship Contract: Relationship Contract Engine → Structured Skill Engineering System

**Source:** Relationship Contract Engine  
**Target:** Structured Skill Engineering System  
**Relationship Direction:** Relationship Contract Engine → Structured Skill Engineering System  
**Reciprocal Direction:** Structured Skill Engineering System → Relationship Contract Engine when relationship-heavy engineering is required  
**Relationship Type:** audit  
**Relationship Strength:** strong  
**Strength Reason:** the structured system needs link validation, but the contract engine exists specifically to enforce reciprocal, weighted, chain-aware relationships.  
**Direct or Indirect:** direct  
**Chain Position:** governance side-link attached to the engineering phase  
**Reason for Relationship:** relationship management is specialised enough to be its own sub-skill rather than a buried paragraph.  
**Behavioural Impact:** this sub-skill audits and applies link contracts before the engineering system treats the network as consistent.  
**Source Update Requirement:** produce verified contracts, update requirements, and audit status.  
**Target Update Requirement:** invoke this sub-skill whenever links, sub-skills, chains, or reciprocal updates are changed.  
**Affected Files:** `relationship-contract-engine/SKILL.md`, `structured-skill-engineering-system/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Relationship Contract Engine → Skill Handoff Bridge

**Source:** Relationship Contract Engine  
**Target:** Skill Handoff Bridge  
**Relationship Direction:** Relationship Contract Engine → Skill Handoff Bridge by defining what relationship metadata must survive handoff  
**Reciprocal Direction:** Skill Handoff Bridge → Relationship Contract Engine when candidate relationships appear in a handoff packet  
**Relationship Type:** orchestration  
**Relationship Strength:** moderate  
**Strength Reason:** the bridge should preserve link candidates, but this sub-skill validates and weights them.  
**Direct or Indirect:** conditional direct  
**Chain Position:** side-link from bridge phase into relationship governance  
**Reason for Relationship:** proposed relationships must not be lost or accidentally promoted during translation.  
**Behavioural Impact:** bridge packets should label candidate links and send them here for contract creation.  
**Source Update Requirement:** state whether candidate links are accepted, rejected, deferred, direct, indirect, or chained.  
**Target Update Requirement:** preserve link candidates without pretending they are verified contracts.  
**Affected Files:** `relationship-contract-engine/SKILL.md`, `skill-handoff-bridge/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Relationship Contract Engine → Creative Exploration Engine

**Source:** Relationship Contract Engine  
**Target:** Creative Exploration Engine  
**Relationship Direction:** Relationship Contract Engine constrains Creative Exploration Engine only when creative work proposes repository links  
**Reciprocal Direction:** Creative Exploration Engine → Relationship Contract Engine with candidate relationship ideas  
**Relationship Type:** constraint  
**Relationship Strength:** contextual  
**Strength Reason:** creative exploration should stay loose, but relationship proposals must not become accepted links without audit.  
**Direct or Indirect:** conditional direct  
**Chain Position:** side-link from creative phase into governance  
**Reason for Relationship:** early ideas often imply new skills, and those implications need proper contracts later.  
**Behavioural Impact:** this sub-skill prevents creative relationship ideas from being mistaken for applied repository structure.  
**Source Update Requirement:** reject, defer, or formalise candidate relationships with weight and reason.  
**Target Update Requirement:** label relationship ideas as candidates and avoid self-certifying them.  
**Affected Files:** `relationship-contract-engine/SKILL.md`, `creative-exploration-engine/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Relationship Contract Engine → Skill Creator

**Source:** Relationship Contract Engine  
**Target:** Skill Creator  
**Relationship Direction:** Relationship Contract Engine constrains and audits Skill Creator when skill creation or improvement affects relationships  
**Reciprocal Direction:** Skill Creator calls Relationship Contract Engine when it creates, updates, links, splits, merges, inherits, chains, or audits skills/sub-skills  
**Relationship Type:** audit  
**Relationship Strength:** strong  
**Strength Reason:** Skill Creator is one of the main places new skills and sub-skills are created, so it is also where vague links and accidental relationship drift are most likely to creep in.  
**Direct or Indirect:** conditional direct  
**Chain Position:** sidecar governance link during practical creation and update work  
**Reason for Relationship:** relationship changes made during skill creation must be reciprocal, weighted, chain-aware, and auditable.  
**Behavioural Impact:** this skill must force Skill Creator to update all affected files rather than leaving casual backlinks or half-updated manifests.  
**Source Update Requirement:** provide relationship contract validation, reciprocal update rules, and audit checks.  
**Target Update Requirement:** invoke this skill whenever creation or improvement changes repository relationships.  
**Affected Files:** `relationship-contract-engine/SKILL.md`, `skill-creator/SKILL.md`, `RELATIONSHIP_MAP.md`, `SKILL_MANIFEST.md`  
**Audit Status:** verified

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 003.500  
**Classification:** Systems relationships, dependency control, and network governance

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.


## Classification Boundary

Skill Classification Engine may provide Dewey-style identity codes for relationship maps and future listing. Treat those codes as identifiers only. A shared or adjacent classification code does not create a relationship contract by itself.
