
# Brand Voice & Messaging — Skill

> **Company Branding Workflow: Step ③ of 5**
> ① Naming → ② Positioning → `③ Voice & Messaging` → ④ Visual Identity → ⑤ SEO Content
>
> **Prerequisite**: Run `brand-positioning` first — positioning is the strategic foundation that voice is built on. If the user hasn't done positioning, do a lightweight version in the discovery phase.
> **Input from previous steps**: Brand name (working or confirmed), positioning statement, value proposition, target customer profile.
> **What this step produces**: Mission/Vision/Values, brand pillars, messaging hierarchy (tagline → one-liner → pitch → boilerplate), voice & tone guidelines, word bank.
> **After this skill**: Run `brand-visual` to define how the brand looks.

A structured framework for defining how a brand speaks, from internal messaging docs to public-facing taglines. This skill turns positioning strategy into words.

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

**If the user just completed `brand-positioning`**: Ask them to share their positioning statement, value proposition, and target customer profile. Use these as input — don't re-ask what's already been answered. You can skip straight to Round 2 (Voice Character).

### Round 1 — Brand Context

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Do you already have a positioning statement?"
- header: "Positioning"
- multiSelect: false
- options:
  - { label: "Yes, I'll share it", description: "I have a positioning statement — I'll paste it next" }
  - { label: "Needs refinement", description: "I have something rough but it's not solid yet" }
  - { label: "No, help me", description: "I haven't done positioning yet — let's figure it out" }

**Q2:**
- question: "Who is your primary audience?"
- header: "Audience"
- multiSelect: true
- options:
  - { label: "Developers", description: "Engineers, DevOps, technical builders" }
  - { label: "Enterprise buyers", description: "B2B decision-makers, procurement, executives" }
  - { label: "Consumers", description: "General public, individuals, end users" }
  - { label: "Creators / mixed", description: "Designers, founders, indie builders — or mixed audience" }

**Q3:**
- question: "What one thing should everyone remember about your brand?"
- header: "Core message"
- multiSelect: false
- options:
  - { label: "Most trusted", description: "We're the safe, reliable, credible choice" }
  - { label: "Easiest to use", description: "We make things simple, frictionless, delightful" }
  - { label: "Most innovative", description: "We're at the frontier, ahead of the curve" }
  - { label: "I'll describe it", description: "None of these fit — I'll explain in my next message" }

### Round 2 — Voice Character

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Pick traits that FIT your brand voice:"
- header: "Voice — fit"
- multiSelect: true
- options:
  - { label: "Authoritative / Bold", description: "Confident, commanding, direct — also Formal/Serious via 'Other'" }
  - { label: "Approachable / Warm", description: "Friendly, human, inviting — also Casual/Playful via 'Other'" }
  - { label: "Technical / Precise", description: "Expert-level, accurate, engineer-respecting" }
  - { label: "Simple / Understated", description: "Clear, clean, no noise — also Cool/Minimal via 'Other'" }

**Q2:**
- question: "Pick traits that DON'T fit:"
- header: "Voice — avoid"
- multiSelect: true
- options:
  - { label: "Authoritative / Bold", description: "Too commanding, cold, or aggressive" }
  - { label: "Approachable / Warm", description: "Too casual, friendly, or unprofessional" }
  - { label: "Technical / Precise", description: "Too nerdy, jargon-heavy, or intimidating" }
  - { label: "Simple / Understated", description: "Too plain, boring, or lacking personality" }

**Q3:**
- question: "If your brand were a person at a dinner party, they'd be:"
- header: "Personality"
- multiSelect: false
- options:
  - { label: "The trusted advisor", description: "Everyone listens — authoritative, calm, never shows off" }
  - { label: "The witty friend", description: "Makes things fun — clever, light, keeps energy up" }
  - { label: "The quiet expert", description: "Speaks only when it matters — every word carries weight" }
  - { label: "The enthusiastic visionary", description: "Inspires the whole table — passionate, forward-looking" }

### Round 3 — Messaging Boundaries

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Words or vibes you WANT associated with the brand:"
- header: "Word — want"
- multiSelect: true
- options:
  - { label: "Reliable / Secure", description: "Trust, infrastructure, safety, stability" }
  - { label: "Fast / Seamless", description: "Speed, flow, frictionless, effortless" }
  - { label: "Simple / Open", description: "Clarity, transparency, accessible, minimal" }
  - { label: "Premium / Innovative", description: "High-end, cutting-edge, forward-looking" }

