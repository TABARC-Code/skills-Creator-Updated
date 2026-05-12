---
name: skill-classification-engine
description: 'Assign, audit, and maintain Dewey-style classification codes for skills and sub-skills so future listings, catalogues,
  relationship maps, and skill-linking systems can find and group them sensibly. Use this whenever a skill is created, renamed,
  reorganised, linked, indexed, added to a manifest, or prepared for a larger skill library. Dewey: 025.400.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '025.400'
  classification_label: Library operations, cataloguing, classification, and future indexing
---

# Skill Classification Engine

Author: TABARC-Code  
Repository: https://github.com/TABARC-Code/

Use this sub-skill to give each skill a stable catalogue identity. The codes are **Dewey-style**, not a claim of official library classification. They are a practical filing spine for future listing, search, grouping, and skill-linking.

## Core Purpose

Assign a small identity block to every skill or sub-skill so the repository can be browsed later without turning into a junk drawer with YAML.

## Identity Block

Add or maintain this metadata in each `SKILL.md` frontmatter where possible:

```yaml
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: "005.100"
  classification_label: "Computer programming, programs, and reusable workflow creation"
```

For human-facing docs, also include the same idea in tables or indexes:

```markdown
| Skill | Dewey-style Code | Classification |
|---|---:|---|
| skill-creator | 005.100 | Computer programming, programs, and reusable workflow creation |
```

## Code Selection Rules

1. Pick the primary behaviour, not the prettiest theme.
2. Prefer the most useful shelf position for future discovery.
3. Use a three-digit Dewey-style base from the broad classes below.
4. Add local decimal extensions when the repo needs finer grouping.
5. Do not let the code replace relationship contracts; classification groups skills, relationships explain behaviour.

## Useful Classes for This Repo

| Code | Use For |
|---:|---|
| 000 | Computer science, knowledge, systems, and general works |
| 001 | Knowledge and knowledge systems |
| 003 | Systems, system architecture, chains, dependencies, governance |
| 004 | Data processing and computer science |
| 005 | Computer programming, programs, data, reusable tooling |
| 006 | Special computer methods, AI, multimedia, interaction with advanced methods |
| 020 | Library and information sciences |
| 025 | Library operations, cataloguing, indexing, classification |
| 070 | News media, journalism, publishing workflows |
| 150 | Psychology, thinking, ideation, cognition |
| 300 | Social sciences, organisations, community systems |
| 400 | Language and linguistic workflows |
| 500 | Science and mathematics workflows |
| 600 | Technology, applied systems, engineering workflows |
| 700 | Arts, design, games, recreation, visual systems |
| 800 | Literature, rhetoric, criticism, writing systems |
| 900 | History, geography, worldbuilding, setting research |


## Quiet Description Tagging

When creating a new skill, inspect the skill's real purpose first: writing, mechanics, programming, design, research, systems, teaching, art, planning, or whatever the core behaviour actually is. Choose the closest Dewey-style code from `CLASSIFICATION_INDEX.md`, then add it discreetly to the `description` field in the skill frontmatter.

Use this low-noise pattern at the end of the description:

```yaml
description: Build reusable Python utilities for cleaning CSV files and validating outputs. Use this when the user needs repeatable data-processing scripts, transformations, or small automation tools. Dewey: 005.100.
```

Keep the tag small. Do not turn the description into a catalogue entry; the description still needs to trigger the skill properly. The Dewey tag is just a quiet shelf mark for future listing, indexing, and skill-linking.

## Purpose-to-Code Routing

Use the key activity, not decorative language. If a skill does several things, classify by the behaviour that decides whether the skill should trigger.

| Key Purpose | Prefer Code | Notes |
|---|---:|---|
| Skill creation, prompt systems, reusable workflows, programming tools | 005 / 005.100 | Default for skill-builder mechanics and code-like workflows |
| Systems, architecture, dependencies, chains, governance | 003 | Use for orchestration and structural logic |
| AI, multimedia, advanced computational methods | 006 | Use when the special method is the point |
| Catalogues, indexes, manifests, metadata, classification | 025 | Use for listing and retrieval systems |
| Writing, rhetoric, literature, editorial workflows | 800 / 808 | Use for prose, criticism, narrative craft, text improvement |
| Language, grammar, linguistics, translation | 400 / 418 | Use when language mechanics are central |
| Visual design, art, games, performance, creative media | 700 / 740 / 790 | Use for design/art/play-facing skills |
| Engineering, mechanics, applied technology, making | 600 / 620 | Use for physical systems, applied engineering, fabrication |
| Education, teaching, curriculum, learning support | 370 | Use when the skill teaches or structures learning |
| Psychology, cognition, ideation, mental models | 150 / 153 | Use for thinking, creativity, decision behaviour |
| Research, knowledge systems, general information work | 001 / 020 | Use when discovery and organisation matter most |
| News, journalism, publishing | 070 | Use for reporting and publishing workflows |
| History, geography, setting/world research | 900 | Use for historical, geographic, or worldbuilding research |

## Local Extensions

Use local decimals when the broad class is too chunky:

- `003.100` — systems architecture and validation
- `003.500` — relationship governance and dependency control
- `003.700` — handoff, translation, and workflow bridging
- `005.100` — skill creation and reusable tooling
- `005.120` — skill-builder systems and repositories
- `025.400` — catalogue classification and indexing
- `153.350` — creative ideation and concept generation

These extensions are repo-local. Useful beats ceremonially pure.

## Current Repository Codes

| Skill | Dewey-style Code | Classification |
|---|---:|---|
| option-b-skill-builder | 005.120 | Computer programming, programs, and skill-building systems |
| creative-exploration-engine | 153.350 | Creative ideation and concept generation |
| skill-handoff-bridge | 003.700 | Systems translation and workflow handoff |
| structured-skill-engineering-system | 003.100 | Systems architecture, validation, and control |
| skill-creator | 005.100 | Skill creation, tooling, evals, packaging |
| relationship-contract-engine | 003.500 | Systems relationships and dependency governance |
| skill-classification-engine | 025.400 | Catalogue classification and indexing |

## Behaviour

When a skill is created or changed:

1. inspect its actual purpose
2. assign or update the Dewey-style code
3. add/update frontmatter metadata
4. add/update the discreet `Dewey: xxx.xxx.` suffix in the frontmatter description
5. update `CLASSIFICATION_INDEX.md`
6. update `SKILL_MANIFEST.md` if the public listing changed
7. ask Relationship Contract Engine to update contracts only if classification changes affect links, hierarchy, or routing

## Guardrails

- Do not copy a parent skill's code automatically to a sub-skill.
- Do not use classification as a substitute for link strength, dependency logic, or behavioural contracts.
- Do not over-classify tiny helper files unless they need future discovery.
- Use plain labels. Nobody wants a filing system that sounds like it applied for a consultancy grant.

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 025.400  
**Classification:** Library operations, cataloguing, classification, and future indexing

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.
