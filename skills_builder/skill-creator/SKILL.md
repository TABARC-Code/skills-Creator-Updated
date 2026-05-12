---
name: skill-creator
description: 'Create new skills, modify existing skills, run realistic skill evals, compare skill outputs against baselines,
  improve skill instructions from feedback, package finished skills, and optimise skill descriptions for better triggering.
  Use this whenever the user wants to build a skill from an idea, turn a workflow into a reusable skill, audit a skill, iterate
  on SKILL.md, create eval prompts, run benchmark-style tests, or improve when and how a skill activates. Dewey: 005.100.'
metadata:
  author: TABARC-Code
  author_url: https://github.com/TABARC-Code/
  dewey_decimal_code: '005.100'
  classification_label: Computer programming, programs, tooling, and reusable workflow creation
---

# Skill Creator

Use this skill to build, test, improve, and package skills. It is the hands-on workshop in the Option B system: not just architecture, not just ideation, but the practical loop that turns a skill idea into something that can survive real use.

This skill inherits the repository's separation of concerns:

```text
Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System → Skill Creator
```

The earlier skills help produce the idea, handoff packet, and engineering rules. This skill runs the practical creation and improvement loop.

## Core Purpose

Create and improve skills through an iterative loop:

1. Capture what the skill should do.
2. Draft or update `SKILL.md`.
3. Create realistic test prompts.
4. Run skill outputs against baselines where the environment supports it.
5. Help the user review qualitative outputs and quantitative checks.
6. Revise the skill from feedback and benchmark evidence.
7. Repeat until the user is happy or progress stalls.
8. Optimise the skill description for triggering when appropriate.
9. Package the finished skill if packaging tools are available.

Do not turn this into theatre. If files can be changed, change them. If a test can be run, run it. If the current environment cannot support subagents, browser review, or Claude CLI subprocesses, say so plainly and use the fallback workflow.

## Communication Style

Match the user's technical comfort.

Terms like "evaluation" and "benchmark" are usually fine. Terms like "JSON", "assertion", and "schema" are fine with technical users, but briefly define them if the user seems less familiar. Keep explanations practical. Nobody needs a sermon about data structures while their skill is on fire.

## Entry Points

Figure out where the user already is:

| User State | What to do |
|---|---|
| They have only an idea | Capture intent, ask edge-case questions, draft the skill |
| They have a workflow in the conversation | Extract the workflow, tools, corrections, and output formats before asking gaps |
| They have an existing skill | Audit it, create or update evals, then iterate |
| They only want to vibe | Use a lighter creative pass, but label that it is not full validation |
| They want proof | Run or design the full eval loop with baselines, grading, and review output |

## Capture Intent

Before drafting, establish:

1. What should this skill enable the model to do?
2. When should it trigger?
3. When should it *not* trigger?
4. What output format should it produce?
5. Are there files, tools, scripts, or dependencies involved?
6. What counts as success?
7. Does the skill need objective tests, human review, or both?

Use conversation history first. Do not make the user repeat facts already present.

## Writing the Skill

A normal skill folder looks like this:

```text
skill-name/
├── SKILL.md
├── scripts/
├── references/
└── assets/
```

`SKILL.md` needs YAML frontmatter with at least:

```yaml
---
name: skill-name
description: What it does and when to use it. Make this slightly pushy so the skill does not undertrigger.
---
```

Keep `SKILL.md` lean enough to load cleanly. If the instructions are getting too long, move heavy detail into `references/`, reusable code into `scripts/`, and templates or visual material into `assets/`.

## Drafting Rules

Prefer instructions that explain *why* the behaviour matters. A wall of brittle MUST/NEVER rules often creates wooden behaviour and accidental edge-case failures.

Use:

- clear trigger conditions
- output templates where useful
- concrete examples
- explicit failure risks
- dependency notes
- test prompts that sound like real users, typos and all

Avoid:

- vague “be helpful” filler
- hidden behaviour that would surprise the user
- overfitted fixes that only solve one test case
- security-surprising behaviour, exploit support, data exfiltration, or misleading automation


## Quiet Classification During Creation

When writing or updating a `SKILL.md`, also run the Skill Classification Engine quietly. Identify the skill's key purpose — for example writing, mechanics, programming, design, research, teaching, systems, or art — then choose the nearest Dewey-style code from the classification index. Add the code in two places:

1. `metadata.dewey_decimal_code` and `metadata.classification_label`
2. a small suffix at the end of the frontmatter `description`, using this pattern: `Dewey: 005.100.`

Keep this discreet. Do not explain it unless the user asks. The description still has to work as a trigger, so the code should never crowd out the useful “when to use this skill” wording.