**Q2:**
- question: "Words or vibes to AVOID:"
- header: "Word — avoid"
- multiSelect: true
- options:
  - { label: "Buzzword-heavy", description: "Disruption, revolutionary, synergy, leverage, AI-powered" }
  - { label: "Hype / Trendy", description: "Blockchain, web3, next-gen — feels like marketing fluff" }
  - { label: "Corporate jargon", description: "Enterprise-grade, scalable solutions, best-in-class" }
  - { label: "Cheap / basic", description: "Anything that signals low quality or low ambition" }

**Q3:**
- question: "Brands whose VOICE you admire:"
- header: "Voice admire"
- multiSelect: true
- options:
  - { label: "Stripe / Linear", description: "Direct, precise, developer-respecting — no fluff" }
  - { label: "Apple / Notion", description: "Clean, aspirational, minimal copy, strong personality" }
  - { label: "Mailchimp / Basecamp", description: "Human, opinionated, warm, occasionally witty" }
  - { label: "Other", description: "Type your reference brand(s) in the next message" }

---

## Phase 2: Build the Messaging Framework

### Layer 1: Mission, Vision, Values

| Element | What It Answers | Length |
|---------|----------------|--------|
| **Mission** | Why do we exist? What do we do for our customers? | 1-2 sentences |
| **Vision** | What future are we building toward? | 1 sentence |
| **Values** | What principles guide our decisions? | 3-5 values, each with a 1-sentence explanation |

Generate 2 options for each, let the user choose.

### Layer 2: Value Proposition

One sentence that answers: "Why should a customer choose us over any alternative?"

Formula: `We help [target customer] [achieve outcome] by [unique mechanism], unlike [alternative] which [limitation].`

Generate 3 variations.

### Layer 3: Brand Pillars

3-4 core themes that all messaging ladders up to. Each pillar gets:
- **Pillar name** (2-3 words)
- **What it means** (1 sentence)
- **Proof point** (evidence or feature that supports it)

Example:
> **Pillar: Effortless Security**
> Meaning: Protection that works in the background, never in the way.
> Proof: Zero-config encryption on every transaction.

### Layer 4: Messaging Hierarchy

| Level | Purpose | Length | Example Use |
|-------|---------|--------|-------------|
| **Tagline** | Instant recall, brand essence | 2-6 words | Logo lockup, hero banner |
| **One-liner** | Explain what you do | 1 sentence | Homepage H1, pitch opening |
| **Elevator pitch** | Full context for a stranger | 30 seconds / 3-4 sentences | Networking, investor intro |
| **Boilerplate** | Standard company description | 1 paragraph | Press releases, about page |

Generate all 4 levels. For tagline, provide 5-8 options.

### Layer 5: Voice & Tone Guidelines

Define:

**Voice** (constant — who we are):
- 3-4 adjectives that describe the brand voice
- For each: a "Do" example and a "Don't" example

**Tone** (variable — adapts to context):

| Context | Tone Shift | Example |
|---------|-----------|---------|
| Marketing / Homepage | Confident, aspirational | "The future of agent payments" |
| Documentation / Help | Clear, patient, precise | "To set up your first wallet, follow these steps" |
| Error messages | Calm, helpful, not blaming | "Something went wrong. Let's try that again." |
| Social media | Casual, human, witty | "Agents don't sleep. Neither does your wallet." |
| Investor / Press | Authoritative, data-driven | "Processing $2M in agent transactions monthly" |

---

## Phase 3: Tagline Deep Dive

Taglines deserve extra work. Generate 15-20 tagline candidates across these categories:

| Category | What It Does | Example Style |
|----------|-------------|---------------|
| **Benefit-led** | States the outcome | "Shave time. Shave money." (Dollar Shave Club) |
| **Imperative** | Commands action | "Just do it." (Nike), "Think different." (Apple) |
| **Provocative** | Challenges assumptions | "Impossible is nothing." (Adidas) |
| **Descriptive** | Says what you do cleverly | "Financial infrastructure for the internet." (Stripe) |
| **Metaphorical** | Uses imagery | "Red Bull gives you wings." |
| **Question** | Makes you think | "Got milk?" |

### Tagline Scoring

Score each tagline on:

