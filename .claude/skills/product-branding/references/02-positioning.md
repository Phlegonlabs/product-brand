
# Brand Positioning — Strategy Skill

> **Company Branding Workflow: Step ② of 5**
> ① Naming → `② Positioning` → ③ Voice & Messaging → ④ Visual Identity → ⑤ SEO Content
>
> **Prerequisite**: Run `brand-naming` first — you need a confirmed name + domain before positioning.
> **What this step produces**: Positioning statement, value proposition, key differentiators, target customer profile, competitive map.
> **After this skill**: Run `brand-voice` to turn positioning into messaging.

A structured framework for defining how a brand is perceived in the market. This skill helps founders and teams go from "we do X" to "we own this space in the customer's mind."

### Tool Usage Rule

**ALWAYS use the `ask_user_input` tool for all questions throughout this skill.** Every round of questions should be presented as interactive clickable choices, not plain text questions.

Rules:
- Group related questions into one tool call (max 3 questions per call)
- Use `single_select` for questions with one answer
- Use `multi_select` for questions where multiple options apply
- Use `rank_priorities` when the user needs to prioritize
- Only fall back to prose questions when truly open-ended (e.g., "describe your product")
- Keep option labels short (2-6 words), add descriptions only when needed

---

## Phase 1: Discovery Interview

**If the user just completed `brand-naming`**: The Diamond Framework answers from naming (Win / Have / Need / Say) are direct positioning inputs — map them as follows and skip Round 1 entirely:

| Diamond Framework (from naming) | Positioning Use |
|----------------------------------|----------------|
| **Win** — "What does victory look like?" | → Feeds directly into aspirational positioning statement |
| **Have** — "Current advantages" | → Becomes your Key Differentiators list |
| **Need** — "What's still required" | → Identifies positioning gaps to address later |
| **Say** — "Core message the name must carry" | → The seed of your Value Proposition |

Ask the user to share their confirmed name, domain, and these four Diamond answers. Then jump straight to Round 2 (Competitive Landscape).

### Round 1 — The Basics

Present as one `ask_user_input` call:

**Q1** (single_select): "What stage are you at?"
- Options: Idea / MVP / Growth / Rebrand

**Q2** (multi_select): "Who is your primary audience?"
- Options: Developers / Enterprise buyers / Consumers / Creators / SMB owners / Internal teams

**Q3** (single_select): "Describe your product/service?"
- Options: "I'll type it next" / "Skip for now"

Then let user type their description + what problem they solve.

### Round 2 — Competitive Landscape

Present as one `ask_user_input` call:

**Q1** (single_select): "How crowded is your market?"
- Options: Very crowded (10+ competitors) / Moderately crowded (3-9) / Emerging (1-2 direct) / Creating a new category

**Q2** (multi_select): "What's your real advantage over competitors?"
- Options: Better technology / Better UX / Cheaper / Faster / More trusted / Better support / Niche focus / First mover

**Q3** (single_select): "Can you name your top 3 competitors?"
- Options: "Yes, I'll list them next" / "Not sure yet" / "No direct competitors"

### Round 3 — Aspiration

Present as one `ask_user_input` call:

**Q1** (single_select): "In 3 years, what do people say about your brand?"
- Options: "The standard in our category" / "The most innovative" / "The most trusted" / "The easiest to use" / "The one for serious professionals" / Other

**Q2** (multi_select): "Brands you admire (any industry)?"
- Options: Stripe / Apple / Linear / Notion / Airbnb / Nike / Vercel / Tesla / Other (type next)

**Q3** (multi_select): "Your brand should NOT feel like:"
- Options: Corporate / Cheap / Overly techy / Generic / Playful / Cold / Trendy

---

## Phase 2: Positioning Frameworks

Run the user's answers through these frameworks. Present results from at least 2.

### Framework 1: Arielle Jackson Positioning Statement

The most widely used startup positioning template (from Google/Square):

```
For [target customer]
who [statement of need or opportunity],
[product name] is a [product category]
that [statement of key benefit].
Unlike [competitive alternative],
our product [statement of primary differentiation].
```

Generate 2-3 variations with different emphasis.

### Framework 2: April Dunford's "Obviously Awesome" (5 Components)

