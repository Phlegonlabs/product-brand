---
name: product-branding
description: >
  Complete product branding toolkit with 5 sequential modules: Naming, Positioning, Voice & Messaging, Visual Identity, and SEO Content. Use this skill for ANY branding-related request. Triggers include 'brand', 'branding', 'naming', 'name my company', 'brand name', 'product name', 'rename', 'rebrand', 'brand strategy', 'positioning', 'brand positioning', 'value proposition', 'brand voice', 'tagline', 'slogan', 'messaging', 'brand tone', 'visual identity', 'logo', 'color palette', 'brand design', 'typography', 'SEO', 'SEO content', 'content strategy', 'keyword research', 'blog post', '品牌', '命名', '取名', '品牌定位', '品牌策略', '標語', '品牌設計', 'SEO文章', or ANY request related to building, defining, or improving a brand. This is a comprehensive branding system — always start here for branding work.
---

# Product Branding Toolkit

A complete, 5-step branding system that takes a company from zero to a fully defined brand with content strategy. Each step builds on the previous one.

### Tool Usage Rule

**ALWAYS use the `ask_user_input` tool for all questions throughout this skill.** Every question should be presented as interactive clickable choices, not plain text.

---

## Project Initialization

**Run this FIRST before any module — every time a new branding project starts.**

1. Ask for the project name using `ask_user_input`:

   **Q** (free text / single_select): "What should we call this project folder? Use lowercase letters and hyphens (e.g., `my-brand`, `acme-2025`)."
   - Options: (let user type freely — present 2-3 examples as suggestions)

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
| ① | **Naming** | Name generation via Identify → Invent → Implement | Brand name + domain strategy |
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

When moving from one step to the next, carry forward ALL outputs from previous steps. Summarize them at the start of the next module:

```
=== Context from Previous Steps ===
Project Folder: [repo-root/project-name]
Name: [confirmed name]
Domain: [registered domain]
Positioning: [positioning statement]
Value Proposition: [one sentence]
Target Customer: [description]
Voice Traits: [3-4 adjectives]
Brand Pillars: [list]
Tagline: [if created]
Color Palette: [if defined]
===
```

This prevents re-asking questions and ensures continuity.

### Transitioning Between Steps

After completing each module:

1. **Save the output file first** (before prompting the user):
   - Write the complete module deliverables to `{Project Folder}/0X-module-name.md`
   - File format: include a YAML frontmatter block with `project`, `module`, and `date` fields, followed by the full deliverable content
   - Confirm to the user: "✅ Saved to `{project-name}/0X-module-name.md`"

2. **Then prompt the user** with `ask_user_input`:

**Q** (single_select): "Step [N] complete! Ready for the next step?"
- Options: "Yes, let's continue to [next step name]" / "I want to revisit something first" / "That's enough for today"

If "revisit": ask what they want to change and loop back.
If "enough for today": summarize what's been completed and what's remaining. Tell them they can come back and say "continue branding" to pick up where they left off.

---

## Module Reference Files

Each module is a complete, self-contained guide stored in `references/`:

| File | Lines | Content |
|------|-------|---------|
| `references/01-naming.md` | ~490 | Lexicon methodology: Identify brief (Diamond Framework) → Invent 60-100 names (3 cognitive perspectives) → Implement (screen → score → domain strategy → recommend) |
| `references/02-positioning.md` | ~225 | 4 positioning frameworks (Jackson, Dunford, Diamond, Map) → statement + value prop |
| `references/03-voice.md` | ~265 | Messaging hierarchy → taglines → voice guidelines → tone matrix → AI-ready governance |
| `references/04-visual.md` | ~330 | Color palette → typography → logo brief → application guidelines |
| `references/05-seo.md` | ~510 | Keyword research → content creation → GEO optimization → E-E-A-T → maintenance |

**When to read a reference file**: Read it IMMEDIATELY when the router determines which module to run. Read the FULL file before starting any work. Do NOT summarize or skip sections — follow the module's instructions exactly.

---

## Quick-Start: First Interaction

If the user's first message is vague (e.g., "help me with branding"), use `ask_user_input`:

**Q1** (single_select): "Where are you in the branding process?"
- Options: Starting from zero / Have a name, need everything else / Have name + positioning, need voice & visuals / Just need SEO content / Not sure, help me figure out

**Q2** (single_select): "What's most urgent right now?"
- Options: Finding a name + domain / Defining brand strategy / Creating messaging & tagline / Visual identity & logo direction / SEO & content strategy

Based on answers, route to the correct module and start there.

---

## Language Note

Conduct the entire process in the user's language. All modules support multilingual workflows.