| Criteria | Question | Weight |
|----------|----------|--------|
| Memorability | Can you recall it after one hearing? | High |
| Clarity | Does it make sense without explanation? | High |
| Distinctiveness | Could a competitor use the same line? | High |
| Brand Fit | Does it match the voice and positioning? | High |
| Versatility | Does it work on a billboard AND a business card? | Medium |
| Longevity | Will it still work in 5 years? | Medium |

Present top 5 with scores.

---

## Phase 4: Output & Deliverables

Present the complete messaging framework as a clean document:

1. **Mission / Vision / Values**
2. **Value Proposition**
3. **Brand Pillars** (3-4)
4. **Messaging Hierarchy** (Tagline → One-liner → Elevator Pitch → Boilerplate)
5. **Voice Guidelines** (adjectives + do/don't examples)
6. **Tone Matrix** (context-specific tone shifts)
7. **Word Bank** (always use / never use)

### Quality Checks

- Read every piece of copy aloud. Does it sound natural?
- Could a new marketing hire write on-brand copy using only this doc?
- Does the tagline work without the logo next to it?
- Is the voice distinct from your top 3 competitors?
- Does the messaging hierarchy tell a consistent story at every level?

---

## Expert Principles

- **Voice is who you are. Tone is how you adapt.** Voice stays constant; tone shifts by context.
- **The best taglines come from positioning, not brainstorming.** Do the strategy work first.
- **Write for one person, not a crowd.** Great brand copy feels like a direct conversation.
- **Kill the jargon.** If your grandma can't understand it, simplify.
- **The 3-second test.** If someone lands on your homepage, can they understand what you do in 3 seconds?
- **Consistency > Creativity.** A mediocre message delivered consistently beats a brilliant message delivered inconsistently.
- **Do/Don't examples are mandatory.** Abstract adjectives ("be authentic") are useless. Concrete examples of good vs bad copy are what teams actually use.
- **Voice guidelines must cover ALL mediums.** Written, video, podcast, social, chatbot, AI-generated. Modern brands speak in many formats.
- **Voice guidelines that aren't used are fiction.** If the team ignores them, they're too complex, too vague, or weren't co-created. Simplify and involve everyone.
- **93% of consumers want brands to keep up with online culture** (Sprout Social 2025). Your voice can't be static — it needs to flex with cultural context while staying recognizable.
- **AI is now part of your voice system.** Chatbots, AI-generated emails, and automated responses all carry your brand voice. Voice guidelines must extend to AI prompt structure and tone filters.

---

## Common Voice & Messaging Mistakes

| Mistake | Why It Hurts | Fix |
|---------|-------------|-----|
| **Too vague guidelines** | "Be authentic and relatable" doesn't help anyone decide between a contraction and formal language | Write specific Do/Don't examples for every voice trait |
| **Developing in isolation** | Marketing writes guidelines; sales, CS, product never see them. Inconsistency follows. | Co-create with ALL customer-facing teams. One shared document. |
| **Voice without tone variation** | Same energy everywhere sounds robotic. Error messages shouldn't sound like marketing copy. | Define tone shifts per context: marketing, docs, errors, social, investor |
| **Ignoring non-text mediums** | Voice guidelines only cover blog posts. What about video scripts? Podcast intros? Chatbots? | Address voice across ALL channels including spoken, visual, and AI-generated |
| **All aspiration, no execution** | Beautiful 50-page brand bible that nobody reads | Keep it to 1-2 pages max. Decision tree format > essay format |
| **Not testing with real audience** | Sounds great internally, lands flat with customers | A/B test messaging. Monitor social sentiment. Adjust based on what resonates. |
| **Translating literally** | "Assume Nothing" → "Do Nothing" (HSBC). "Finger-lickin' good" → "Eat your fingers off" (KFC China) | Never translate taglines or voice literally. Recreate meaning with native speakers. |
| **Forced humor** | Trying to be Wendy's Twitter when your audience is enterprise CFOs | Humor must be authentic to your brand. If unsure, keep a straight face (Mailchimp's rule). |
| **No word bank** | Teams use different terms for the same thing. Inconsistency creeps in. | Maintain always-use / never-use word lists. Update regularly. |
| **Set and forget** | Voice guidelines from 2022 don't reflect your 2026 brand | Review voice guidelines every 6 months. Update when brand, audience, or market shifts. |

---

## Voice Governance & AI Era Best Practices