| Component | Question |
|-----------|----------|
| **Competitive Alternatives** | What would customers use if you didn't exist? |
| **Unique Attributes** | What features/capabilities do you have that alternatives don't? |
| **Value** | What value do those unique attributes enable for customers? |
| **Target Customer** | Who cares most about that value? |
| **Market Category** | What context makes your value obvious? |

Work through each component with the user, then synthesize.

### Framework 3: Lexicon Diamond Framework

| Point | Question |
|-------|----------|
| **Win** | What does winning look like for us? |
| **Have** | What do we already have to win? |
| **Need** | What do we still need to win? |
| **Say** | What do we need to say to win? |

This surfaces gaps between ambition and reality.

### Framework 4: Positioning Map

Create a 2x2 positioning map plotting the brand against competitors on the two most relevant axes. Common axis pairs:

- Price vs Quality
- Simple vs Feature-rich
- Consumer vs Enterprise
- Speed vs Reliability
- Innovative vs Established

Ask the user which dimensions matter most, then plot.

---

## Phase 3: Synthesis & Output

### Deliver These Artifacts

1. **Positioning Statement** — 1-2 sentences, using Framework 1 or a custom format
2. **Value Proposition** — One sentence: what unique value you deliver
3. **Key Differentiators** — Top 3 reasons you're different from alternatives
4. **Target Customer Profile** — Specific description of who this is for
5. **Category Definition** — Where you sit (or the new category you're creating)
6. **Positioning Map** — Visual 2x2 showing competitive landscape
7. **Elevator Pitch** — 30-second spoken version

### Quality Checks

- Does the positioning pass the "so what?" test? (Would a customer care?)
- Is it specific enough to exclude non-target customers?
- Does it hold up against each named competitor?
- Can a new employee understand it in 2 minutes?
- Would it still be true after a product pivot?

---

## Expert Principles

- **Positioning is not tagline writing.** Positioning is the strategic foundation; taglines are creative execution of it.
- **You can't position for everyone.** If your positioning doesn't exclude anyone, it doesn't attract anyone either.
- **Category is context.** Choosing the right category makes your value obvious; choosing wrong makes you invisible.
- **Positioning should feel uncomfortable.** If it's comfortable, it's probably too generic (Placek's Discomfort Principle).
- **Test with outsiders.** Internal teams are the worst judges of positioning. Test with people who've never heard of you.
- **Position ≠ Aspiration.** Your positioning is how the market actually perceives you, not where you wish to be. Know the gap.
- **Benefits need beliefs.** A benefit alone isn't positioning. The best positioning resolves an inherent tension or captures a unique insight about the customer's life.
- **Positioning is a living document.** Review quarterly. Markets shift, competitors move, customer needs evolve. Stale positioning is invisible positioning.
- **Collective ownership wins.** Positioning developed in a silo and "announced" to the org will fail. Involve sales, product, and CS teams in the process.

---

## Common Positioning Mistakes

| Mistake | Why It Hurts | Fix |
|---------|-------------|-----|
| **Too generic / safe** | "Innovative, trusted, quality" — same as every competitor. Invisible. | Find the one thing ONLY you can claim. If a competitor could use the same words, start over. |
| **Trying to appeal to everyone** | Dilutes your message. Nobody feels like it's for them. | Pick your best-fit customer segment. Serve them deeply. Let others self-select. |
| **Confusing messaging with positioning** | Taglines and copy are output, not strategy. | Do the strategy work first. Great messaging flows naturally from clear positioning. |
| **Skipping research** | Assumptions ≠ reality. You'll build on a false foundation. | Talk to customers, study competitors, survey the market BEFORE writing a positioning statement. |
| **Copying competitors** | Following the leader makes you a follower, not an alternative. | Study competitors to find gaps, not to imitate. Position against them, not beside them. |
| **Picking the wrong category** | Wrong context = wrong expectations = wrong competitors. | Ask: "What would customers compare us to if we didn't exist?" That's your real category. |
| **Not testing** | Sounds great internally, confuses customers externally. | A/B test positioning messages. Run focus groups. Watch for hesitation, confusion, or indifference. |
| **Making promises you can't keep** | Erodes trust fast. Positioning is a promise. | Only claim what you can deliver TODAY. Aspirational positioning without substance backfires. |
| **Letting it go stale** | Market shifts, competitor moves, customer needs evolve. Yesterday's positioning becomes today's irrelevance. | Revisit positioning every 6-12 months. Refresh when market conditions change significantly. |
| **Developing in a silo** | Sales, product, CS teams don't buy in. Execution fails. | Include cross-functional input. Positioning should feel like collective truth, not a marketing decree. |

---

## Positioning Validation Checklist

Before finalizing, run the positioning through these tests:

| Test | Question | Pass Criteria |
|------|----------|---------------|
| **Differentiation** | Is this meaningfully different from top 3 competitors? | Can't be copy-pasted onto a competitor's website |
| **Relevance** | Does the target customer actually care about this difference? | Based on customer research, not assumption |
| **Believability** | Can we credibly deliver on this claim? | Have proof points (features, data, testimonials) |
| **Defensibility** | Can competitors easily copy this position? | Based on structural advantage, not just messaging |
| **Durability** | Will this still be true after a product pivot or expansion? | Not tied to a single feature or trend |
| **Clarity** | Can a stranger understand it in one read? | No jargon, no insider knowledge needed |
| **Actionability** | Can teams use this to make decisions? | Product, marketing, sales can all apply it |

---

## Positioning Maintenance Cadence

| Timeframe | Action |
|-----------|--------|
| **Monthly** | Check: are marketing materials still aligned with positioning? |
| **Quarterly** | Review competitive landscape. Any new entrants or repositioning by competitors? |
| **Biannually** | Customer pulse check: does our positioning still resonate? Survey or interview 5-10 customers. |
| **Annually** | Full positioning review. Update if market has shifted significantly. |
| **Trigger-based** | Revisit immediately if: new funding round, major pivot, new competitor enters, target market shifts |

---

## Positioning Bias by Company Type

Quick reference for default positioning emphasis:

| Company Type | Best Positioning Lens | Avoid |
|-------------|----------------------|-------|
| **AI / ML startup** | Outcome + mechanism ("what it does, not that it's AI") | Positioning as "AI-powered" — everyone says this |
| **Developer tool** | Identity ("who the developer becomes") + mechanism | Over-promising on vague innovation claims |
| **Consumer app** | Outcome + emotion ("how it makes you feel") | Technical mechanism (users don't care) |
| **Enterprise SaaS** | Trust + outcome + ROI | Playful or abstract claims without proof |
| **Security product** | Trust + category definition ("what bad outcome you prevent") | Innovation-first framing (security buyers want reliability) |
| **Fintech** | Outcome + trust + simplicity ("it just works") | Disruption framing (erodes institutional trust) |
| **Creative / design tool** | Identity ("who you become") + aesthetic quality | Pure technical feature lists |
| **Agent / assistant** | Outcome + relationship framing ("working with" not "using") | Overpromising on autonomy |
| **Infrastructure / DevOps** | Reliability + mechanism + category definition | Consumer-style emotional framing |

---

## Language Note

Conduct the entire process in the user's language. Positioning statements should be written in the primary market language, with translations if multi-market.

---

## Save Output

After presenting the deliverables to the user, save them to the project folder:

1. Use the `Project Folder` path from the context block
2. Write the complete output to `{Project Folder}/02-positioning.md` using the Write tool
3. File structure:
   ```
   ---
   project: {project-name}
   module: 02-positioning
   date: {today's date}
   ---

   # Brand Positioning

   ## Positioning Statement
   [Arielle Jackson / Dunford format]

   ## Value Proposition
   [one sentence]

   ## Key Differentiators
   [list]

   ## Target Customer Profile
   [description]

   ## Category Definition
   [how the brand defines its market]

   ## Positioning Map
   [2x2 description or ASCII diagram]

   ## Elevator Pitch
   [30-second version]
   ```
4. Confirm: "✅ Saved to `{project-name}/02-positioning.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **Positioning locked in!** The next step is **brand voice & messaging** — turning your positioning into taglines, elevator pitches, and voice guidelines that your team can use everywhere. Want to start `brand-voice` now?
