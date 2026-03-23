---
name: vault-organizer
description: Interactive guide for organizing an Obsidian vault, whether from scratch or restructuring an existing one. Use when someone wants to set up, audit, or reorganize their vault, choose a knowledge management approach (PARA, Zettelkasten, ACE, flat/tags, hybrid), establish naming conventions, folder structure, tags, YAML frontmatter, backups, sync, auto-linking, and AI-agent integration. Also use when the user mentions "organize my vault", "vault structure", "naming convention", "audit my vault", "clean up my vault", or "how should I structure my notes".
---

# Vault Organizer

An interactive, step-by-step guide that helps someone organize their Obsidian vault: from scratch or by restructuring an existing one.

The skill has three phases (Phase 2 only for existing vaults):

```
New vault:      Discovery (1.1-1.4) -> Implementation -> Done
Existing vault: Discovery (1.1-1.2) -> Audit -> Discovery (1.3-1.4, informed by audit) -> Implementation (with migration) -> Done
```

For existing vaults, the audit feeds into discovery: the skill analyzes what patterns already exist in the vault and uses them as a starting point for the naming/structure conversation.

Read `references/approaches.md` when you need details about specific KM approaches.
Read `references/naming-convention.md` for the naming framework (formulas, patterns, scaling guide). All concrete codes and structures are generated from user discovery, not pre-set in the reference.

## Important principles

- **Automation-first.** Every solution must be automated or semi-automated. Never recommend something that requires manual upkeep (manual MOCs, hand-typed frontmatter, remembering naming rules). If something can't be fully automated, explain why and minimize the manual part.
- **Start minimal.** The biggest mistake is building an elaborate system before understanding your needs. Recommend the simplest version that works.
- **No one-size-fits-all.** Each person's brain works differently. The "best" system is the one they'll actually use.
- **Respect existing work.** If the user already has notes, don't propose wiping everything. Migrate gradually.
- **Decisions, not lectures.** At each step, present 2-3 concrete options with tradeoffs. Help them decide, then implement.
- **Language:** Match the user's language (Russian or English). If they write in Russian, respond in Russian.

---

## Phase 1: Discovery

Goal: understand the user well enough to recommend a KM approach.

### Step 1.1: Understand the user

Ask these questions conversationally (not as a checklist dump). Adapt based on answers. Use AskUserQuestion where possible.