## Test Case Workflow

After a draft exists, create 2–3 realistic starter test prompts. Save them to `evals/evals.json` using the schema in `references/schemas.md`.

Initial evals should include prompts and expected outputs. Draft assertions after or while runs are happening, not before the task is understood.

Use this shape:

```json
{
  "skill_name": "example-skill",
  "evals": [
    {
      "id": 1,
      "prompt": "User's task prompt",
      "expected_output": "Description of expected result",
      "files": [],
      "expectations": []
    }
  ]
}
```

## Full Evaluation Loop

When the environment supports subagents and scripts, use the full loop:

1. Create a workspace beside the skill directory: `<skill-name>-workspace/`.
2. For each eval, run both with-skill and baseline runs in the same iteration.
3. Save each run under `iteration-N/eval-name/with_skill/outputs/` and baseline output under `without_skill/`, `old_skill/`, or the relevant comparison directory.
4. Draft objective assertions while runs are happening.
5. Save timing data when available.
6. Grade outputs with `agents/grader.md` and save `grading.json`.
7. Aggregate results with `scripts/aggregate_benchmark.py`.
8. Generate the review UI with `scripts/generate_review.py`.
9. Let the user review outputs before making major revisions.
10. Read feedback, improve the skill, and repeat in the next iteration directory.

The human review step matters. Do not silently replace it with your own vibes unless the environment cannot support the viewer or the user explicitly asks for a quicker pass.

## Fallback Evaluation Loop

If subagents, browser UI, or Claude CLI execution are unavailable:

1. Run test prompts one at a time yourself using the draft skill instructions.
2. Skip baseline benchmarking if a fair baseline cannot be produced.
3. Present the outputs directly in chat or as files.
4. Ask the user for inline feedback.
5. Revise the skill and rerun the same tests.
6. Record what could not be tested and why.

This is less rigorous, but still useful. Do not pretend it is equivalent to the full benchmark loop.

## Improvement Rules

When revising a skill:

- generalise from feedback instead of overfitting one test
- remove instructions that waste time or cause repeated unhelpful work
- bundle repeated helper scripts when several evals recreate the same tool
- explain why new instructions matter
- keep the description aligned with actual trigger behaviour
- preserve the original skill name when updating an installed skill unless the user explicitly wants a rename

## Description Optimisation

After the skill works, offer description optimisation.

Create around 20 trigger eval queries with should-trigger and should-not-trigger labels. Use realistic prompts with context, file names, casual phrasing, near-misses, and edge cases.

Use:

- `assets/eval_review.html` for human review of trigger evals
- `scripts/run_loop.py` for iterative trigger optimisation where Claude CLI is available
- `scripts/run_eval.py` and `scripts/improve_description.py` for lower-level pieces
- `scripts/generate_report.py` for the HTML report

Apply the best description to the `SKILL.md` frontmatter only after reviewing before/after behaviour and scores.

## Packaging

When packaging is available, use:

```bash
python -m scripts.package_skill <path/to/skill-folder>
```

The package script validates the skill first. Keep `evals/` out of packaged distribution unless the packaging policy changes.

## Bundled Resources

Read these only when needed:

| Resource | Use |
|---|---|
| `agents/grader.md` | Grade assertions against transcripts and outputs |
| `agents/comparator.md` | Blind A/B comparison between two outputs |
| `agents/analyzer.md` | Post-hoc analysis after blind comparison |
| `references/schemas.md` | JSON structures for evals, grading, benchmark, feedback |
| `references/full-skill-creator-source.md` | Full upstream source text this sub-skill was adapted from |
| `scripts/*.py` | Eval, benchmark, trigger optimisation, reporting, validation, packaging |
| `assets/eval_review.html` | Review page for trigger eval sets |
| `assets/viewer.html` | Review UI template used by eval viewer |

## Relationship Contract Delegation

When creating or updating skills changes relationships, links, sub-skills, chains, or parent/child structure, invoke the Relationship Contract Engine.

The Skill Creator may propose and apply skill changes, but relationship changes are not official until reciprocal structured contracts are updated in all affected files and the relationship map is audited.

## Output When Updating a Repository

After actual repository work, report:

1. concise summary of changes
2. files created or updated
3. relationship logic added or changed
4. audit result
5. unresolved issues or environment limits

Do not claim file edits that did not happen. Tedious, yes. Better than lying with confidence.

## Repository Relationship Contracts

### Relationship Contract: Skill Creator → Structured Skill Engineering System

