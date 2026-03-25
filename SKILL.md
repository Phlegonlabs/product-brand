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

## Onboarding

**Run this FIRST for every new branding project — before routing to any module.**

### When to skip Onboarding

Skip if the user:
- References an existing project folder by name (e.g., "continue my-startup-brand")
- Names a specific step to resume (e.g., "run step 3 for acme-brand", "continue positioning")

If skipping: confirm the folder exists, scan for existing output files, summarize what's been completed, then route to the correct module.

---

### Turn 1: Welcome + Situation

Output this welcome message as plain text (not AskUserQuestion):

> "Welcome to Brand Builder — a 5-step system that takes your brand from zero to fully defined.
>
> Here's the roadmap:
> ① Naming — Find the right brand name + domain
> ② Positioning — Define your market position + value prop
> ③ Voice & Messaging — Taglines, tone, and messaging hierarchy
> ④ Visual Identity — Color palette, typography, logo brief
> ⑤ SEO Content — Content strategy that ranks
>
> Each step builds on the previous one, but you can also jump to whichever step you need. We'll save everything to a project folder so you can pick up anytime.
>
> Let's start with a few quick questions."

Then immediately call `AskUserQuestion` with 2 questions:

**Q1:**
- question: "What best describes your situation?"
- header: "Situation"
- multiSelect: false
- options:
  - { label: "Starting from zero", description: "New idea or early-stage project — no branding done yet" }
  - { label: "Have some pieces", description: "Have a name, rough positioning, or partial brand work" }
  - { label: "Rebranding", description: "Existing brand that needs a refresh or overhaul" }
  - { label: "Just need one thing", description: "Only need help with a specific step (e.g., tagline, SEO)" }

**Q2:**
- question: "What are you building?"
- header: "Project type"
- multiSelect: false
- options:
  - { label: "Software / SaaS", description: "App, platform, developer tool, or digital service" }
  - { label: "Consumer product", description: "Physical product, D2C brand, or consumer service" }
  - { label: "Agency / consulting", description: "Service business, freelance, or professional practice" }
  - { label: "Something else", description: "Select 'Other' to describe your project" }

---

### Turn 2: Audience + First Step

Call `AskUserQuestion` with 2 questions:

**Q1:**
- question: "Who is your primary audience?"
- header: "Audience"
- multiSelect: true
- options:
  - { label: "Developers", description: "Engineers, DevOps, technical builders" }
  - { label: "Enterprise buyers", description: "B2B decision-makers, procurement, executives" }
  - { label: "Consumers", description: "General public, individuals, end users" }
  - { label: "Creators / SMBs", description: "Designers, founders, indie builders, small businesses" }

**Q2:**
- question: "What do you want to tackle first?"
- header: "First step"
- multiSelect: false
- options (adjust based on Turn 1 Q1 answer):
  - If "Starting from zero" or "Rebranding": show these options:
    - { label: "Name + domain", description: "Start at Step ① — find and secure a brand name" }
    - { label: "Brand strategy", description: "Start at Step ② — define positioning + value prop" }
    - { label: "Voice & messaging", description: "Start at Step ③ — taglines, tone, copy guidelines" }
    - { label: "Start from Step ①", description: "Do it all in order — naming first, then everything else" }
  - If "Just need one thing": show all 5 steps:
    - { label: "Name + domain", description: "Step ① — brand naming" }
    - { label: "Positioning", description: "Step ② — market position + value prop" }
    - { label: "Voice & messaging", description: "Step ③ — taglines + tone" }
    - { label: "Visual identity", description: "Step ④ — colors, typography, logo brief — or SEO via 'Other'" }
  - If "Have some pieces": default to all 5 steps with appropriate starting point

---

### Turn 3: Project Folder + Description

Call `AskUserQuestion` with 2 questions:

**Q1:**
- question: "Give your project a folder name (lowercase, hyphens). All outputs will be saved here."
- header: "Project name"
- multiSelect: false
- options:
  - { label: "my-brand", description: "Simple format — use 'Other' to type your actual project name" }
  - { label: "acme-2025", description: "Company + year format — use 'Other' to customize" }
  - { label: "I'll type it", description: "Select 'Other' to enter a custom folder name" }

The user will typically select "Other" and type their own project name — that is the expected flow.

**Q2:**
- question: "Describe your product or business in one line (or skip for now)."
- header: "Description"
- multiSelect: false
- options:
  - { label: "I'll type it next", description: "I'll describe the product in my next message" }
  - { label: "Skip for now", description: "Start the module and I'll explain as we go" }

Then let the user type their description in their reply (if they chose "I'll type it next").

After Turn 3:
1. Create the project folder: `{repo-root}/{project-name}/`
2. Confirm: "Project folder `{project-name}/` created. All outputs will be saved here as we go."
3. Output the onboarding brief as an internal context block:

```
=== Onboarding Brief ===
Situation: [from Turn 1 Q1]
Project Type: [from Turn 1 Q2]
Audience: [from Turn 2 Q1]
First Step: [from Turn 2 Q2]
Description: [from Turn 3 Q2, if provided]
Project Folder: {project-name}/
===
```

4. Route to the selected module using the Router below.

### Passing Onboarding Context to Modules

When routing to a module after onboarding, if a Discovery Interview question was already answered during onboarding, **pre-fill the answer and ask the user to confirm** rather than re-asking from scratch. Present it as: "Based on what you told me earlier, [pre-filled answer] — does that still apply?"

Key overlaps to watch for:
- **Naming Round 1 Q1** (what are we naming?) ← Project Type
- **Naming Round 1 Q2** (who is the audience?) ← Audience
- **Positioning Round 1 Q1** (what stage are you at?) ← Situation
- **Positioning Round 1 Q2** (who is the audience?) ← Audience
- **Positioning Round 1 Q3** (describe your product) ← Description

This only applies within the same session. If the user returns in a new session, the module's full Discovery Interview runs normally.

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

**Before routing**: If this is a new project and Onboarding has not been completed, run Onboarding first. Only route to a module after onboarding is complete and a project folder has been created.

**Exception**: Skip Onboarding if the user is continuing an existing project (references a folder by name) or explicitly names a step to resume.

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

## Language Note

Conduct the entire process in the user's language. All modules support multilingual workflows.
