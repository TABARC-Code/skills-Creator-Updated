# Option B Skill System: Creative → Bridge → Structured → Creator

**Author:** TABARC-Code

This repo is a six-part skill-building system. It keeps fast creative exploration separate from structured engineering, then adds a practical Skill Creator loop and a relationship contract layer so the whole thing does not slowly mutate into a charming pile of Markdown spaghetti.

## The system

1. `creative-exploration-engine` — fast ideation, variants, fragments, and rough direction.
2. `skill-handoff-bridge` — turns rough creative material into a structured handoff packet.
3. `structured-skill-engineering-system` — defines hierarchy, evaluation, failure logic, scale control, and engineering standards.
4. `skill-creator` — creates, tests, improves, packages, and description-optimises real skills using bundled eval tools.
5. `relationship-contract-engine` — keeps skill and sub-skill links reciprocal, weighted, chain-aware, and auditable.
6. `skill-classification-engine` — assigns Dewey-style identity codes for future listing, indexing, and cleaner skill linking.

## Recommended workflow

```text
Creative Exploration Engine
→ Skill Handoff Bridge
→ Structured Skill Engineering System
→ Skill Creator
↔ Relationship Contract Engine when links, sub-skills, chains, or reciprocal updates are involved
↔ Skill Classification Engine when skills need catalogue identity, Dewey-style codes, or future listing support
```

The creative skill must not self-certify. The bridge must not over-evaluate. The structured engineering skill defines what reliability means. The Skill Creator does the practical building and eval loop. The Relationship Contract Engine keeps the repository’s links honest. The Skill Classification Engine gives every major skill a Dewey-style shelf mark so future browsing does not become archaeological work.

## What this does

This is a skill builder, but not just a “generate me a prompt” toy.

It helps you:

- turn a rough idea into a reusable skill
- split messy ideation from formal validation
- write `SKILL.md` files with trigger-aware descriptions
- create realistic eval prompts
- run qualitative and quantitative review where the environment supports it
- compare skill output against baselines
- improve skills from user feedback and benchmark evidence
- package finished skills
- prevent skill networks from bloating into vague backlink soup

## Skill Creator layer

`skill-creator` contains the practical workflow and bundled tooling adapted from the upstream Skill Creator material.

It includes:

- grader, comparator, and analyzer agent instructions
- JSON schemas for evals, grading, benchmark, and feedback files
- eval viewer and trigger eval review HTML assets
- scripts for benchmark aggregation, review generation, trigger optimisation, validation, and packaging
- a concise `SKILL.md` that points to the heavier resources only when needed

The original full Skill Creator source is preserved in:

```text
skill-creator/references/full-skill-creator-source.md
```

That file is deliberately not crammed into the main skill body. Progressive disclosure exists for a reason, even if Markdown sometimes pretends otherwise.

## Relationship Contract Layer

The repo treats skill links as contracts, not polite little backlinks. If a skill links to another skill, the affected files must say what changes on both sides.

Every accepted relationship must define:

- source and target
- direction and reciprocal direction
- relationship type
- strength or weight
- reason for the weight
- direct, indirect, chained, or conditional status
- behavioural impact
- update requirements for both sides
- audit status

Sub-skills follow the same rules as parent skills. A parent link does not automatically apply to every sub-skill, because that would be tidy, convenient, and usually wrong.

See `RELATIONSHIP_MAP.md` for the current verified contracts.

## Useful files

| File | Purpose |
|---|---|
| `SKILL_MANIFEST.md` | Repo index of skills and roles |
| `RELATIONSHIP_MAP.md` | Current verified relationship contracts |
| `USAGE.md` | How to run the workflow in practice |
| `EXAMPLE_WORKFLOW.md` | Worked example of idea → skill creation |
| `NOTES.md` | Human-readable update notes |
| `skill-creator/references/schemas.md` | Eval and grading JSON schemas |

## Design note

This is heavier than a single all-in-one skill. That is intentional. Lightweight systems are lovely right up until they are not.


## Skill Classification Layer

`skill-classification-engine` adds Dewey-style identity codes to skills and sub-skills. This is for future listing, search, grouping, and skill linking.

It does not replace relationship contracts. A classification code says where something sits on the shelf; a relationship contract says what it actually changes.
