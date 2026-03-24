
# Brand Visual Direction — Skill

> **Company Branding Workflow: Step ④ of 5**
> ① Naming → ② Positioning → ③ Voice & Messaging → `④ Visual Identity` → ⑤ SEO Content
>
> **Prerequisite**: Run `brand-voice` first — visual identity should express the strategy and voice, not lead them. At minimum, you need: brand name (working or confirmed), positioning statement, 3-4 voice adjectives.
> **Input from previous steps**: Brand name (working or confirmed), positioning, voice traits, target audience, brand pillars.
> **What this step produces**: Color palette (with hex codes), typography pairing, logo direction brief, visual do's and don'ts, application guidelines.
> **After this skill**: Run `seo-content` to start creating content that ranks.

A structured framework for defining the visual direction of a brand. This skill does NOT design logos — it creates a **visual strategy brief** that guides designers, giving them clear direction instead of vague "make it look good."

**Important**: Claude generates visual direction docs, mood board descriptions, and specifications — not actual logo files or illustrations. The output is a brief for a designer or design tool.

### Tool Usage Rule

**ALWAYS use the `AskUserQuestion` tool for all questions throughout this skill.** Every round of questions should be presented as interactive clickable choices, not plain text questions.

Rules for `AskUserQuestion`:
- 1-4 questions per call
- 2-4 options per question (users can always select "Other" for custom input)
- Each option needs a short `label` (1-5 words) and a `description`
- Each question needs a `header` tag (max 12 chars)
- Use `multiSelect: true` when multiple answers apply
- Use `multiSelect: false` for single-choice questions
- No `rank_priorities` — use multi-select + ask to prioritize in follow-up if needed

---

## Phase 1: Discovery Interview

**If the user just completed `brand-voice`**: Ask them to share their brand name, positioning statement, voice adjectives (3-4), and brand pillars. Use these as input — don't re-ask what's already been answered. You can skip Round 1 and go straight to Round 2 (Visual Taste).

### Round 1 — Brand Context

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Do you have brand positioning and voice defined already?"
- header: "Prior work"
- multiSelect: false
- options:
  - { label: "Yes, both done", description: "Positioning + voice complete — ready to define visuals" }
  - { label: "Positioning only", description: "Have positioning, no voice guidelines yet" }
  - { label: "Nothing yet", description: "Starting from scratch — will define strategy as we go" }
  - { label: "Loosely defined", description: "Have some rough ideas but nothing formalized" }

**Q2:**
- question: "Where will this identity primarily live?"
- header: "Platform"
- multiSelect: true
- options:
  - { label: "Web app / SaaS", description: "Product UI, dashboards, in-app design" }
  - { label: "Marketing website", description: "Public-facing homepage and landing pages" }
  - { label: "Social / pitch deck", description: "Social media graphics and investor presentations" }
  - { label: "Mobile app", description: "iOS / Android — also physical product / print via 'Other'" }

**Q3:**
- question: "Any existing visual assets to keep or replace?"
- header: "Existing assets"
- multiSelect: false
- options:
  - { label: "Starting from scratch", description: "No existing visual assets — fully new identity" }
  - { label: "Keep existing logo", description: "Have a logo, want to build around it" }
  - { label: "Replace existing logo", description: "Have a logo but want a new one" }
  - { label: "Partial brand guidelines", description: "Have some guidelines but they need expansion or refresh" }

### Round 2 — Visual Taste

Call `AskUserQuestion` with 3 questions (visual spectrums):

**Q1:**
- question: "Overall visual feeling?"
- header: "Feeling"
- multiSelect: false
- options:
  - { label: "Warm & Human", description: "Organic shapes, warm colors, approachable, consumer-friendly" }
  - { label: "Cool & Technical", description: "Sharp edges, dark/neutral palette, precise, developer-native" }
  - { label: "Balanced", description: "Technical backbone with human touch — modern SaaS feel" }

**Q2:**
- question: "Visual complexity and energy?"
- header: "Complexity"
- multiSelect: false
- options:
  - { label: "Minimal & Calm", description: "Clean, lots of whitespace, quiet confidence" }
  - { label: "Dynamic & Bold", description: "High contrast, strong typography, makes an entrance" }
  - { label: "Rich & Detailed", description: "Dense information, layered visuals, illustration-heavy" }

