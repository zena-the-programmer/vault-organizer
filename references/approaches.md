# Knowledge Management Approaches Reference

## Quick Comparison

| Dimension | PARA | Zettelkasten | Johnny Decimal | ACE/LYT | GTD | Flat/Tags |
|---|---|---|---|---|---|---|
| Learning curve | Low | High | Medium | Medium | Medium | Medium-High |
| Folder reliance | High | None/Low | Very High | Medium | Medium | None |
| Link reliance | Low | Very High | None | High | Low | High |
| Best for tasks | Good | Poor | Poor | Good | Excellent | Medium |
| Best for ideas | Poor | Excellent | Poor | Good | Poor | Medium |
| Maintenance | Medium | High | Low | Medium | High (weekly) | Low |
| Scales to 1000+ | Medium | Excellent | Good | Good | Medium | Depends |
| Obsidian-native | Low | High | Low | High | Medium | High |

## 1. PARA (Tiago Forte)

**Core:** Organize by actionability. Projects (active + deadline), Areas (ongoing), Resources (reference), Archives (inactive).

**Best for:** Action-oriented users, freelancers, managers. People who think in tasks and outcomes.

**Pros:** Intuitive, universal (works outside Obsidian too), clear decision tree, max 4 levels deep.
**Cons:** Files only live in one folder, underutilizes Obsidian linking/graph, Areas vs Resources boundary is fuzzy.

**New notes:** Projects or Areas (by actionability). Add Inbox folder.
**Finding notes:** Browse 4 folders, search.
**Projects:** First-class, top-level folder.
**Reference:** Resources folder with topic subfolders.

## 2. Zettelkasten (Niklas Luhmann)

**Core:** Atomic notes (one idea = one note) connected by links. Structure emerges from connections, not folders.

**Best for:** Researchers, writers, academics, deep thinkers who generate ideas from reading.

**Pros:** Maximizes Obsidian (linking, graph, backlinks), forces deep processing, scales infinitely.
**Cons:** Steep learning curve, requires disciplined atomic notes, no natural project management.

**New notes:** Fleeting -> literature -> permanent (with links).
**Finding notes:** Link chains, MOCs, graph, search.
**Projects:** Not native. Use MOC per project or tags.
**Reference:** Literature notes linked to permanent notes.

## 3. Johnny Decimal

**Core:** 10 areas (10-99), each with max 10 categories. Every item has unique ID like 23.04.

**Best for:** People who want extreme predictability. System admins, accountants. Works across all systems.

**Pros:** Unique addresses, muscle memory, speakable numbers.
**Cons:** Hard limit 100 slots, requires upfront planning, no archiving mechanism.

## 4. ACE / LYT (Nick Milo)

**Core:** Three headspaces: Atlas (knowledge), Calendar (time), Efforts (action). MOCs instead of deep hierarchies.

**Structure:** `+` (Inbox), `Atlas/`, `Calendar/`, `Efforts/`, `x` (extra)

**Best for:** Best-of-both-worlds users. Thinkers who also manage projects. Users who outgrew PARA.

**Pros:** Balances structure + flexibility, designed for Obsidian, MOCs as dynamic TOC.
**Cons:** Somewhat proprietary ecosystem, MOC maintenance overhead.

## 5. GTD (Getting Things Done)

**Core:** Capture -> Clarify -> Organize -> Reflect -> Engage. Focus on next actions and contexts.

**Best for:** Task-heavy users managing hundreds of action items. Needs Obsidian Tasks plugin.

**Pros:** Battle-tested, reduces mental load, weekly review keeps system current.
**Cons:** Task system, not knowledge system. Weak for ideas. Requires strict weekly reviews.

## 6. Flat / Tag-Based (Steph Ango style)

**Core:** Minimal folders. Organization through tags, YAML properties, and links. Structure from metadata.

**Best for:** Power users comfortable with search and Dataview. Prolific note-takers.

**Pros:** Zero friction, notes belong to multiple categories via tags, no maintenance.
**Cons:** File browser useless at scale, requires tag discipline, hard for beginners.

## Common Hybrids

- **PARA + Zettelkasten:** PARA for action, Zettelkasten for insight in Resources
- **PARA + GTD:** PARA for files, GTD for task workflow within Projects
- **ACE + Zettelkasten:** Atlas uses Zettelkasten, Efforts uses project management
- **Johnny Decimal + PARA:** JD numbering applied to PARA categories
