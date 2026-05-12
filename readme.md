# Skill Builder System

### Structured creative skill engineering without the usual prompt-spaghetti catastrophe

**Author:** TABARC-Code
GitHub: [TABARC-Code](https://github.com/TABARC-Code)

---

## What this is

This repo is a part ego proheject that is a ebuild of tthe Anthropic Claude skill creator to be much more funtional. So more a modular skill-building system designed to stop large prompt/skill ecosystems slowly mutating into an unmaintainable haunted forest of contradictory instructions and mystery links.

Which, to be fair, is what most of them eventually become. I've been here calling my self out as well.

The core idea is simple:

> Separate creativity from engineering.

Do not force the same system to:

* brainstorm wildly,
* structure outputs,
* validate logic,
* manage relationships,
* optimise triggers,
* benchmark behaviour,
* and maintain consistency,

all at the same time.

Because that’s how you end up with a 4,000-line “universal prompt framework” nobody wants to touch six weeks later.

---

# The architecture

```text
Creative Exploration
        ↓
Handoff Bridge
        ↓
Structured Engineering
        ↓
Skill Creator
        ↕
Relationship Contract Engine
        ↕
Classification Engine
```

Each part exists for a reason.

Each part has boundaries.

That matters more than people think.

---

# What it actually does

This system builds and maintains skills properly.

Not just:

> “generate me a prompt”

but:

* create skills,
* refine skills,
* evaluate skills,
* benchmark skills,
* classify skills,
* manage skill relationships,
* scale skill networks,
* prevent structural drift,
* and stop everything collapsing into vague backlink soup.

There’s also a Dewey-style classification layer now, because once you get beyond a handful of skills you rapidly discover that “I’ll just remember where everything is” was optimism masquerading as architecture.

---

# Why the split system exists

Most systems either:

| Type                     | Failure                                        |
| ------------------------ | ---------------------------------------------- |
| Pure creative systems    | chaotic nonsense                               |
| Pure engineering systems | rigid dead outputs                             |
| Single-layer hybrids     | eventually collapse under their own complexity |

So this separates the workflow into specialised stages.

Mess first.
Structure second.
Validation third.

Turns out that works better.

---

# Core components

---

## 1. Creative Exploration Engine

Fast ideation.

Loose structure.
High variance.
Exploration-first.

This is where:

* weird ideas,
* alternate directions,
* mechanics,
* themes,
* systems,
* structures,

all get generated before evaluation starts strangling things prematurely.

Importantly:

It does **not** pretend rough ideas are finished products.

A surprisingly rare feature for Ai i appreciate.

---

## 2. Handoff Bridge

The translator layer.

This converts:

```text
Interesting but chaotic concept
```

into:

```text
Something the engineering layer can actually work with
```

Without this stage, most systems either:

* over-engineer too early,
* or never stabilise at all.

The bridge extracts:

* intent,
* constraints,
* useful fragments,
* behavioural goals,
* implementation direction.

Basically the difference between:

> “cool idea”

and:

> “usable specification”.

---

## 3. Structured Skill Engineering System

This is where the repo stops being polite.

The engineering layer handles:

* evaluation,
* test prompts,
* scoring,
* assertions,
* relationship logic,
* regression tracking,
* structure enforcement,
* versioning,
* scale control.

This is the part that asks:

> “Does this actually work repeatedly?”

rather than:

> “Did it produce one nice-looking output once?”

Very different question.

---

## 4. Skill Creator

The operational workflow system.

This handles:

* drafting skills,
* creating evals,
* iterative improvement,
* benchmark generation,
* blind comparison,
* description optimisation,
* packaging.

Essentially:

```text
idea → tested skill → packaged output
```

with significantly less guesswork than normal prompt iteration.

---

## 5. Relationship Contract Engine

One of the bigger structural additions.

This prevents “links” from becoming meaningless references.

A relationship only exists if it causes:

* behavioural change,
* constraint inheritance,
* dependency,
* execution impact,
* auditing,
* translation,
* or structural influence.

Not:

> “these sound vaguely related”.

Every relationship includes:

* direction,
* reciprocal logic,
* weight,
* reason,
* behavioural impact,
* audit tracking.

Which sounds excessive until you’ve watched a large interconnected system implode because nobody knew what depended on what anymore.

---

## 6. Classification Engine

A lightweight Dewey-style classification system.

When new skills are created, the system quietly analyses:

* domain,
* purpose,
* behaviour,
* primary function,

and assigns classification references.

Mostly this exists because future-you is always angrier than present-you.

Especially after skill number 40.

---

# What this repo is *not*

Its not:

* a magic universal AI framework,
* a one-click prompt generator,
* “AGI architecture”,
* a vibe-driven automation shrine,
* or an excuse to avoid thinking about systems design.

It’s infrastructure.

Messy human creative infrastructure, admittedly, but still infrastructure.

---

# Design philosophy

A few core principles drive the whole thing:

### Separate concerns

Creative systems and validation systems should not fully control each other.

### Relationships must mean something

No decorative backlinking.

### Skills should scale cleanly

Small systems tolerate chaos. Large ones absolutely do not.

### Iteration beats rigidity

The goal is survivable evolution, not perfect first drafts.

### Structure should support creativity, not suffocate it

Important distinction.

---

# Repository structure

```text
skill-builder/
├── creative-exploration-engine/
├── handoff-bridge/
├── structured-skill-engineering/
├── skill-creator/
├── relationship-contract-engine/
├── skill-classification-engine/
├── references/
├── assets/
├── scripts/
├── tests/
├── README.md
├── DESCRIPTION.md
├── RELATIONSHIP_MAP.md
├── SKILL_MANIFEST.md
└── CLASSIFICATION_INDEX.md
```

Fairly normal. Intentionally boring.

If your architecture diagram starts resembling occult geometry, things have probably gone wrong.

---

# Current state

The system now supports:

* modular skill creation
* structured evaluation
* reciprocal relationship contracts
* chain-aware linking
* benchmark workflows
* trigger optimisation
* classification indexing
* version-aware iteration
* scale-conscious architecture

Which is enough to be useful without immediately becoming unbearable.

Hopefully.

---

# Known trade-offs

This repos is:

* more structured than lightweight prompt systems,
* more complex than single-file skills,
* slower to set up initially.

That’s the price of not having the whole thing collapse into contradictory sludge later.

Engineering is mostly just choosing which problems you’d rather have.

---

# Future plans

Likely additions:

* visual relationship maps
* automated dependency analysis
* skill health diagnostics
* graph-based traversal
* conflict resolution tooling
* better benchmark visualisation
* partial autonomous refactoring

And probably a few things that future-me will regret architecturally. but thatss him.

---

Note@ The dewey Deimal sub skill is partly an autistic thing i am currently obbsessing over nd my thinking is that its a good classification system, binary, and easy for AI can follow and understand and allows easy skill classification.
