# Example Workflow

**Author:** TABARC-Code

This shows how the system turns an idea into a buildable skill.

## User idea

> I want a skill that helps me turn messy tabletop game notes into clean scenario briefings.

## 1. Creative Exploration Engine

```markdown
# Creative Draft

## Core Idea
A skill that converts chaotic tabletop scenario notes into clear, playable briefing packs.

## Variants
1. Mission brief style: objective, forces, map notes, victory conditions.
2. Narrative campaign style: mood, factions, secrets, consequences.
3. Referee prep style: hidden information, triggers, escalation, likely player questions.

## Useful Fragments
- “briefing pack” output
- hidden referee notes separated from player-facing text
- map assumptions clearly labelled
- victory condition sanity check

## Unresolved Questions
- Is this for historical wargames, RPGs, skirmish games, or all of them?
- Should it produce printable handouts?

## Recommended Direction
Start with a mission-brief skill because it has the clearest structure and easiest tests.

## Handoff Readiness
Ready for Bridge
```

## 2. Skill Handoff Bridge

```markdown
# Handoff Packet

## Selected Concept
A mission-briefing skill for tabletop scenarios.

## Intent
Turn messy notes into a clear scenario pack that a player or referee can use at the table.

## Required Capabilities
- identify player-facing vs referee-only material
- structure objectives, forces, terrain, setup, special rules, and victory conditions
- flag missing assumptions
- produce a clean Markdown briefing

## Constraints
- do not invent historical facts
- label assumptions
- keep secret information separate

## Open Risks
- user notes may be incomplete
- different game systems use different terms

## Ready for Engineering?
Yes

## Engineering Brief
Create a skill that converts rough tabletop scenario notes into structured scenario briefings with separate player-facing and referee-only sections, clear assumptions, and missing-information flags.
```

## 3. Structured Skill Engineering System

Defines:

- Layer: L1 Domain
- Module: Domain / Execution
- Abstraction: Operational
- Trigger conditions: messy scenario notes, tabletop briefings, player handouts, referee packs
- Must not activate: general fiction writing with no playable scenario intent
- Eval plan: baseline note cleanup, missing-info case, secret-information separation case

## 4. Skill Creator

Creates:

```text
scenario-briefing-skill/
├── SKILL.md
└── evals/
    └── evals.json
```

Then runs the practical loop:

1. draft skill
2. create starter evals
3. run or simulate test prompts
4. review outputs with the user
5. revise skill
6. repeat
7. optimise description if useful
8. package skill

## 5. Relationship Contract Engine

If this new scenario skill links to, say, a `historical-research` skill and a `document-formatting` skill, the relationship engine records both sides:

```text
scenario-briefing-skill → historical-research
historical-research ← scenario-briefing-skill

scenario-briefing-skill → document-formatting
document-formatting ← scenario-briefing-skill
```

Each link gets direction, type, strength, reason, behaviour change, and audit status.

No “see also historical research” nonsense pretending to be architecture.


## Classification Pass

After the skill is drafted and linked, run the Skill Classification Engine.

Example result:

```yaml
metadata:
  dewey_decimal_code: "005.100"
  classification_label: "Computer programming, programs, and reusable workflow creation"
```

This gives the skill a shelf mark for future listing. It does not prove dependency, usefulness, or quality. Annoying, but important.