**Q3:**
- question: "Era / vibe?"
- header: "Era"
- multiSelect: false
- options:
  - { label: "Timeless & Classic", description: "Won't look dated in 5 years — clean fundamentals" }
  - { label: "Modern & Cutting-edge", description: "Current design trends — dark mode, gradient, glassmorphism" }
  - { label: "Retro with a twist", description: "Nostalgic references made fresh — vintage color, serif type" }

Then follow up with `AskUserQuestion`:

**Q1:**
- question: "Brands whose VISUAL style you admire:"
- header: "Visual admire"
- multiSelect: true
- options:
  - { label: "Stripe / Linear", description: "Minimal, precise, dark mode, developer-first" }
  - { label: "Vercel / Figma", description: "Modern SaaS, bold typography, high contrast" }
  - { label: "Apple / Notion", description: "Premium, clean, human-centered, light and airy" }
  - { label: "Other", description: "Type your reference brand(s) in the next message" }

### Round 3 — Color & Constraints

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Any color families you're drawn to?"
- header: "Color — draw"
- multiSelect: true
- options:
  - { label: "Blue / Navy / Teal", description: "Trust, stability, professionalism — also Purple via 'Other'" }
  - { label: "Green / Amber", description: "Growth, optimism, energy — also Red/Coral via 'Other'" }
  - { label: "Black & White", description: "Premium, bold, high contrast — minimal color approach" }
  - { label: "No preference", description: "Open to any direction — let the brand strategy lead" }

**Q2:**
- question: "Any colors to AVOID?"
- header: "Color — avoid"
- multiSelect: true
- options:
  - { label: "Blue (too corporate)", description: "Feels generic, overused in B2B/enterprise" }
  - { label: "Red (too aggressive)", description: "Feels alarming, urgent, or associated with errors" }
  - { label: "Green (too eco)", description: "Feels like sustainability/environment — wrong association" }
  - { label: "No restrictions", description: "Open to any color family" }

**Q3:**
- question: "Budget for design execution?"
- header: "Design budget"
- multiSelect: false
- options:
  - { label: "DIY / AI tools", description: "Canva, Looka, Midjourney — no designer budget" }
  - { label: "Freelance ($50-500)", description: "Vetted Fiverr or 99designs freelancer" }
  - { label: "Designer ($500-5K)", description: "Dribbble or Upwork specialist" }
  - { label: "Agency ($5K+)", description: "Professional brand agency engagement" }

---

## Phase 2: Color Palette Strategy

### Color Psychology Reference

| Color Family | Associations | Best For |
|-------------|-------------|----------|
| **Blue** | Trust, stability, professionalism | Fintech, enterprise, healthcare |
| **Purple** | Premium, creative, innovative | AI, design tools, luxury |
| **Green** | Growth, nature, health, money | Sustainability, fintech, health |
| **Red/Coral** | Energy, urgency, passion | Consumer, food, entertainment |
| **Orange/Amber** | Friendly, optimistic, accessible | Consumer apps, education |
| **Teal** | Modern, calm, balanced | SaaS, wellness, tech |
| **Black** | Premium, bold, authoritative | Luxury, fashion, high-end tech |
| **Navy** | Trustworthy, established, deep | Finance, consulting, enterprise |

### Palette Construction

Build a palette with these roles:

| Role | Purpose | Example |
|------|---------|---------|
| **Primary** | Main brand color, logo, CTAs | 1 color |
| **Secondary** | Supporting, accents, illustrations | 1-2 colors |
| **Neutral** | Text, backgrounds, borders | 2-3 shades (dark, medium, light) |
| **Semantic** | Success, warning, error states | Green, amber, red |

Generate 2-3 palette options based on the discovery answers. For each palette provide:
- Hex codes for every color
- Color name (give each a memorable name, e.g., "Midnight" not just "#1A1A2E")
- Usage context (where to use each)
- Light mode and dark mode versions

### Palette Dos and Don'ts

- ✅ Test contrast ratios (WCAG AA minimum: 4.5:1 for text)
- ✅ Check how colors look in grayscale (for accessibility)
- ✅ Ensure primary color works on both white and dark backgrounds
- ❌ Don't use more than 2 saturated colors
- ❌ Don't pick colors that clash with common UI patterns (e.g., red for a positive action)

---

## Phase 3: Typography Strategy

### Font Pairing Approach

| Role | Purpose | Typical Choice |
|------|---------|----------------|
| **Heading** | Brand personality, impact | Sans-serif or distinctive display font |
| **Body** | Readability, long-form content | Clean sans-serif or readable serif |
| **Mono** | Code, data, technical content | Monospace font (if tech product) |

