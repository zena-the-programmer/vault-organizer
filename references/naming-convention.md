# Naming Convention Framework

This is a framework for building personalized naming conventions. All codes and structures are generated from user discovery, not pre-set.

## Naming Formula

```
{project} {type} description – YYYY-MM-DD.md
```

- Date ALWAYS at the end
- EN DASH (–) as separator
- Max 80 characters
- Max 2 codes per filename

## How to Generate Project Codes

Based on user's active projects (from Discovery Step 1.3), create codes:
- 2-8 characters, lowercase, no spaces
- Must be unique and stable (won't change when project scope shifts)
- Use the shortest unambiguous abbreviation
- If the user works in one domain, project = specific initiative; if many domains, project = domain

**Guideline:** Ask "If you had to tag a file so you'd find it in 2 years, what one word would you use?" That word is the project code.

## How to Generate Type Codes

Based on user's content patterns (from Discovery Step 1.3), identify what kinds of notes they create. Common categories to explore:

| Category | Discovery question | Typical codes |
|----------|-------------------|---------------|
| Knowledge capture | "Do you take notes from books, articles, courses?" | research, summary, notes |
| Action/planning | "Do you write plans, roadmaps, specs?" | plan, prd, roadmap |
| Instructions | "Do you document how-to's for yourself or others?" | guide, rule, checklist |
| Meetings | "Do you record meetings, calls, consultations?" | transcript, meeting, summary |
| Content creation | "Do you write articles, posts, presentations?" | article, post, demo, case |
| Templates/tools | "Do you create reusable templates or prompts?" | template, prompt, tool |
| Processes | "Do you have recurring reviews, syncs, retros?" | retro, review, sync |

**Guideline:** Start with 5-7 types that cover 80% of user's notes. They can always add more later. Don't include types for content they don't create.

## File Types by Category

| Type | Format | When to use |
|------|--------|-------------|
| AI-Generated / structured | `{project} {type} description – YYYY-MM-DD.md` | Notes created with Templater or AI agents |
| Temporal | `YYYY-MM-DD.md`, `WEEK_XX_YYYY.md` | Daily/weekly notes (auto-generated) |
| Reference | `Descriptive Name.md` | Long-lived reference notes (Wishlist, Book list) |
| Project docs | `Project Name - Doc Type.md` | One-off project documents |
| System | `UPPERCASE.md` or `PascalCase.md` | CLAUDE.md, Agents.md, MOC files |

## YAML Frontmatter Levels

### Level 0: None
Just filenames. Only for < 50 notes or users who hate metadata.

### Level 1: Auto-filled by Templater (recommended default)
```yaml
---
tags:
  - type/[from suggester -- populated with user's type codes]
  - project/[from suggester -- populated with user's project codes]
date: [auto-filled]
---
```

### Level 2: Full (200+ notes)
```yaml
---
aliases: [prompted once on creation]
tags:
  - type/[suggester]
  - project/[suggester]
  - topic/[suggester -- populated with user's topic tags]
  - status/[suggester]
date: [auto-filled]
---
```

## Tag Namespaces

```
type/       what it is (derived from user's type codes)
project/    which project (derived from user's project codes)
topic/      subject matter (derived from user's recurring themes)
status/     lifecycle: active, draft, archive
```

3-5 tags per file. Tags complement filenames, don't duplicate them.
Start with `type/` + `project/` only. Add `topic/` and `status/` when the user has enough notes to benefit.

## Folder Structure Principles

- 6-10 top-level folders max
- Flat > nested (max 3 levels deep)
- Folder names match the chosen KM approach (PARA, ACE, etc.)
- Every folder should have a clear "when does a file go here?" rule
- If the user can't decide between two folders, the structure needs simplifying

Folder structures are generated in Implementation Step 3.1 based on the chosen approach + user's projects/areas.

## Scaling Guide

| Vault size | What to add |
|------------|-------------|
| 0-50 | Basic folder structure, 3-5 project codes, 5-7 type codes |
| 50-200 | Templater automation, tags, daily notes |
| 200-500 | Dataview MOCs, weekly reviews, Agents.md per folder |
| 500+ | AI agent integration, batch-linking, Smart Connections |
