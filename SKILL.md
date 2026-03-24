---
name: brand-builder
user-invokable: true
description: >
  Complete product branding toolkit with 5 sequential modules: Naming, Positioning, Voice & Messaging, Visual Identity, and SEO Content. Use this skill for ANY branding-related request. Triggers include 'brand', 'branding', 'naming', 'name my company', 'brand name', 'product name', 'rename', 'rebrand', 'brand strategy', 'positioning', 'brand positioning', 'value proposition', 'brand voice', 'tagline', 'slogan', 'messaging', 'brand tone', 'visual identity', 'logo', 'color palette', 'brand design', 'typography', 'SEO', 'SEO content', 'content strategy', 'keyword research', 'blog post', '品牌', '命名', '取名', '品牌定位', '品牌策略', '標語', '品牌設計', 'SEO文章', or ANY request related to building, defining, or improving a brand. This is a comprehensive branding system — always start here for branding work.
---

# Brand Builder

A complete, 5-step branding system that takes a company from zero to a fully defined brand with content strategy. Each step builds on the previous one.

### Tool Usage Rule

**ALWAYS use the `AskUserQuestion` tool for all questions throughout this skill.** Every question should be presented as interactive clickable choices, not plain text.

Rules for `AskUserQuestion`:
- 1-4 questions per call
- 2-4 options per question (users can always select "Other" for custom input)
- Each option needs a short `label` (1-5 words) and a `description`
- Each question needs a `header` tag (max 12 chars)
- Use `multiSelect: true` when multiple answers apply
- Use `multiSelect: false` for single-choice questions
- No `rank_priorities` — use multi-select + ask to prioritize in follow-up if needed

---

## Project Initialization

**Run this FIRST before any module — every time a new branding project starts.**

1. Ask for the project name using `AskUserQuestion`:

   Call `AskUserQuestion` with:
   - question: "What should we call this project folder? Use lowercase letters and hyphens."
   - header: "Project name"
   - multiSelect: false
   - options:
     - { label: "my-brand", description: "Simple format — replace with your actual project name via 'Other'" }
     - { label: "acme-2025", description: "Company + year format — use 'Other' to type your own name" }
     - { label: "I'll type it", description: "Select 'Other' to enter a custom folder name" }

   The user will typically select "Other" and type their own project name — that is the expected flow.

2. Once confirmed, create the project folder in the repo root:
   - Path: `{repo-root}/{project-name}/`
   - Use the Write tool or Bash `mkdir` to create the folder
   - Confirm to the user: "Project folder `{project-name}/` created. All outputs will be saved here as we go."

3. Store the project folder path in the context block (see below) for all subsequent modules.

> **Skip this step only if** the user is continuing an existing project (e.g., says "continue branding" or provides a project name already). In that case, confirm the folder exists and use its path.

---

## The 5-Step Workflow

```
① Naming  →  ② Positioning  →  ③ Voice  →  ④ Visual  →  ⑤ SEO Content
```

| Step | Module | What It Does | Output |
|------|--------|-------------|--------|
| ① | **Naming** | Name generation via Identify → Invent → Implement | 10 registrable name candidates (balanced: ~5 real words + ~5 engineered) + domain strategy |
| ② | **Positioning** | Define market position + differentiation | Positioning statement, value prop, competitive map |
| ③ | **Voice** | Define how the brand speaks | Tagline, messaging hierarchy, voice guidelines |
| ④ | **Visual** | Define how the brand looks | Color palette, typography, logo brief |
| ⑤ | **SEO Content** | Build content that ranks | Topic clusters, keyword plan, content calendar |

---

## How To Use This Skill

### Starting a new brand from scratch
→ Start at **Step ①** and go in order. Each step feeds into the next.

### Already have a name / some branding done
→ Use the router below to jump to the right step.

### Just need one specific thing (e.g., "write me a tagline")
→ Jump directly to the relevant module. The skill will ask for any missing context.

---

## Router: Determine Which Step to Run

When the user makes a request, determine which module to load:

| User Says | Load Module |
|-----------|-------------|
| "name my company", "brand name", "rename", "I need a name", "命名", "取名" | → Read `references/01-naming.md` |
| "brand positioning", "positioning statement", "value proposition", "how to position", "品牌定位" | → Read `references/02-positioning.md` |
| "brand voice", "tagline", "slogan", "messaging", "how should we sound", "品牌語言", "標語" | → Read `references/03-voice.md` |
| "visual identity", "logo", "colors", "color palette", "typography", "brand design", "品牌設計" | → Read `references/04-visual.md` |
| "SEO", "content strategy", "blog post", "keyword research", "rank on Google", "SEO文章" | → Read `references/05-seo.md` |
| "build my brand", "full branding", "start from scratch", "product branding", "品牌" | → Start at `references/01-naming.md`, proceed in order |

