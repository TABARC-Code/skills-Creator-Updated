# Usage

**Author:** TABARC-Code

## Plain version

Use the system like this:

```text
1. Explore the idea.
2. Bridge it into a clean brief.
3. Engineer the skill rules.
4. Build and test the skill.
5. Add relationship contracts if links changed.
```

## Recommended workflow

### 1. Start creative

Use `creative-exploration-engine` when the idea is still foggy.

Output should be a Creative Draft with variants, fragments, constraints, unresolved questions, and a recommended direction.

### 2. Convert the mess

Use `skill-handoff-bridge` when the idea is promising but not build-ready.

Output should be a Handoff Packet with selected concept, intent, capabilities, constraints, risks, readiness, and an engineering brief.

### 3. Define the engineering logic

Use `structured-skill-engineering-system` to define the skill architecture:

- layer
- module
- abstraction level
- trigger conditions
- output format
- failure modes
- evaluation plan
- scale and link controls

### 4. Build the actual skill

Use `skill-creator` to:

- draft or edit `SKILL.md`
- create `evals/evals.json`
- run the eval loop where possible
- generate review output for the human
- improve the skill from feedback
- optimise the description
- package the finished skill

### 5. Govern relationships

Use `relationship-contract-engine` whenever the work creates or changes links between skills or sub-skills.

A link is not official until both sides are updated and the relationship map agrees.

## Fast path

For quick work:

```text
Creative Exploration → Skill Creator
```

Use this only when the user explicitly wants speed over validation. Mark the output as a draft, not a finished skill.

## Proper path

For serious work:

```text
Creative Exploration → Handoff Bridge → Structured Engineering → Skill Creator → Relationship Contract audit
```

This is slower. It also fails less stupidly.


## Classifying Skills

Use `skill-classification-engine` when a skill or sub-skill needs a Dewey-style identity code for future listing, indexing, or skill linking.

Classification is not a relationship. A code helps you find a skill; a contract explains what changes when skills interact.
