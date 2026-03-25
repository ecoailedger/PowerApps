
## Purpose of this repository

This repository is a working lab for **Canvas Power Apps engineering**.

It exists to do three things well:

1. **Trial and build reusable Power Apps code components**
   - Primarily PCF controls intended for Canvas apps
   - Supporting helper code, example implementations, and packaging notes

2. **Store high-quality Power Apps reference patterns**
   - Proven Canvas YAML examples
   - Reusable Power Fx snippets
   - Layout patterns, state patterns, form patterns, gallery patterns, component patterns

3. **Act as a trusted implementation repo**
   - Practical, copy-pasteable examples
   - Clean structure
   - No fake assumptions
   - No “demo fluff” that would break in a real app

This repo is not just for experiments. It should gradually become a **high-trust internal reference library** for building better Canvas apps.

---

## What good looks like in this repo

Everything added here should be:

- **practical**
- **readable**
- **reusable**
- **well-structured**
- **easy to lift into a real Canvas app**
- **clear about assumptions and limitations**

Prefer examples that are:

- close to real Power Apps usage
- easy to test
- small enough to understand quickly
- documented well enough that another person can use them without guessing

---

## Core principles

### 1) Do not invent things
Do not make up:

- Dataverse table names
- SharePoint column names
- Power Fx variable names that imply a real schema unless clearly marked as example-only
- YAML properties that do not exist
- PCF APIs that are not real

If a schema is unknown:

- state that it is assumed
- use obviously generic placeholder names
- label them clearly as placeholders

### 2) Prefer minimal, safe changes
When updating existing code or examples:

- preserve structure where possible
- avoid unnecessary rewrites
- improve only what is needed
- do not “modernise” for the sake of it

### 3) Optimise for real Canvas app usage
Examples should reflect how Canvas apps are actually built:

- component-driven layouts
- galleries, forms, containers, tabs, modals
- readable Power Fx
- maintainable state handling
- sensible naming

### 4) Examples must teach
Every strong example should help the reader understand:

- what the pattern is for
- why it is built this way
- what can be changed safely
- what the risks are

### 5) Keep YAML trustworthy
Power Apps YAML in this repo must be:

- syntactically clean
- structurally realistic
- aligned to real control/property patterns
- easy to adapt

If a YAML sample is illustrative rather than production-ready, say so explicitly.

---

## Repository scope

This repo may contain:

- PCF controls for Canvas apps
- sample Canvas YAML files
- Power Fx pattern libraries
- reusable UI patterns
- helper scripts for component development
- documentation for packaging, testing, and importing
- example data contracts for demo use
- notes on known limitations in Canvas apps and PCF

This repo should not become:

- a dumping ground for random snippets
- a generic Microsoft docs mirror
- a place for half-finished examples with no explanation
- a storage area for unverified code copied from the internet

---

## Standard folder structure

Use this structure unless there is a strong reason not to.