**Source:** Skill Creator  
**Target:** Structured Skill Engineering System  
**Relationship Direction:** Skill Creator executes and iterates the practical skill-building loop under the architectural constraints of Structured Skill Engineering System  
**Reciprocal Direction:** Structured Skill Engineering System defines the reliability, evaluation, hierarchy, failure, and scaling standards that Skill Creator applies  
**Relationship Type:** execution layer  
**Relationship Strength:** critical  
**Strength Reason:** without the structured system, Skill Creator can build prompts but cannot reliably enforce architecture, scale control, or failure discipline. Without Skill Creator, the structured system remains mostly specification rather than executable workflow.  
**Direct or Indirect:** direct  
**Chain Position:** downstream execution after `Creative Exploration Engine → Skill Handoff Bridge → Structured Skill Engineering System`  
**Reason for Relationship:** practical creation and eval tooling must follow the engineering rules, while engineering rules need an execution loop to become real.  
**Behavioural Impact:** Skill Creator must create, test, revise, and package skills while respecting structured evaluation, failure classification, and repository consistency.  
**Source Update Requirement:** apply structured engineering standards during drafting, testing, and improvement.  
**Target Update Requirement:** route practical skill creation/eval/package work into Skill Creator rather than keeping it as abstract architecture.  
**Affected Files:** `skill-creator/SKILL.md`, `structured-skill-engineering-system/SKILL.md`, `RELATIONSHIP_MAP.md`, `SKILL_MANIFEST.md`  
**Audit Status:** verified

### Relationship Contract: Skill Creator → Skill Handoff Bridge

**Source:** Skill Creator  
**Target:** Skill Handoff Bridge  
**Relationship Direction:** Skill Creator consumes bridge packets as preferred starting briefs  
**Reciprocal Direction:** Skill Handoff Bridge prepares packets in a form Skill Creator can turn into `SKILL.md`, evals, references, scripts, and package structure  
**Relationship Type:** translation  
**Relationship Strength:** strong  
**Strength Reason:** a clean handoff reduces guessing and prevents raw creative material from being mistaken for build-ready instructions.  
**Direct or Indirect:** direct  
**Chain Position:** Bridge sits immediately upstream of Skill Creator when moving from concept to build loop  
**Reason for Relationship:** Skill Creator needs intent, capabilities, constraints, risks, and output expectations before drafting or testing.  
**Behavioural Impact:** Skill Creator should extract missing information from the bridge packet and ask only for gaps; the bridge should produce standalone engineering briefs.  
**Source Update Requirement:** treat bridge packets as preferred input and preserve stated constraints.  
**Target Update Requirement:** include enough detail for skill creation, eval planning, and description drafting.  
**Affected Files:** `skill-creator/SKILL.md`, `skill-handoff-bridge/SKILL.md`, `RELATIONSHIP_MAP.md`  
**Audit Status:** verified

### Relationship Contract: Skill Creator → Relationship Contract Engine

**Source:** Skill Creator  
**Target:** Relationship Contract Engine  
**Relationship Direction:** Skill Creator calls Relationship Contract Engine when creation or improvement changes links, sub-skills, chains, inheritance, or repository maps  
**Reciprocal Direction:** Relationship Contract Engine constrains Skill Creator by requiring reciprocal structured contracts and relationship-map updates before link changes count as complete  
**Relationship Type:** audit  
**Relationship Strength:** strong  
**Strength Reason:** Skill Creator frequently creates or edits skills, so it is one of the main sources of relationship drift unless relationship governance is explicit.  
**Direct or Indirect:** conditional direct  
**Chain Position:** sidecar governance link during creation/update work  
**Reason for Relationship:** new skills and sub-skills often introduce links; those links need direction, weight, chain logic, and reciprocal updates.  
**Behavioural Impact:** Skill Creator must not use vague backlinks or unweighted “related skills” lists as substitutes for contracts.  
**Source Update Requirement:** invoke relationship governance when link-affecting changes occur.  
**Target Update Requirement:** update all affected sides and audit the repository after Skill Creator changes relationships.  
**Affected Files:** `skill-creator/SKILL.md`, `relationship-contract-engine/SKILL.md`, `RELATIONSHIP_MAP.md`, `SKILL_MANIFEST.md`  
**Audit Status:** verified

## Skill Identity

**Author:** TABARC-Code  
**Author URL:** https://github.com/TABARC-Code/  
**Dewey-style Code:** 005.100  
**Classification:** Computer programming, programs, tooling, and reusable workflow creation

Use this identity for manifests, future listing, and skill-linking. Classification helps users find the skill; relationship contracts still define how it behaves with other skills.