1. **What do you use Obsidian for?** (work notes, personal journal, research, creative writing, task management, mix)
2. **Do you already have a vault?** (no / yes, < 50 notes / yes, 50-200 / yes, 200-500 / yes, 500+)
3. **What frustrates you most?** (can't find things, messy structure, too many folders, no system at all, info scattered across apps, nothing yet)
4. **How do you think?** (in projects/tasks, in ideas/connections, in timelines, in categories)
5. **Do you use AI agents with your vault?** (Claude Code, Cursor, Copilot, no)
6. **How technical are you?** (can write Dataview queries / comfortable with YAML / just want folders)
7. **Where do you access your vault?** (desktop only, desktop + mobile, multiple devices)

Based on the answer to question 2, decide the path:
- **No vault / < 50 notes** -> skip Phase 2 (Audit), go straight to Phase 3 (Implementation)
- **50+ notes** -> proceed to Phase 2 (Audit) after Discovery

### Step 1.2: Recommend an approach

Based on answers, read `references/approaches.md` and recommend ONE primary approach (with optional hybrid element). Use this decision tree:

```
IF mostly tasks + projects + action-oriented
  -> PARA (+ GTD elements if heavy on tasks)

IF mostly research + writing + idea generation
  -> Zettelkasten (+ PARA for project management if needed)

IF wants Obsidian-native + balance of structure and flexibility
  -> ACE/LYT

IF power user + hates folder decisions + comfortable with search
  -> Flat/Tags

IF wants extreme order + uses multiple systems
  -> Johnny Decimal

IF new to Obsidian + unsure
  -> PARA (lowest learning curve, easiest to evolve later)
```

Present the recommendation with:
- Why this approach fits them specifically
- 1-2 alternatives they could consider
- Key tradeoff they should be aware of

Wait for confirmation before proceeding.

### Step 1.3: Deep content discovery

This is the most important step. Everything downstream (naming, folders, tags, templates) is generated from these answers. Ask conversationally, not as a checklist.

**For existing vaults:** Use data from Steps 2.4-2.5 to pre-fill questions. Instead of asking from scratch, present what was detected and ask the user to confirm/adjust. See Step 2.5 for examples of how to reframe questions.

**Projects & domains:**
1. **List your 3-5 active projects** (work, personal, creative -- anything with a goal and an end date)
   - *Existing vault:* "I see folders for X, Y, Z. Are these your active projects? Any missing or outdated?"
2. **What ongoing areas of life do you manage?** (health, finance, learning, relationships, career)
3. **For each project/area: what's the one word you'd use to find files related to it in 2 years?** -- this becomes their project code

**Content types:**
4. **What kinds of notes do you actually create?** Walk through categories:
   - *Existing vault:* "Based on your filenames and tags, I see [transcripts, guides, research]. What else do you create that I might have missed?"
   - Knowledge capture: book notes, article highlights, course notes, research?
   - Plans & specs: roadmaps, project plans, requirements?
   - Instructions: how-to's, checklists, rules for yourself?
   - Meetings: transcripts, call notes, consultation summaries?
   - Content creation: blog posts, articles, presentations, social media?
   - Templates & tools: reusable prompts, templates, scripts?
5. **Which of these do you create most often?** (top 3) -- these become priority type codes
6. **Are there types unique to your work?** (e.g., "client briefs", "experiment logs", "deal memos")

**Processes & recurring notes:**
7. **Do you have recurring reviews or rituals?** (daily journal, weekly review, monthly retro, quarterly planning)
8. **Do you track people?** (clients, contacts, team members -- need a @people/ folder?)
9. **Do you have meetings that generate notes?** (1:1s, standups, consultations)

**Reference material:**
10. **What reference material do you collect?** (book notes, saved articles, course materials, recipes, quotes)
11. **Do you have content in multiple languages?** (affects search and linking strategy)

### Step 1.4: Synthesize personal naming convention

Based on answers from 1.3, read `references/naming-convention.md` for the framework, then generate and present:

**1. Their project codes:**
```
Based on your projects, here are your codes:
{code1}    Project/Area 1 name
{code2}    Project/Area 2 name
...
```

**2. Their type codes:**
```
Based on how you create notes, here are your types:
{type1}    description (from their most common content)
{type2}    description
...
```
Start with 5-7 types that cover 80% of their notes. Don't include types for content they don't create.

**3. Their naming formula with real examples:**
```
Your naming convention:
{code1} {type1} description – YYYY-MM-DD.md

Examples from YOUR projects:
{marketing} {research} competitor analysis – 2026-03-23.md
{therapy} {summary} session with Dr. Kim – 2026-03-20.md
{self} {plan} Q2 goals – 2026-03-15.md
```

**4. Their tag namespaces:**
```
Your tags:
type/[type1], type/[type2], ...
project/[code1], project/[code2], ...
topic/[discovered themes from their answers]
status/active, status/draft, status/archive
```

**Present this as a cohesive proposal.** Ask: "Does this capture how you work? Anything to add, rename, or remove?"

Wait for confirmation. Revise if needed. This becomes the foundation for all implementation steps.

---

## Phase 2: Vault Audit (existing vaults only)

Skip this phase if the user is starting from scratch. For existing vaults, run this AFTER Steps 1.1-1.2 (basic understanding + approach recommendation) but BEFORE Steps 1.3-1.4 (deep content discovery + naming synthesis). The audit data informs the discovery conversation.

### Step 2.1: Automated health check

Run diagnostics using available tools. Try in this order:

**Using Obsidian CLI (if available, v1.12.4+):**
```bash
obsidian orphans total          # count notes with zero incoming links
obsidian unresolved             # list broken/unresolved links
obsidian tags counts sort=count # tag frequency distribution
```

**Using filesystem analysis (always available):**
```bash
# File counts by type
find /path/to/vault -name "*.md" | wc -l
find /path/to/vault -type f ! -name "*.md" | wc -l

# Folder depth analysis
find /path/to/vault -type d | awk -F/ '{print NF-1}' | sort -n | tail -5

# Largest folders
find /path/to/vault -name "*.md" -exec dirname {} \; | sort | uniq -c | sort -rn | head -20

# Empty files / stubs
find /path/to/vault -name "*.md" -size -100c | wc -l

# Tag extraction
grep -roh '#[a-zA-Z0-9/_-]*' /path/to/vault --include="*.md" | sort | uniq -c | sort -rn | head -30

# Files with no YAML frontmatter
grep -rL "^---" /path/to/vault --include="*.md" | wc -l
```

### Step 2.2: Present health report

Show results as a health scorecard:

| Metric | Value | Status |
|--------|-------|--------|
| Total notes | ___ | |
| Orphan notes (no incoming links) | ___% | < 10% healthy, 10-30% warning, > 30% critical |
| Broken links | ___ | 0 healthy, 1-20 warning, > 20 critical |
| Max folder depth | ___ | 1-3 healthy, 4 warning, 5+ critical |
| Largest folder | ___ files | < 100 healthy, 100-300 warning, > 300 critical |
| Tag inconsistencies | ___ | synonyms like #book vs #books |
| Stubs (< 100 chars) | ___% | < 5% healthy, 5-15% warning, > 15% critical |
| Notes without frontmatter | ___% | |

### Step 2.3: Automated quick fixes

Run automated fixes for mechanical issues (with user confirmation):

**Auto-fixable:**
- Merge tag duplicates (script: search-and-replace `#book` -> `#books`)
- Add missing frontmatter to files (script: prepend `---\ndate: {file.mtime}\n---`)
- Identify and list orphaned attachments for bulk deletion

**Needs user input:**
- Broken links: present each with suggested fix (rename target, delete link, create stub note)
- Archive candidates: list notes untouched > 12 months for user review

Ask: "I can auto-fix [X] issues. Want me to proceed? I'll show you a diff before committing."

### Step 2.4: Analyze existing patterns

Before asking the user to define their naming/structure from scratch, extract what they're already doing. The vault has organic patterns worth preserving.

**Naming patterns:**
```bash
# Sample 30 most recent .md files to detect naming patterns
find /path/to/vault -name "*.md" -not -path "*/.obsidian/*" -not -path "*/.trash/*" | \
  xargs ls -t | head -30

# Look for date patterns in filenames
find /path/to/vault -name "*202[0-9]*" -name "*.md" | head -20

# Look for prefix/code patterns (words in curly braces, CAPS prefixes, etc.)
find /path/to/vault -name "{*}*" -o -name "[A-Z][A-Z]*-*" | head -20
```

**Folder structure:**
```bash
# Current top-level folders
ls -d /path/to/vault/*/

# Folder tree (2 levels deep)
find /path/to/vault -maxdepth 2 -type d -not -path "*/.obsidian/*" -not -path "*/.trash/*"
```

**Tag usage:**
```bash
# Extract all tags from YAML frontmatter and inline
grep -roh 'tags:' /path/to/vault --include="*.md" -A 10 | grep -o '[a-z]*/[a-z_-]*' | sort | uniq -c | sort -rn | head -30

# Inline tags
grep -roh '#[a-zA-Z0-9/_-]*' /path/to/vault --include="*.md" | sort | uniq -c | sort -rn | head -30
```

**YAML frontmatter patterns:**
```bash
# What fields are used in frontmatter?
grep -roh '^[a-z_-]*:' /path/to/vault --include="*.md" | sort | uniq -c | sort -rn | head -20
```

**Templates:**
```bash
# Check if Templates folder exists and what's in it
ls /path/to/vault/Templates/ 2>/dev/null || echo "No Templates folder"
```

### Step 2.5: Present "Current vs Proposed" overview

Combine audit data with the user's answers from Steps 1.1-1.2 to present a clear picture:

**Show what exists:**
```
Your vault today:
- [X] notes across [Y] folders
- Naming: [detected patterns, e.g. "mix of dates, descriptive names, some with prefixes"]
- Tags: [top 10 most used tags]
- Frontmatter: [X]% of files have YAML, common fields: [list]
- Templates: [exist/don't exist], [list if exist]
- Folder structure: [current tree]
```

**Show what's working (keep):**
Identify patterns that are consistent and worth preserving. E.g.:
- "You already use date-based naming for daily notes, this works well"
- "Your `Projects/` folder has clear subfolders per project, good structure"
- "Tags like `#type/research` are already namespaced, we'll keep this pattern"

**Show what's inconsistent (fix):**
- "Some files use `#research`, others `#type/research`, others `type: research` in YAML"
- "3 different date formats in filenames: YYYY-MM-DD, DD.MM.YYYY, Month DD"
- "40% of files have no frontmatter"

**Now proceed to Steps 1.3-1.4** with this context. When asking discovery questions, pre-fill with detected patterns:
- Instead of "List your projects": "I see folders for X, Y, Z. Are these your active projects? Any missing?"
- Instead of "What types of content?": "I see [transcripts, guides, research notes] based on your filenames. What else do you create?"
- Instead of "What tags do you use?": "Your most used tags are [list]. Want to keep these, or restructure?"

This makes Step 1.4 (synthesis) produce a **diff**, not just a proposal:

```
Naming convention changes:
  KEEP:    daily notes as YYYY-MM-DD.md
  KEEP:    {project} prefix pattern (already used in 60% of files)
  ADD:     {type} code after project (currently missing)
  FIX:     standardize date format (DD.MM -> YYYY-MM-DD in 23 files)
  RENAME:  {proj} -> {project} (longer but clearer, affects 15 files)

Folder structure changes:
  KEEP:    Projects/, Areas/ (already PARA-like)
  ADD:     Templates/, Archives/
  MERGE:   Docs/ + Reference/ -> Resources/
  MOVE:    scattered daily notes -> Areas/Mental Health/Daily/

Tag changes:
  KEEP:    type/research, type/guide (already namespaced)
  FIX:     #research -> type/research (45 files)
  ADD:     project/ namespace (currently not used)
  REMOVE:  #misc, #todo (too vague, 12 files)
```

This shows the user exactly what changes, what stays, and how many files are affected. Wait for confirmation before proceeding to Implementation.

---

## Phase 3: Implementation

Walk through each component in order. At each step: explain what it is, present options, help decide, then implement. Every step must produce automated infrastructure, not just rules to remember.

### Step 3.1: Folder Structure

Read `references/naming-convention.md` section "Folder Structure".

**Present 2-3 options** adapted to their chosen approach:

For PARA users:
```
vault/
├── _inbox/
├── Projects/
├── Areas/
├── Resources/
├── Archives/
└── Templates/
```

For ACE users:
```
vault/
├── +/              (inbox)
├── Atlas/           (knowledge)
├── Calendar/        (daily, weekly)
├── Efforts/         (projects)
└── x/              (attachments)
```

For Flat/Tags users:
```
vault/
├── _inbox/
├── Notes/           (everything)
├── Daily/
├── Templates/
└── Attachments/
```

Ask if they want `@people/` for contacts, `meetings/` for transcripts, etc.

**Action: Create the full folder structure.** Don't just create top-level PARA/ACE folders -- populate them with subfolders from the user's actual projects and areas discovered in Steps 1.3-1.4.

For example, if a PARA user listed projects "AI Workshop", "Lido", "English" and areas "Mental Health", "Finance", create:

```
vault/
├── _inbox/
├── Projects/
│   ├── AI Workshop/
│   ├── Lido/
│   └── English/
├── Areas/
│   ├── Mental Health/
│   │   └── Daily/          (if they have daily notes)
│   └── Finance/
├── Resources/
├── Archives/
├── Templates/
└── Attachments/
```

For each project subfolder, create a placeholder `Agents.md` with the project name and code:
```markdown
# [Project Name]

Project code: `{project_code}`

## Context
[To be filled]
```

This gives the user a vault that's ready to use immediately, not an empty shell they have to organize themselves.

### Step 3.2: Attachment Management

**Configure before anything else to prevent mess.**

| Option | How | Best for |
|--------|-----|----------|
| Central folder | Settings > Default location > `Attachments/` | Simple setups |
| Subfolder per note | "Consistent Attachments and Links" plugin | 200+ notes, lots of images |
| Same folder | Settings > Same folder as current file | Project-heavy workflows |

**Action:** Change the Obsidian setting. If existing vault, offer to run a script to consolidate scattered attachments.

### Step 3.3: Naming Convention + Templater Automation

Use the naming convention confirmed in Step 1.4 (project codes, type codes, tag namespaces). These were already approved by the user.

**Automation:** Create a Templater template populated with the user's actual codes:

```markdown
<%*
// Populated from Discovery Step 1.4
const projects = [/* user's project codes from 1.4 */];
const types = [/* user's type codes from 1.4 */];
const project = await tp.system.suggester(projects, projects, false, "Project code:");
const type = await tp.system.suggester(types, types, false, "Content type:");
const desc = await tp.system.prompt("Brief description:");
const date = tp.date.now("YYYY-MM-DD");
const filename = `{${project}} {${type}} ${desc} – ${date}`;
await tp.file.rename(filename);
-%>
```

The user never needs to remember the formula: they pick from dropdowns and the file is named correctly.

**Action:** Create the Templater template (with their actual codes) + a `_naming-convention.md` reference note in the vault documenting their personal codes and examples.

### Step 3.4: YAML Frontmatter & Aliases (auto-filled)

Present three levels:

**Level 0 (none):** Just filenames. Only for < 50 notes.

**Level 1 (auto-filled by Templater):**
```yaml
---
tags:
  - <% await tp.system.suggester([/* user's type/ tags from Step 1.4 */], ...) %>
  - <% await tp.system.suggester([/* user's project/ tags from Step 1.4 */], ...) %>
date: <% tp.date.now("YYYY-MM-DD") %>
---
```

**Level 2 (full, auto-filled with aliases):**
```yaml
---
aliases:
  - <% await tp.system.prompt("Aliases (comma-separated):") %>
tags:
  - <% /* type/ suggester with user's codes */ %>
  - <% /* project/ suggester with user's codes */ %>
  - <% /* topic/ suggester with user's themes */ %>
date: <% tp.date.now("YYYY-MM-DD") %>
---
```

The user selects tags from dropdowns, never types them manually. Date is auto-filled. Aliases are prompted once on creation.

**Recommend Level 1 always** (even for beginners, since Templater handles the complexity). Level 2 for 200+ notes.

**Action:** Build the Templater template with their specific project/type tag lists as suggester options.

### Step 3.5: Tags Strategy (auto-assigned)

Present tag namespaces using the user's actual codes from Step 1.4:
```
type/       what it is (populated from user's type codes)
project/    which project (populated from user's project codes)
topic/      subject matter (populated from user's recurring themes)
status/     lifecycle: active, draft, archive
```

**Automation layers:**
1. **Templater suggesters** (from Step 3.4) handle `type/` and `project/` tags at creation
2. **Linter plugin** can auto-add tags based on folder (file in `Projects/AI/` -> auto-tag `project/ai`)
3. **For existing vaults:** Write a batch script to add missing tags based on folder location

Rules:
- 3-5 tags per file
- Tags complement filenames, don't duplicate them
- Start with `type/` and `project/` only. Add `topic/` and `status/` when needed.

**Action:** Configure tag suggesters in Templater. If existing vault, run batch-tagging script.

### Step 3.6: Templates (ready-to-use)

Create working Templater templates (not descriptions -- actual files the user can invoke immediately):

1. **New note template** -- auto-renames file per convention, auto-fills YAML with suggesters, prompts for aliases
2. **Daily note template** -- minimal (3-5 sections), auto-date, includes `[[links]]` to relevant areas. Anti-pattern warning: daily notes without review = write-only graveyard.
3. **Meeting note template** (if relevant) -- auto-fills date, attendees prompt, backlink to project
4. **Project overview template** -- Dataview query auto-listing all notes in the project folder

Every template must auto-fill everything it can. The user should only type what can't be derived.

**Action:** Create template files in Templates folder. Test each one.

### Step 3.7: Auto-Linking & Discovery

This step builds the connection infrastructure that prevents notes from becoming isolated.

**Layer 1: Virtual Linker plugin (passive, zero risk)**
- Shows potential `[[wikilinks]]` in real-time without modifying files
- Install, configure to match note titles + aliases
- User sees connections instantly, decides which to make permanent

**Layer 2: Dataview dynamic MOCs (replaces manual MOCs)**
- Create MOC notes with Dataview queries instead of hand-maintained lists:

```dataview
TABLE file.mtime AS "Updated"
FROM "Projects/AI"
SORT file.mtime DESC
```

```dataview
LIST FROM #topic/coaching
SORT file.cday DESC
```

- Backlink-based MOC: put `LIST FROM [[]]` in a MOC note. Any note that links to it auto-appears in the list.
- MOCs never need manual updating. Notes appear/disappear as they match.

**Layer 3: Smart Connections plugin (semantic discovery)**
- AI finds semantically related notes in a sidebar
- Works with local models (free, private) or cloud APIs
- Especially valuable for multilingual vaults (finds connections across languages)

**Layer 4: Periodic batch-linking (for AI agent users)**
- Claude Code / Cursor can run a monthly batch pass:
  - Scan all notes for unlinked mentions of existing note titles
  - Wrap matches in `[[]]`
  - Present diff for review before committing
- This is the most powerful option for bilingual vaults (handles Russian morphology)

**Recommend:** Layer 1 + Layer 2 for everyone. Layer 3 for 200+ notes. Layer 4 for AI agent users.

**Action:** Install Virtual Linker, create 3-5 Dataview MOC notes for key topics/folders. Install Smart Connections if appropriate.

### Step 3.8: Plugins

Based on their setup, recommend plugins in priority order:

| Priority | Plugin | What it automates |
|----------|--------|-------------------|
| Must | Templater | File naming, YAML, tags via dropdowns |
| Must | Dataview | Dynamic MOCs, dashboards, queries |
| Must | Virtual Linker | Auto-discovered connections |
| Should | Calendar | Daily note navigation |
| Should | Obsidian Git | Auto-backup every 30 min |
| Should | Smart Connections | AI semantic note discovery |
| Should | Linter | Auto-format, auto-tag by folder |
| Nice | Quick Switcher++ | Fast file search |
| Nice | Periodic Notes | Weekly/monthly note creation |
| Nice | Tasks | Task aggregation across notes |

**Plugin overload warning:** 40+ active plugins slow Obsidian, especially on mobile. Install only what you'll use. Audit quarterly.

### Step 3.9: Backup & Sync

**Backup (non-negotiable, automated on day one):**

Sync is NOT backup. iCloud/Dropbox propagate deletions to all devices.

**Setup:** Obsidian Git plugin with auto-commit every 30 minutes to a private GitHub repo. Fully automatic after 5-minute setup.

**Sync (if multi-device):**

| Option | Reliability | Cost | Notes |
|--------|-------------|------|-------|
| Obsidian Sync | Best | $4/mo | Encrypted, selective sync |
| iCloud | OK (Apple only) | Free | Issues on Windows. Fine < 500 notes |
| Syncthing | Good | Free | No iOS. Technical setup |

**Action:** Set up Obsidian Git. Configure sync if multi-device.

### Step 3.10: AI Agent Integration

If they use Claude Code, Cursor, or similar:

1. **Generate CLAUDE.md** from all previous decisions:
   - Naming formula + project/type codes
   - Folder rules (where new files go)
   - Attachment folder setting
   - Tag namespaces
   - Auto-linking rules

2. **Create Agents.md** in key folders with local context

3. **Set up batch-linking script** (if Claude Code user) for periodic auto-linking runs

**Action:** Generate a complete CLAUDE.md. The AI agent now enforces all conventions automatically.

### Step 3.11: Migration (existing vaults only)

Skip if starting from scratch. For existing vaults, rename ALL files to follow the naming convention, not just new ones.

#### 3.11.1: Assess the scope

Count files by naming status:
- **Already convention-compliant** (`{project} {type} ...`): count
- **Structural names to keep** (daily notes `YYYY-MM-DD.md`, weekly `WEEK_XX_YYYY.md`, system files `Agents.md`/`CLAUDE.md`/`MOC*.md`, templates): count
- **Reference files** (long-lived notes like `Wishlist.md`, `Book list.md`): count -- these stay as `Descriptive Name.md`
- **Need renaming**: everything else

Present the breakdown so the user understands the full scope.

#### 3.11.2: Folder-by-folder migration

**Never rename everything at once.** Migrate one folder at a time, starting with the most important/active project.

For each folder:
1. **List all files** in the folder with current names
2. **For each file**, read its content (first 20 lines) to understand what it is
3. **Propose new name** using the convention: `{project} {type} description – YYYY-MM-DD – Interface.md`
   - Derive the date from: YAML frontmatter `date:` field > filename date > file modification date
   - Derive the interface from: filename clues (`– Cursor`, `– Claude Code`) > content clues > `Manual` as default
   - Derive type from content: transcript of a meeting = `{transcript}`, how-to = `{guide}`, etc.
   - If a file is a reference note (no date, long-lived), keep it as `Descriptive Name.md`
4. **Present the rename table** to the user:
   ```
   Current name                              -> Proposed name
   Interview - Dasha (Ops).md                -> {lido} {transcript} Interview Dasha Ops – 2025-12-04 – Granola.md
   OKR Cycle Proposal 2026.md                -> {lido} {plan} OKR Cycle Proposal – 2026-01-15 – Manual.md
   Wishlist.md                               -> [KEEP as is - reference file]
   ```
5. **Wait for user confirmation.** User may correct project codes, types, or descriptions.
6. **Execute renames** using `obsidian move` CLI (preserves wikilinks) or Obsidian API. Never use raw filesystem mv.
7. **Update YAML frontmatter** if missing: add tags based on the new project/type codes.
8. **Git commit** after each folder is done.

**File types that should NOT be renamed:**
- Daily notes (`YYYY-MM-DD.md`)
- Weekly notes (`WEEK_XX_YYYY.md`)
- System files (`Agents.md`, `CLAUDE.md`, `MOC - *.md`, `README.md`)
- Templates
- Reference notes the user wants to keep with descriptive names

**Prioritization:** Start with the user's most active project folder, then work outward. This gives immediate value and lets the user validate the approach before scaling.

#### 3.11.3: Fix old convention codes

Files that already use `{codes}` but with outdated codes get a simpler migration: search-and-replace the old code with the new one in the filename.

#### 3.11.4: Structural fixes

After renaming:
1. Fix broken links -- script identifies and suggests fixes
2. Merge tag duplicates -- search-and-replace script
3. Add missing frontmatter -- script prepends YAML with date from file metadata
4. Move files to correct folders -- `obsidian move` CLI for automatic link rewriting
5. Archive stale notes -- script identifies untouched > 12 months, moves to Archives/

**Critical rule:** Always use `obsidian move` CLI or Obsidian app for moves, never filesystem operations. Obsidian auto-rewrites wikilinks.

**Action:** Work through folders one by one. After each folder, commit and verify links are intact.

---

## Completion

After all steps, summarize what was created and what's automated:

```
Your vault setup:
- Approach: [chosen approach]
- Folders: [list]
- Attachments: [strategy, auto-configured]

Automated via Templater:
- File naming (dropdown project/type selection)
- YAML frontmatter (auto-date, tag suggesters, alias prompt)

Automated via plugins:
- Connections: Virtual Linker (passive), Smart Connections (semantic)
- MOCs: Dataview queries (auto-updating)
- Backup: Obsidian Git (every 30 min)
- Sync: [method]

Automated via AI agent:
- CLAUDE.md enforces conventions for AI-created files
- Batch-linking: [monthly/as-needed]

Manual (minimized):
- Choosing aliases when creating notes
- Reviewing batch-link suggestions
- [anything else that can't be automated]
```

**Follow-up:** Run the vault health check again after 2 weeks (same commands from Phase 2) to measure improvement. Compare orphan count, broken links, etc.

---

## Quick Reference: When to read reference files

| Situation | Read |
|-----------|------|
| User asks about specific KM approaches | `references/approaches.md` |
| Need the naming formula or scaling guide | `references/naming-convention.md` |
| User mentions specific approach pros/cons | `references/approaches.md` |
| Building CLAUDE.md or templates | Use results from Step 1.4 (user's personal codes) |