```text
/
├─ CODEX.md
├─ README.md
├─ docs/
│  ├─ architecture/
│  ├─ canvas-patterns/
│  ├─ pcf-guides/
│  ├─ yaml-patterns/
│  └─ decisions/
├─ components/
│  ├─ pcf/
│  │  ├─ <component-name>/
│  │  └─ <component-name>/
│  └─ shared/
├─ examples/
│  ├─ yaml/
│  │  ├─ galleries/
│  │  ├─ forms/
│  │  ├─ navigation/
│  │  ├─ modals/
│  │  ├─ tabs/
│  │  └─ responsive/
│  ├─ powerfx/
│  └─ sample-app-patterns/
├─ scripts/
├─ assets/
│  ├─ screenshots/
│  └─ diagrams/
└─ notes/
Folder intent
/components/pcf

Each PCF control should live in its own folder with:

source code
manifest
build notes
usage notes
screenshots or GIFs if useful
a short README
/examples/yaml

This should hold small, focused YAML examples that prove one pattern each.

Good examples:

responsive screen shell
tabbed layout
modal popup
editable gallery row
header with contextual actions
loading and empty states
status badges
master-detail layout
/examples/powerfx

Store reusable Power Fx snippets by scenario, not by randomness.

Examples:

filtering
patching
navigation
local state
formatting
collections
validation
date handling
currency handling
/docs

This should explain the repo and the reasoning behind patterns.

Naming rules
Files and folders

Use clear, predictable names.

Examples:

responsive-screen-shell.yaml
tabbed-record-detail.yaml
gallery-status-badges.fx.md
pcf-control-checklist.md

Avoid vague names like:

test.yaml
new1.md
stuff.md
powerappsbits.md
Components

PCF component folders should use consistent kebab-case:

icon-badge
status-pill
record-summary-card
Examples

Name examples for the pattern they demonstrate, not the screen they came from.

Good:

modal-confirm-delete.yaml

Bad:

screen3-final-v2.yaml
Documentation standard for every meaningful addition

Any meaningful component or example should include:

Summary

What it is and what problem it solves.

Use case

Where it is useful in a Canvas app.

Inputs

What data, properties, or assumptions it expects.

Outputs or behaviour

What it does when used.

Constraints

Known limitations, unsupported scenarios, performance concerns.

Adaptation notes

What can be safely renamed or changed.

Rules for PCF controls

This repo is a trial space for making code components for Canvas Power Apps, so PCF quality matters.

PCF controls in this repo should aim to be:
small
single-purpose
easy to demo
easy to test
easy to document
Prefer components that solve real Canvas pain points

Examples:

better status displays
richer badges and chips
visual summaries
compact record cards
icon-enhanced text blocks
timeline or activity displays
improved filtering UI
lightweight KPI tiles
attachment or file indicators
richer lookup presentation
Avoid starting with giant “do everything” controls

Do not build overly broad components first.

Prefer:

one clear control with one job

Avoid:

one control that tries to replace half the screen
Each PCF component should include:
purpose
manifest clarity
property definitions
local build instructions
Canvas usage notes
screenshot
known issues
Rules for Power Apps YAML examples

YAML examples are a key asset in this repo. Treat them as reference implementations.

YAML examples should be:
focused
realistic
clearly scoped
easy to paste into a test app
documented with assumptions
Each YAML example should say:
what it demonstrates
what controls are involved
whether it depends on variables, collections, or data sources
whether names are placeholders
Prefer examples that demonstrate:
layout
pattern
interaction
maintainability

over examples that are just visually busy.

YAML quality rules
Keep indentation clean
Keep properties grouped logically
Use realistic Power Apps property names
Avoid bloated examples with too much unrelated content
Do not mix multiple major concepts into one example unless the example is intentionally composite
Rules for Power Fx examples

Power Fx examples should be written for readability first.

Style
Keep formulas structured and readable
Use line breaks when logic is non-trivial
Avoid clever one-liners that are hard to maintain
Prefer explicitness over compressed syntax
Requirements

Each Power Fx example should include:

pattern name
formula
explanation
assumptions
common edits
Example categories to build over time
filtering and search
sorting
record selection
form state
Patch patterns
collection shaping
lookups
validation
navigation
formatting
modal state
loading state
empty state
role-based visibility
Regional and formatting defaults

Unless a specific example needs otherwise, prefer UK formatting in examples.

Use:

dates in a UK-friendly pattern
currency examples using £
en-GB formatting where relevant

Examples:

dd mmm yyyy
[$-en-GB]dd mmm yyyy
£#,##0.00
[$-en-GB]#,##0.00

Do not hardcode regional formatting without explaining it when it matters.

Preferred example patterns for this repo

These are high-value patterns worth building out first.

Canvas YAML patterns
responsive app shell
page header with actions
tabbed detail page
modal dialog
side panel
reusable card layout
editable gallery
sectioned form layout
KPI strip
badge and status patterns
search and filter toolbar
empty state and skeleton/loading state
back navigation pattern
confirmation popup pattern
Power Fx patterns
search + sort + filter combo
local UI state with UpdateContext
app-level state with Set
collection shaping with AddColumns
safe Patch examples
form validation before submit
status colour logic
currency/date formatting
role-based control visibility
selected record detail pattern
PCF ideas
status pill / badge control
icon text summary control
record summary tile
compact KPI card
richer tag/chip selector
timeline display
warning/health indicator
approval status visual
file / attachment indicator
branded section header control
Contribution standard

When adding something to this repo, follow this workflow:

1. Define the intent

State clearly:

what is being added
why it belongs here
whether it is experimental or reference-grade
2. Keep scope tight

One component, one pattern, or one learning objective per addition.

3. Add documentation

Do not add a meaningful example or component without explaining it.

4. Show usage

Where possible, include:

screenshot
sample formula
sample input
sample YAML usage
5. Record limitations

Be honest about what is unfinished or assumed.

Pull request expectations

A good PR in this repo should answer:

What was added or changed?
Why does it matter?
Is it production-ready, experimental, or illustrative?
What assumptions were made?
How should it be tested?
What should reviewers pay attention to?
Definition of done

Something is only “done” in this repo when it is:

named properly
placed in the right folder
readable
documented
realistic
useful to reuse later

Not done:

code exists

Done:

code exists and can be trusted
Anti-patterns for this repo

Avoid these:

1. Fake realism

Examples that look polished but rely on invented schemas or impossible properties.

2. Giant snippets with no explanation

Large code drops that no one can safely reuse.

3. Random experiments in the root

Everything should have a home.

4. Hidden assumptions

If something depends on a variable, collection, or data source, say so.

5. Unstructured PCF trials

Every component experiment still needs a minimum level of order.

6. Rewriting working examples for style points

Only change what improves correctness, clarity, or reuse.

Suggested file templates
Template: YAML example doc
# <Example Name>

## Purpose
Brief description of the pattern.

## What it demonstrates
- item 1
- item 2

## Assumptions
- any variables used
- any collections used
- any placeholder names used

## Notes
Anything important for adapting it safely.
Template: PCF component doc
# <Component Name>

## Purpose
What the control does.

## Why this exists
What Canvas limitation or pain point it helps with.

## Inputs
List of properties.

## Behaviour
What users should expect.

## Canvas usage notes
How to bind and use it.

## Limitations
Known constraints.

## Build notes
Commands, packaging, or setup details.
Template: Power Fx snippet doc
# <Pattern Name>

## Scenario
What this formula is for.

## Formula
```powerfx
// formula here
Assumptions

What fields, variables, or controls are expected.

Notes

How to adapt safely.


---

## Expected README direction

The root `README.md` should stay short and practical.

It should explain:

- what this repo is
- what lives where
- how to find examples
- how PCF trials are organised
- what quality bar applies

Detailed guidance belongs in `/docs` and this `CODEX.md`.

---

## Working preferences for this repo

When generating or updating content for this repo, prefer:

- direct answers
- minimal but correct changes
- examples that can actually be used
- real Power Apps structure over generic UI theory
- clarity over cleverness

When uncertain:

- state the assumption
- do not pretend certainty
- do not fabricate schemas or platform behaviour

---

## Repo north star

This repo should become a **trusted build space and reference library** for:

- Canvas Power Apps code components
- clean YAML patterns
- reusable Power Fx
- practical implementation examples

Every addition should move it toward that goal.