### Font Personality Map

| Feel | Font Families to Consider |
|------|--------------------------|
| **Modern & Clean** | Geist, Inter, Satoshi, General Sans, Plus Jakarta Sans |
| **Technical & Precise** | Geist Mono, IBM Plex Sans, JetBrains Mono, Space Grotesk |
| **Premium & Elegant** | Fraunces, Playfair Display, Cormorant |
| **Friendly & Rounded** | Nunito, Rubik, Quicksand |
| **Bold & Confident** | Clash Display, Cabinet Grotesk, Outfit |
| **Neutral & Professional** | Inter, Geist, Figtree, DM Sans |
| **Geometric & Startup** | Manrope, Sora, Urbanist |

> **Geist / Geist Mono** — Vercel's open-source typeface. Optimized for code and UI. Extremely clean at all sizes. Ideal for developer tools, platforms, and technical products. Free at vercel.com/font.

Generate 2-3 font pairing recommendations based on brand voice. For each:
- Heading font + Body font + (optional) Mono font
- Where to get it (Google Fonts free / paid license needed)
- Sample text showing the pairing

### Typography Dos and Don'ts

- ✅ Limit to 2 font families (3 max if including mono)
- ✅ Use font weight for hierarchy, not multiple fonts
- ✅ Ensure the body font is highly readable at 16px
- ❌ Don't pair two decorative fonts
- ❌ Don't use fonts with limited character sets if multi-language

---

## Phase 4: Logo Direction Brief

**Claude does NOT design logos.** Instead, generate a brief that a designer can execute from.

### Logo Brief Template

| Field | Description |
|-------|-------------|
| **Brand name** | The text to include |
| **Logo type** | Wordmark / Lettermark / Icon + Wordmark / Abstract Symbol / Emblem |
| **Personality keywords** | 3-5 words the logo should convey (from voice/positioning) |
| **Metaphor / Symbol direction** | If applicable — what concepts or imagery to explore |
| **Style direction** | Geometric / Organic / Minimal / Technical / Illustrative |
| **Color direction** | Primary palette from Phase 2 |
| **Font direction** | Heading font from Phase 3 (or custom lettering) |
| **Must work at** | Favicon (16px), app icon (120px), website header, business card, social avatar |
| **Avoid** | Specific imagery, clichés, or styles to avoid |

### Logo Type Guide

| Type | Best When | Example |
|------|-----------|---------|
| **Wordmark** | Name is short & distinctive, early-stage | Stripe, Google, Spotify |
| **Lettermark** | Name is long, needs abbreviation | IBM, HBO, NASA |
| **Icon + Wordmark** | Want a symbol that can stand alone eventually | Apple, Nike, Slack |
| **Abstract Symbol** | Want maximum flexibility, global brand | Airbnb, Pepsi |
| **Emblem** | Heritage, authority, institutions | Starbucks, Harvard |

Recommend 1-2 logo types based on the brand context.

### Where to Execute

| Budget | Tool / Service |
|--------|---------------|
| **Free / DIY** | Canva, Looka, Brandmark.io |
| **Budget ($50-500)** | 99designs, Fiverr (vetted designers), Looka premium |
| **Mid ($500-5K)** | Dribbble freelancers, Upwork specialists |
| **Premium ($5K+)** | Brand agencies (Pentagram, Wolff Olins, Focus Lab) |

---

## Phase 5: Output — Visual Direction Document

Compile all outputs into a clean deliverable:

1. **Visual Positioning** — 1-2 sentences describing the intended visual feel
2. **Color Palette** — All colors with hex codes, names, and usage rules
3. **Typography** — Font pairing with sizing/weight hierarchy
4. **Logo Direction Brief** — Complete brief for a designer
5. **Visual Do's and Don'ts** — 5-8 rules for maintaining visual consistency
6. **Mood Reference** — 3-5 reference brands or visual styles, with explanation of what to take from each (NOT to copy, but to reference)
7. **Application Contexts** — How the identity should flex across: website, app, pitch deck, social media, email

### Quality Checks

- Does the visual direction match the brand voice? (warm voice ≠ cold visuals)
- Would the color palette still work if printed in black and white?
- Can the typography scale from mobile to desktop?
- Is the logo direction brief specific enough for a designer to start working?
- Does it look different from the top 3 competitors?

---

## Expert Principles