**IMPORTANT**: After reading the relevant reference file, follow ALL instructions in that file completely. The reference file IS the full module — it contains the discovery interview, frameworks, best practices, and output requirements.

### Passing Context Between Steps

Each module is **independently runnable** — the user may run them in separate sessions days apart. Context is carried via the output files saved in the project folder, not via conversation memory.

When starting any module, **first check the project folder** for existing output files:

1. Scan for: `01-naming.md`, `02-positioning.md`, `03-voice.md`, `04-visual.md`
2. Read any that exist and extract key outputs
3. Summarize what's already available before starting the discovery interview:

```
=== Context from Project Files ===
Project Folder: [path]
Name Candidates: [from 01-naming.md, if exists]
Working Name: [only if user has explicitly chosen one — otherwise use "[Brand]" as placeholder]
Domain Options: [from 01-naming.md, if exists]
Positioning: [from 02-positioning.md, if exists]
Value Proposition: [from 02-positioning.md, if exists]
Target Customer: [from 02-positioning.md, if exists]
Voice Traits: [from 03-voice.md, if exists]
Brand Pillars: [from 03-voice.md, if exists]
Tagline: [from 03-voice.md, if exists]
Color Palette: [from 04-visual.md, if exists]
===
```

Skip any discovery questions whose answers are already in the project files.

### Transitioning Between Steps

After completing each module:

1. **Save the output file** to `{Project Folder}/0X-module-name.md`
   - Include YAML frontmatter with `project`, `module`, and `date` fields
   - Confirm to the user: "✅ Saved to `{project-name}/0X-module-name.md`"

2. **Briefly note what's available next** — but do NOT prompt to continue:
   - Example: "When you're ready, the next step is ② Positioning."
   - The user decides when to run the next module. They may come back in a different session.

---

## Module Reference Files

Each module is a complete, self-contained guide stored in `references/`:

| File | Lines | Content |
|------|-------|---------|
| `references/01-naming.md` | ~490 | Lexicon methodology: Identify brief (Diamond Framework) → Invent 60-100 names (3 cognitive perspectives) → Implement (screen → score → auto-select top 10 balanced candidates: ~5 real words + ~5 engineered) |
| `references/02-positioning.md` | ~225 | 4 positioning frameworks (Jackson, Dunford, Diamond, Map) → statement + value prop |
| `references/03-voice.md` | ~265 | Messaging hierarchy → taglines → voice guidelines → tone matrix → AI-ready governance |
| `references/04-visual.md` | ~330 | Color palette → typography → logo brief → application guidelines |
| `references/05-seo.md` | ~510 | Keyword research → content creation → GEO optimization → E-E-A-T → maintenance |

**When to read a reference file**: Read it IMMEDIATELY when the router determines which module to run. Read the FULL file before starting any work. Do NOT summarize or skip sections — follow the module's instructions exactly.

---

## Quick-Start: First Interaction

If the user's first message is vague (e.g., "help me with branding"), call `AskUserQuestion` with 2 questions:

**Q1:**
- question: "Where are you in the branding process?"
- header: "Starting point"
- multiSelect: false
- options:
  - { label: "Starting from zero", description: "No name, no positioning — start at Step ① Naming" }
  - { label: "Have a name", description: "Name is confirmed, need positioning and everything else" }
  - { label: "Name + positioning done", description: "Need voice, visuals, and/or SEO content" }
  - { label: "Not sure", description: "Help me figure out where to start" }

**Q2:**
- question: "What's most urgent right now?"
- header: "Priority"
- multiSelect: false
- options:
  - { label: "Name + domain", description: "Find and secure the right brand name" }
  - { label: "Brand strategy", description: "Define positioning, value proposition, target audience" }
  - { label: "Voice & messaging", description: "Taglines, copy, and tone guidelines" }
  - { label: "SEO & content", description: "Also covers visual identity direction via 'Other'" }

Based on answers, route to the correct module and start there.

---

## Language Note

Conduct the entire process in the user's language. All modules support multilingual workflows.