### AI-Ready Voice Guidelines

In 2026, AI writes a growing percentage of brand communication (chatbots, email sequences, generated content). Your voice guidelines need to account for this:

- **Prompt templates**: Create pre-approved prompt structures that enforce brand voice when using AI tools
- **Tone filters**: Define rules for AI-generated content (e.g., "never use exclamation marks in error messages", "always use first person plural")
- **Human review gates**: Define which AI-generated content needs human review before publishing (high-stakes: always. Social replies: spot-check.)
- **Voice training examples**: Provide 10-20 example paragraphs of ideal brand voice for AI tools to reference
- **Anti-patterns for AI**: List specific phrases AI tends to generate that are OFF-brand (e.g., "I'd be happy to help!", "Absolutely!", "Great question!")

### Cross-Team Consistency

| Problem | Solution |
|---------|----------|
| Marketing sounds different from sales | Shared messaging doc + monthly alignment meeting |
| Support tickets feel robotic | Give CS team voice training + approved response templates in brand voice |
| Product copy feels technical | Product writers attend voice workshops; marketing reviews UI copy |
| International teams go off-brand | Document voice PRINCIPLES (not just words). Principles translate; vocabulary doesn't. |
| Freelancers / agencies miss the tone | Include voice guidelines in every creative brief. Provide 3-5 reference pieces as examples. |

### Voice Maintenance Cadence

| Timeframe | Action |
|-----------|--------|
| **Monthly** | Audit 5 recent pieces of content across different channels. On-brand? |
| **Quarterly** | Review and update word bank. Add new examples. Remove outdated ones. |
| **Biannually** | Full voice guidelines review. Still accurate? Still being used? Simplify if needed. |
| **Trigger-based** | Revisit immediately if: rebrand, new audience segment, major product launch, new market entry |

---

## Voice Bias by Company Type

Quick reference for default voice direction:

| Company Type | Voice Bias | Avoid |
|-------------|-----------|-------|
| **AI / ML startup** | Confident, clear, minimal jargon — explain what it does, not that it's "AI-powered" | Overhyped future-speak, hollow innovation claims |
| **Developer tool** | Direct, technical, respects intelligence — write for builders | Marketing fluff, vague benefit claims ("take your workflow to the next level") |
| **Consumer app** | Warm, human, relatable — write like a helpful friend | Cold technical language, corporate formality |
| **Enterprise SaaS** | Professional, authoritative, proof-led — back every claim | Casualness without substance, playful tone in wrong contexts |
| **Security product** | Calm, reassuring, precise — confidence without fear-mongering | Alarmist language, buzzword-heavy ("zero-trust AI-powered") |
| **Fintech** | Clear, trustworthy, simple — financial complexity made approachable | Cute/playful (erodes trust), vague promises |
| **Creative / design tool** | Inspiring, aesthetic, personality-forward | Generic "empowerment" language, corporate neutrality |
| **Agent / assistant** | Collaborative, personable, capable — "working with" not "powered by" | Robotic, impersonal, overly formal |
| **Infrastructure / DevOps** | Precise, reliable, developer-respecting — low marketing noise | Consumer-style excitement, excessive adjectives |

---

## Language Note

Conduct the entire process in the user's language. Messaging deliverables should be in the primary market language, with translations if multi-market. Taglines may need separate creative development per language — never just translate.

---

## Save Output

After presenting the messaging framework to the user, save it to the project folder:

1. Use the `Project Folder` path from the context block
2. Write the complete output to `{Project Folder}/03-voice.md` using the Write tool
3. File structure:
   ```
   ---
   project: {project-name}
   module: 03-voice
   date: {today's date}
   ---

   # Brand Voice & Messaging

   ## Mission / Vision / Values

   ## Value Proposition

   ## Brand Pillars

   ## Messaging Hierarchy
   [Tagline → One-liner → Elevator pitch → Boilerplate]

   ## Top Tagline Candidates
   [top 5 with scores]

   ## Voice Guidelines
   [traits, tone matrix, word bank]

   ## AI-Ready Voice Governance
   [prompt templates, anti-patterns]
   ```
4. Confirm: "✅ Saved to `{project-name}/03-voice.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **Voice & messaging defined!** The next step is **visual identity** — defining your color palette, typography, and logo direction so your brand looks as good as it sounds. Want to start `brand-visual` now?