- **Strategy before aesthetics.** Never pick colors because they "look nice" — pick them because they communicate the right message.
- **Constraint breeds creativity.** A tight palette (2-3 colors) is almost always stronger than a rainbow.
- **Design for the smallest size first.** If it doesn't work as a favicon, rethink it.
- **Consistency > Perfection.** A decent identity applied consistently beats a perfect logo used inconsistently.
- **Trends fade, clarity doesn't.** Avoid trendy design elements that will date the brand in 2 years.
- **Show, don't describe.** Whenever possible, show visual references rather than describing in words.
- **Visual identity must match voice.** A warm, playful voice with a cold, corporate visual identity confuses customers. Alignment is everything.
- **Accessibility is not optional.** 4.5:1 contrast ratio minimum (WCAG AA). Test in grayscale. Consider color blindness.
- **The logo is not the brand.** The logo is one touchpoint. Color, typography, photography style, illustration style, spacing — these create brand recognition at scale.
- **Simplicity scales.** The simpler your visual system, the easier it is to apply consistently across 50+ touchpoints.

---

## Common Visual Identity Mistakes

| Mistake | Why It Hurts | Fix |
|---------|-------------|-----|
| **Too many colors** | Chaotic, unmemorable, hard to apply consistently | Limit to 1 primary + 1-2 secondary + neutrals. 2-3 saturated colors max. |
| **Too many fonts** | Visual noise, looks unprofessional | 2 font families max (3 if including mono). Use weight for hierarchy, not more fonts. |
| **Logo doesn't scale** | Looks great on a billboard, unreadable as favicon | Design for 16px first. Test at every size from favicon to banner. |
| **No dark mode version** | 50%+ of users prefer dark mode. Brand looks broken without it. | Define both light and dark mode palettes from day one. |
| **Copying competitor aesthetics** | You become visually indistinguishable. Customers can't tell you apart. | Study competitors to find visual gaps, not to imitate. Differentiate intentionally. |
| **Trendy design choices** | Gradients, glassmorphism, 3D blobs — look dated in 18 months | Prefer timeless over trendy. Classic design systems age better. |
| **Ignoring context** | Logo looks great on white, invisible on a dark header or busy background | Test identity across ALL real application contexts: web, mobile, email, social, print. |
| **No clear guidelines** | Every designer interprets differently. Inconsistency everywhere. | Document spacing, minimum sizes, color usage rules, do's and don'ts with examples. |
| **Stock photo dependency** | Generic, inauthentic, same photos as competitors | Invest in original photography, custom illustrations, or a distinctive illustration style. |
| **Color fails accessibility** | Text unreadable for 8% of males with color vision deficiency | Test contrast ratios. Avoid red/green as only differentiator. Provide alternatives. |
| **Visual ≠ Voice mismatch** | Playful voice + corporate visuals. Customers feel confused. | Audit voice and visual together. They must tell the same story. |
| **Overly complex brand guide** | 100-page PDF nobody reads. Inconsistency follows anyway. | Keep the core guide to 5-10 pages. Detailed specs in appendix. Decision tree > essay. |

---

## Visual Identity Best Practices by Application

### Digital Product (Web App / Mobile App)

- Use your primary color sparingly — only for CTAs and key interactive elements
- Neutral palette carries 80% of the UI; brand color is the accent
- Typography hierarchy: don't use your display/heading font for body text in-app
- Test color palette in actual UI components (buttons, cards, forms) — not just in mood boards
- Ensure all interactive states are defined: default, hover, active, disabled, error
- Dark mode is not just "invert the colors" — design it intentionally

### Marketing Website

- Hero section: brand at full expression (bold colors, large typography, signature imagery)
- Body content: dial back to neutral palette for readability
- CTAs: primary brand color, consistent everywhere
- Photography/illustration style should be distinctive and ownable

### Social Media

- Design templates for recurring content types (announcements, quotes, tutorials)
- Ensure brand is recognizable at small sizes (mobile feed thumbnails)
- Color + typography should be identifiable even without the logo

### Pitch Deck / Investor Materials

- More restrained palette — lean on neutrals with strategic brand color usage
- Typography: prioritize readability over brand expression
- Data visualization should use brand color palette
- Professional but not generic — brand personality should still come through

---

## Color Accessibility Quick Reference

