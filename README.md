# Vault Organizer

A Claude Code skill for organizing Obsidian vaults interactively.

## What it does

Guides you through setting up or restructuring an Obsidian vault step by step:

1. **Discovery** -- understands how you work, what projects you have, what content you create
2. **Audit** (existing vaults) -- scans your vault, detects patterns, shows health scorecard
3. **Implementation** -- builds personalized naming conventions, folder structure, tags, Templater templates, and CLAUDE.md

Everything is generated from your answers, not pre-set. The skill acts as a consultant, not a template.

## Flow

```
New vault:      Discovery -> Implementation -> Done
Existing vault: Discovery -> Audit -> Discovery (informed by audit) -> Implementation + Migration -> Done
```

## Key features

- **Discovery-driven naming convention**: asks about your projects, content types, processes, then proposes codes
- **Vault health check**: orphans, broken links, folder depth, tag inconsistencies, stubs, missing frontmatter
- **Current vs Proposed diff**: shows what to KEEP, ADD, FIX, RENAME, MERGE, MOVE with file counts
- **Folder-by-folder migration**: renames all files to convention, one folder at a time
- **Automation-first**: Templater suggesters, Dataview MOCs, auto-linking -- never recommends manual upkeep
- **AI agent integration**: generates CLAUDE.md from all decisions

## Installation

Copy the skill folder to your Claude Code skills directory:

```bash
# Clone to Claude Code skills
git clone https://github.com/zena-the-programmer/vault-organizer.git ~/.claude/skills/vault-organizer
```

Then invoke with `/vault-organizer` in Claude Code, or it triggers automatically when you mention organizing your vault.

## Files

- `skill.md` -- the main skill definition
- `references/approaches.md` -- KM approaches comparison (PARA, Zettelkasten, ACE, Johnny Decimal, GTD, Flat/Tags)
- `references/naming-convention.md` -- naming framework (formulas and patterns, not pre-set codes)

## Supported approaches

| Approach | Best for |
|----------|----------|
| PARA | Action-oriented users, freelancers, managers |
| Zettelkasten | Researchers, writers, academics |
| ACE/LYT | Balance of structure and flexibility |
| Johnny Decimal | Extreme order across multiple systems |
| GTD | Task-heavy workflows |
| Flat/Tags | Power users comfortable with search |

## License

MIT
