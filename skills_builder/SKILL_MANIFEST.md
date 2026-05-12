# Skill Manifest

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/

## Skills

| Skill | Dewey-style Code | Role | Layer | Module | Main Relationship |
|---|---:|---|---|---|---|
| Option B Skill Builder | 005.120 | Main router for the skill-building repo | L0/L3 Hybrid | Orchestration | Routes to the correct sub-skill |
| Creative Exploration Engine | 153.350 | Generates rough ideas and variants | L2 Support | Creative | Upstream source for bridge |
| Skill Handoff Bridge | 003.700 | Converts messy ideas into engineering packets | L2 Support | Translation | Middle of the controlled handshake |
| Structured Skill Engineering System | 003.100 | Defines skill architecture, evaluation standards, failure logic, and scale control | L0/L4 Hybrid | Engineering / Audit | Downstream validator and ruleset |
| Skill Creator | 005.100 | Creates, tests, iterates, packages, and description-optimises actual skills | L3/L4 Hybrid | Execution / Evaluation | Practical execution loop for skill building |
| Relationship Contract Engine | 003.500 | Maintains reciprocal, weighted, chain-aware skill links | L2/L4 Hybrid | Linking / Audit | Sidecar relationship governor |
| Skill Classification Engine | 025.400 | Assigns Dewey-style identity codes for listing, indexing, and future skill linking | L2/L4 Hybrid | Classification / Indexing | Sidecar catalogue governor |

## Default Workflow

```text
Creative Exploration Engine
→ Skill Handoff Bridge
→ Structured Skill Engineering System
→ Skill Creator
```

## Sidecar Governance

```text
Any skill/sub-skill relationship change
→ Relationship Contract Engine
→ Updated affected files
→ Relationship map audit

Any skill/sub-skill identity, listing, or catalogue change
→ Skill Classification Engine
→ Updated metadata and classification index
→ Manifest audit
```

## Resource-Heavy Sub-Skill

`skill-creator` carries bundled scripts, agents, assets, and references. Its main `SKILL.md` stays concise and points to heavier resources only when needed.

## Rule of Thumb

Creative work may propose links. The bridge may preserve link candidates. Structured engineering may require validation. Skill Creator may apply repository changes. Relationship Contract Engine makes links official. Skill Classification Engine gives skills stable shelf marks for future listing and discovery.