| Test | Tool | Standard |
|------|------|----------|
| **Contrast ratio** | webaim.org/resources/contrastchecker | 4.5:1 minimum for text (WCAG AA) |
| **Color blindness** | color-blindness.com/coblis-color-blindness-simulator | Test all key color combinations |
| **Grayscale test** | Convert palette to grayscale in any design tool | Elements should still be distinguishable |

### Safe Color Combinations (High Contrast)

- Dark text on light background (always safest)
- White text on dark or saturated backgrounds (check contrast)
- Avoid: light text on light background, red on green, blue on purple

---

## AI Era: Visual Asset Generation

In 2026, AI tools are a standard part of the visual design workflow. Include guidance on how to use them within the brand system.

### Prompt-Based Asset Generation

When the brand system is defined, translate it into AI tool prompts:

| What You Need | Tool | Prompt Approach |
|---------------|------|----------------|
| **Mood board / inspiration** | Midjourney, Adobe Firefly | `[brand adjectives] brand identity, [color names], [style direction], high-end startup visual` |
| **Illustration style** | Midjourney, DALL-E, Ideogram | Establish a "style anchor" — generate 3-5 reference images, then use `--sref` (Midjourney) to lock style |
| **Social media graphics** | Canva AI, Adobe Express | Upload brand colors + fonts as a custom kit; use AI to generate layout variants |
| **Icon and logo exploration** | Ideogram, Recraft | Best for wordmarks and geometric logos; poor for complex illustration |
| **Photography style** | Midjourney | Lock lighting, color grade, and subject style in a reusable prompt template |

### AI Visual Governance

Define rules for AI-generated assets before the team uses them freely:

- **Approved tools**: List which AI tools are approved (e.g., Midjourney for illustration, Canva AI for social)
- **Style anchor prompts**: Store 2-3 reference prompts that produce on-brand outputs; share with team
- **Human review gate**: All AI-generated images used publicly need human sign-off — especially for faces, hands, and text
- **Brand kit injection**: Always input your color palette, font, and brand adjectives into AI tools before generating
- **Anti-patterns**: List specific outputs that are off-brand (e.g., "no dark dramatic lighting for our warm brand", "no corporate stock-photo style")

### Modern Design System References

For developer tools and SaaS products, these open-source design systems set the quality bar:

| System | Owner | Best For |
|--------|-------|----------|
| **Geist** | Vercel | Developer tools, dark-mode-first, minimal |
| **Radix UI** | WorkOS | Component library with strong accessibility |
| **shadcn/ui** | Community | Tailwind-based; the default for modern Next.js apps |
| **Base UI** | MUI team | Headless, composable primitives |
| **Ant Design** | Alibaba | Enterprise dashboards, data-heavy interfaces |

These are not to copy — they're to establish expectations for polish, spacing, and interaction quality.

---

## Visual Identity Maintenance Cadence

| Timeframe | Action |
|-----------|--------|
| **Monthly** | Spot-check: are recent designs (social, email, web updates) following the guidelines? |
| **Quarterly** | Audit all public-facing touchpoints. Screenshot everything. Note inconsistencies. |
| **Biannually** | Review guidelines with design team. Update examples. Add new application templates if needed. |
| **Annually** | Full visual identity review. Still differentiated from competitors? Still aligned with positioning? |
| **Trigger-based** | Revisit immediately if: rebrand, new product line, new market, significant competitor visual change |

---

## Language Note

Visual direction is largely language-agnostic, but typography recommendations should account for the languages the brand needs to support (Latin, CJK, Arabic, etc.). Some fonts have limited character support — always verify.

---

## Save Output

After presenting the Visual Direction Document to the user, save it to the project folder:

1. Use the `Project Folder` path from the context block
2. Write the complete output to `{Project Folder}/04-visual.md` using the Write tool
3. File structure:
   ```
   ---
   project: {project-name}
   module: 04-visual
   date: {today's date}
   ---

   # Visual Identity Direction

   ## Visual Positioning

   ## Color Palette
   [primary, secondary, neutral — hex codes + names + usage]

   ## Typography
   [heading font + body font + optional mono, with sources]

   ## Logo Direction Brief
   [logo type, personality, style, size requirements]

   ## Visual Do's & Don'ts

   ## Mood Reference

   ## Application Contexts
   ```
4. Confirm: "✅ Saved to `{project-name}/04-visual.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **Visual direction complete!** The final step is **SEO content strategy** — creating content that ranks in Google and gets cited by AI search engines, all aligned with your new brand identity. Want to start `seo-content` now?
