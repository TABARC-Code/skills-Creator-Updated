# Skill Builder System

### A modular framework for creating, testing, refining, linking, classifying, and scaling AI skills without the whole thing turning into unmaintainable prompt soup.

Built around one fairly stubborn idea:

> creativity and engineering should cooperate, not occupy the same chair at the same time.

Most prompt systems eventually collapse because they try to do everything in one layer.
They brainstorm, structure, evaluate,, optimise, classify, benchmark, and manage dependencies simultaneously until the instructions resemble archaeological sediment.

This repo splits those responsibilities apart properly.

The system uses a staged workflow:

```text id="jsfcmh"
Creative Exploration
→ Handoff Bridge
→ Structured Engineering
→ Skill Creation & Evaluation
↔ Relationship Contracts
↔ Classification & Indexing
```

The creative layer explores ideas quickly and loosely without prematurely strangling them with rigid evaluation. The bridge layer translates rough concepts into something coherent enough to engineer. The structured layer then handles testing, constraints, benchmarking, versioning, scale control, and relationship management.

Which sounds obvious written down, admittedly.
Software engineering is full of things that sound obvious after you've watched systems fail from not doing them.

The repo also includes a relationship contract engine that treats links between skills as actual structural relationships rather than decorative backlinks pretending to be architecture. Every relationship carries direction, weight, behavioural impact, reciprocal logic, and audit information. Because “these things are vaguely related” stops being useful somewhere around skill number twelve.

There’s also a lightweight Dewey-style classification layer for long-term organisation and future graph traversal. Skills quietly inherit classification references based on what they actually do — writing, programming, systems design, mechanics, analysis, etc. Mostly this exists because future-you won’t remember where everything lives, no matter how confident present-you feels about it.

The framework supports:

* modular skill creation.
* Iterative improvement loops
* structured evaluation workflows
* benchmark generation
* blind comparison testing
* relationship auditing
* chain-aware linking
* trigger optimisation
* classification indexing
* scalable skill ecosystems
* repository consistency checks

It’s designed for people building large or evolving skill libraries rather than one-off prompts taped together with optimism and caffeine.

The system deliberately separates:

* Ideation,
* translation,
* Engineering,
* Evaluation,
* governance,
* and indexing,

so each layer can specialise instead of becoming an overgrown monolith with emotional support markdown.

It’s heavier than a single-file prompt setup.
That’s intentional.

Small systems survive chaos surprisingly well. Larger systems absolutely do not. Eventually every loosely-structured prompt ecosystem reaches the point where nobody knows:

* What depends on what,
* Which instructions still matter,
* Why two skills conflict,
* or whether changing one file quietly breaks six others downstream.

This repo exists to stop that happening.

Or at least delay it long enough to remain useful.

---

### NOTE

> There’s also a Dewey Decimal classification layer in here, partly because organising large knowledge systems turns out to map surprisingly well onto organising large skill systems, and partly because the Dewey system has become a bit of an autistic obsession lately. Fair warning.

> Oddly though, it works.

> The numeric hierarchy creates a clean binary-style linking and listing structure for skills, sub-skills, relationships, and future traversal systems. Once the repo starts growing, having deterministic classification paths becomes significantly more useful than “I’ll just grep for it later” — which is historically not a strategy with a great success rate.

