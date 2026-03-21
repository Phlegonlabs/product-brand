
# Brand Namer — Professional Naming Skill

> **Company Branding Workflow: Step ① of 5**
> `① Naming` → ② Positioning → ③ Voice & Messaging → ④ Visual Identity → ⑤ SEO Content
>
> **This is the starting point.** Name first, because everything downstream — domain, positioning, visual identity — follows the name. Once you have a name, move to `brand-positioning`.
> No prerequisites. After this skill: run `brand-positioning`.

A structured, three-phase naming system built from Lexicon Branding methodology (the firm behind Vercel, BlackBerry, Azure, Sonos, Windsurf), startup pattern analysis, phonetic heuristics, trademark logic, and domain strategy. This skill does not just generate random names — it produces names that are distinctive, memorable, scalable, pronounceable, searchable, and brandable over a 10-year horizon.

**The three phases follow Lexicon's proven sequence: Identify → Invent → Implement.**

Domain availability is handled in the Implement phase — it is a logistics problem, not a naming problem. The right name matters far more than the exact .com. As Lexicon's David Placek puts it: "A domain is just an area code." Domain conflicts can always be resolved through prefixes, alternative extensions, or purchases at modest cost. Never sacrifice a great name for a mediocre one because of domain anxiety.

## How This Skill Works

The naming process has **3 phases**. Always follow them in order. Do NOT skip Phase 1 — the Identify phase is the foundation of everything.

### Tool Usage Rule

**ALWAYS use the `ask_user_input` tool for all questions throughout this skill.** Every round of questions should be presented as interactive clickable choices, not plain text questions. This includes discovery interview, mode selection, style preferences, and any follow-up clarifications.

Rules for using `ask_user_input`:
- Group related questions into one tool call (max 3 questions per call)
- Use `single_select` for questions with one answer
- Use `multi_select` for questions where multiple options apply
- Use `rank_priorities` when the user needs to prioritize options
- Only fall back to prose questions when the question is truly open-ended (e.g., "describe your product") — and even then, pair it with selectable questions in the same round
- Keep option labels short (2-6 words each), add descriptions only when needed

---

## Phase 1: Identify

**Goal:** Build a complete brief before generating anything. Quantity of candidates means nothing without a sharp brief. This is the Diamond Framework in action — define what winning looks like before inventing anything.

### Round 1 — Project Basics

Present as one `ask_user_input` call with 3 questions:

**Q1** (single_select): "What are we naming?"
- Options: Company / Product / Feature / Agent or Assistant / Internal Codename

**Q2** (multi_select): "Target audience?"
- Options: Developers / Enterprise buyers / Consumers / Creators / Investors / Internal team

**Q3** (single_select): "Describe your product — what does it do?"
- Options: "I'll type it in the next message" / "Skip for now"

Then let the user type the description in their reply.

### Round 2 — The Diamond Framework

The Diamond Framework reframes naming from "find a word" to "define the desired customer experience." Four vertices:

- **Win:** What defines victory for this brand?
- **Have:** Current advantages to build from
- **Need:** What's still required to win
- **Say:** The one message the name must carry

Present as one `ask_user_input` call:

**Q1** (single_select): "What does winning look like for your brand?"
- Options: Category default/standard / Most trusted & secure / Fastest & best DX / Most innovative / Other (describe next message)

**Q2** (single_select): "What's your biggest current advantage?"
- Options: Strong tech / Unique approach / Team/founder reputation / First mover / Community / None yet

**Q3** (single_select): "What do you still need to win?"
- Options: Brand recognition / User trust / Developer adoption / Funding / Distribution / All of the above

Then ask in a follow-up `ask_user_input`:

**Q1** (single_select): "What one message should the name convey?"
- Options: Security & trust / Speed & efficiency / Innovation / Simplicity / Power & scale / Other

### Round 3 — Tone & Style

Present as one `ask_user_input` call:

**Q1** (multi_select): "Pick 1-2 style directions that fit:"
- Options: Short & Punchy / Technical / Professional / Playful / Abstract / Premium / Human / Mythic / Minimal / AI-Native

**Q2** (multi_select): "Which styles do you NOT want?"
- Options: Short & Punchy / Technical / Professional / Playful / Abstract / Premium / Human / Mythic / Minimal / AI-Native

### Round 4 — Constraints

Present as one `ask_user_input` call:

**Q1** (multi_select): "Any themes to AVOID?"
- Options: Avoid "AI/GPT" trend words / Avoid too-literal words (Pay, Wallet) / Avoid crypto/web3 vibes / Avoid anything too cute/playful / No restrictions

**Q2** (multi_select): "Any themes you're drawn to?"
- Options: Trust / Safety / Speed / Flow / Infrastructure / Innovation / No preference, surprise me

**Q3** (multi_select): "Domain preference? (these are guidelines, not hard gates)"
- Options: .com strongly preferred / .ai is fine / .io is fine / Any TLD is fine / I'll buy whatever domain is needed

Then ask as a follow-up prose question if needed: language requirements, length preference, any geographic or linguistic constraints.

---

## Phase 2: Invent

**Goal:** Generate a large, diverse candidate set from multiple cognitive perspectives before any filtering begins. Quantity enables quality — the first 50 names are almost always the most generic. The breakthroughs emerge after volume.

**Target: 60–100 candidates total.** Generate in three cognitive batches to maximize diversity.

> **Key principle from Lexicon:** Separate generation from evaluation entirely. No judgment during generation. Generate first, judge later. Teams that evaluate while generating produce smaller, safer, more forgettable candidate sets.

### The Three Cognitive Perspectives

Lexicon uses multiple teams with different briefs simultaneously. Claude replicates this by generating from three distinct viewpoints:

#### Perspective A — The Insider (25–35 names)
You know exactly what the product does, who it's for, and what winning looks like. Generate names that feel true to the product's core identity — semantic direction, audience, tone, and strategic positioning from the Identify phase all apply here.

- Pull from the Diamond Framework answers
- Apply the user's stated style preferences
- Use all 8 name types (prioritize Invented, Abstract, Compound)
- Apply letter psychology for brand fit

#### Perspective B — The Competitor (20–30 names)
Imagine a rival company just launched with a name designed to beat yours in the market. What name would make you most envious or threatened? What name would feel like they've already won?

- Ignore the user's brief entirely — think from competitive advantage
- Generate names that feel dominant, distinctive, and category-owning
- Ask: "If I saw this competitor's name in a headline, would I feel nervous?"
- These names are often the most distinctive — cognitive distance produces breakthroughs

#### Perspective C — The Adjacent Category (15–20 names)
Pretend you're naming something in a completely different industry — luxury goods, aerospace, film studio, fashion house, research institute. Then bring only the *feeling* of those names back to this product.

- This is how "Windsurf" emerged: from a team listing "flow" concepts, not surfing companies
- This is how "BlackBerry" emerged: from a team associating keyboard keys with berries
- Generate names that carry an emotional register, not a functional description
- These often become the most memorable candidates

### Name Types Reference (apply across all perspectives)

| # | Type | Description | Examples | Trademark Strength |
|---|------|-------------|----------|-------------------|
| 1 | **Invented** | Completely new word, no prior meaning | Kodak, Xerox, Figma, Spotify | Strongest (Fanciful) |
| 2 | **Abstract / Arbitrary** | Real word used in unrelated context | Stripe, Apple, Linear, Shell | Strong |
| 3 | **Metaphoric / Evocative** | Suggests qualities through image or mythology | Amazon, Nike, Palantir, Oracle | Strong |
| 4 | **Compound / Blended** | Two words merged or blended (1+1=3 effect) | Dropbox, Airbnb, Snapchat, BlackBerry | Moderate-Strong |
| 5 | **Descriptive** | Directly describes product/function | PayPal, Salesforce, Cloudflare | Weak |
| 6 | **Acronym / Initialism** | Letters from a phrase | IBM, BMW, SAP | Moderate |
| 7 | **Foreign Word** | Borrowed or adapted from another language | Samsung, Lego, Asana | Moderate-Strong |
| 8 | **Phonetic Shift** | Real word with intentional spelling change | Lyft, Tumblr, Fiverr | Moderate |

**Distribution target:** 70%+ should be Invented, Abstract, or Compound types. These have the strongest trademark position and highest ownability.

### Semantic Lenses (guide root selection)

| Lens | What It Names | Example Root Directions |
|------|---------------|------------------------|
| **Outcome** | Speed, control, clarity, growth | signal, momentum, lift, focus |
| **Mechanism** | How the product works | sync, relay, forge, stream |
| **Metaphor** | Symbolic story or object | beacon, prism, atlas, forge |
| **Identity** | Who the user becomes | builder, operator, maker |
| **Worldview** | Belief system or feeling | sovereign, exact, calm |
| **Category adjacency** | Nearby concepts, not literal | Stripe for payments, Plaid for fintech |

### Sound Psychology (apply to all candidates)

Sound shapes perception. Even invented words should feel right:

| Letter / Sound | Psychological Effect | Example Names |
|----------------|---------------------|---------------|
| **V** | Most alive and vibrant — chosen deliberately for Vercel | Vercel, Vimeo, Vivid |
| **B** | Stable, trustworthy, grounded | BlackBerry, Basecamp, Bench |
| **Z** | Distinctive, modern, energetic | Azure, Zoom, Zappos |
| **X** | Technical, futuristic, unknown | SpaceX, Xerox, Xero |
| **Hard consonants** (B, T, K, P) | Force, clarity, confidence | Stripe, Block, Snap |
| **Soft sounds** (S, L, M) | Flow, calm, friendliness | Loom, Sonos, Slack |
| **Open vowels** (O, A) | Warm, broad, human | Canva, Sonos |

### Generation Methods

| Method | How | Example |
|--------|-----|---------|
| **Root Mutation** | Compress/twist a concept root | measure→mezra, vector→vektro |
| **Portmanteau** | Blend two uncommon roots | signal+forge→sigforq, trust+velocity→truveq |
| **Consonant Cluster** | Add rare clusters to simple roots | flow→flokr, trust→truvk |
| **Vowel Swap** | Replace expected vowels with unusual ones | cover→covyr, relay→reluq |
| **Collision Compound** | Join semantically unrelated but emotionally aligned words | Wind+Surf, Black+Berry, Power+Book |
| **Classical Roots** | Greek/Latin roots create technical abstraction | lumen, nexus, vertex, axis |
| **Cross-Language Blend** | Mix roots from 2+ languages | Latin lux + Japanese ki→lukzai |
| **Real-Word Theft** | Use a real word from the wrong category | Stripe, Notion, Linear, Ramp |

### Presenting the Candidate Set

After generating all 60–100 candidates across three perspectives, present them organized by perspective with brief notes on the root/feeling behind each cluster. Do NOT score or filter yet — present the full set.

Then ask:

**`ask_user_input` (multi_select):** "Which of these feel like they're in the right territory? Select as many as feel interesting."

If the user selects 10+, proceed to Phase 3.
If the user selects fewer than 5, discuss what's missing and generate another round of 20-30 with adjusted direction.

---

## Phase 3: Implement

**Goal:** Take the user's selections through screening, scoring, domain logistics, conflict checking, and final recommendation. This is where the name becomes a brand asset.

### Step 1: First-Pass Filter

From the user's selected candidates, remove names that fail any hard rule:

**Hard Rules (any violation eliminates the name):**
1. Cannot be pronounced correctly on first attempt
2. Cannot be spelled after hearing it once
3. Obvious same-category company conflict (same name, same space)
4. Severe negative meaning in any target market language
5. Too descriptive to scale beyond one narrow feature

**Soft Rules (lower priority, not automatic elimination):**
- .com unavailable at standard pricing
- Slightly longer than ideal
- More abstract than the team is used to
- Not instantly loved on first read (this is often a *good* sign)

Present the surviving names after filtering.

### Step 2: Score Survivors

Score each surviving candidate (1–5 per category, max 50):

| Category | Question |
|----------|----------|
| **Memorability** | Will people remember it after one exposure? |
| **Pronounceability** | Can most users say it correctly? |
| **Spellability** | Can users spell it after hearing it? |
| **Distinctiveness** | Does it stand apart from same-category brands? |
| **Brand Fit** | Does it feel right for this product and audience? |
| **Scalability** | Will it still work after expansion or pivot? |
| **Searchability** | Can it rank and be found without noise? |
| **Trademark Strength** | Is it likely ownable (not descriptive)? |
| **International Safety** | Does it travel well across markets? |
| **Phonetic Quality** | Does the sound carry the right psychological register? |

**Thresholds:**
- 40+ = Strong shortlist candidate
- 32–39 = Review manually
- <32 = Likely too weak

### The 10 Core Tests (apply to top candidates)

1. **Cocktail Party Test**: Heard once in noise, can you repeat it?
2. **Phone Test**: Can it be spelled without explanation?
3. **Investor Test**: Does it sound credible to serious buyers?
4. **T-Shirt Test**: Would the team proudly wear it?
5. **Google Test**: Is it searchable without noise?
6. **Longevity Test**: Does it survive a 10-year company arc?
7. **Polarization Test**: Does it create energy, not indifference?
8. **Competitor Test**: If a rival launched with this name, would you feel envious?
9. **International Test**: Does it avoid cross-language problems?
10. **Trademark Test**: Is it more defensible than descriptive?

> **Placek's Discomfort Principle:** If the whole team immediately loves a name, it's probably too safe. Great names — Sonos ("not entertainment enough"), Azure ("dumb"), BlackBerry ("crazy") — were rejected or polarizing at first. Polarization is a signal of strength, not a reason to retreat.

### Step 3: Conflict Screening

For each of the **top 5 scored names**, use web search to check:
- `"[name]" + [industry keywords]` — existing companies in same space
- `"[name]" startup` or `"[name]" app` — early-stage conflicts
- `"[name]" trademark` — registered marks

Flag results as:
- 🟢 Clean — no meaningful conflicts found
- 🟡 Minor — same name exists but in a different industry (restaurant, etc.)
- 🔴 Blocker — same name in same or adjacent category

Search for social handle conflicts: X (Twitter), LinkedIn, GitHub, Product Hunt.

If a target-language market is specified, check for profanity, negative connotations, or awkward sound-alikes.

### Step 4: Domain Strategy

Domain is a logistics problem. Present options clearly — do not eliminate names based on domain availability.

For each shortlisted name, check and present:

```
=== Domain Situation: [name] ===

| Domain          | Status | Notes                        |
|-----------------|--------|------------------------------|
| [name].com      | ✅/❌   | Available / Registered       |
| [name].ai       | ✅/❌   | Available / Registered       |
| [name].io       | ✅/❌   | Available / Registered       |
| get[name].com   | ✅/❌   | Variant option               |
| use[name].com   | ✅/❌   | Variant option               |
```

**Domain resolution options (present all that apply):**
- **Available at standard price** → Register on Cloudflare at-cost
- **Taken — .ai/.io available** → Use alternate TLD (entirely normal for modern startups)
- **Taken — variant available** → `get[name].com` or `use[name].com` are legitimate launch options
- **Taken — worth buying** → For a truly great name, $5K–$30K domain purchase is rational; the name compounds in value over decades
- **Taken — check expiry** → Some domains are registered but unused; check WHOIS for expiry

Use RDAP to verify availability (no API key required):
```bash
# HTTP 404 = available, HTTP 200 = taken
curl -s -o /dev/null -w "%{http_code}" "https://rdap.org/domain/{name}.{tld}"
```

### Step 5: Final Recommendation

Present the **top 3 names** with:

| Field | Details |
|-------|---------|
| **Name** | The winning name |
| **Score** | Full breakdown from Step 2 |
| **Domain Path** | Best available domain option and resolution strategy |
| **Conflicts** | Results from Step 3 |
| **Brand Rationale** | Why this name works — roots, sound psychology, strategic fit |
| **Next Steps** | Secure domain → trademark counsel → team feedback → 48-hour rest test |

**48-hour rest test:** Ask the team to sit with the top name for two days before deciding. Great names become more believable with repetition, not less. If a name still feels right after 48 hours of repeated exposure, it's strong.

If conflict screening eliminates a finalist, pull up the next scored candidate.

---

## Appendix: Domain Tools & Pricing Reference

### Domain Search Tools

**Availability Check: RDAP**
```bash
# HTTP 404 = available, HTTP 200 = taken
curl -s -o /dev/null -w "%{http_code}" "https://rdap.org/domain/example.com"
```
Free, no API key required, covers all target TLDs (.com .ai .io .co .dev .xyz .sh .app .tech).

**Registration: Cloudflare Registrar (preferred)**
At-cost pricing, no markup, free WHOIS privacy + DNSSEC.
Go to `dash.cloudflare.com/domains` once a domain is confirmed available.

**Deep Verification (use for final shortlist):**

| Tool | URL | Why Use It |
|------|-----|-----------|
| **WHOIS Lookup** | whois.com/whois | See who owns a taken domain; check expiry |
| **ICANN WHOIS** | lookup.icann.org | Official source; most accurate |
| **Wayback Machine** | web.archive.org | Check domain history; brand contamination risk |

**Premium Domain Marketplaces:**

| Marketplace | URL | Notes |
|-------------|-----|-------|
| **Sedo** | sedo.com | Largest domain marketplace; auction + fixed price |
| **Dan.com** | dan.com | Simple buy/lease; installment plans |
| **Afternic** | afternic.com | GoDaddy's marketplace; huge inventory |
| **BrandBucket** | brandbucket.com | Curated premium names $1K–$50K; includes logo |

### Cloudflare At-Cost Pricing Reference

| TLD | Price | Notes |
|-----|-------|-------|
| .com | ~$10.11/yr | Standard; strongest trust signal |
| .ai | ~$18.85/yr (2yr min) | Much cheaper than $50–90 elsewhere |
| .io | ~$33.98/yr | Stable; common for dev tools |
| .co | ~$11.69/yr | Solid fallback |
| .dev | ~$12.00/yr | Forces HTTPS; strong dev signal |
| .xyz | ~$10.00/yr | Modern; no bait pricing on Cloudflare |
| .sh | ~$5–10/yr | Short; dev-friendly |
| .app | ~$14.00/yr | Forces HTTPS; consumer/mobile |
| .tech | ~$4.47/yr | Budget-friendly tech signal |

⚠️ Prices may change — verify at dash.cloudflare.com.

### TLD Priority Reference

| Priority | TLD | Best For |
|----------|-----|----------|
| 🥇 Tier 1 | **.com** | Universal default, strongest trust |
| 🥇 Tier 1 | **.ai** | AI / ML companies |
| 🥈 Tier 2 | **.io** | Developer tools |
| 🥈 Tier 2 | **.co** | Short fallback |
| 🥈 Tier 2 | **.dev** | Developer-facing |
| 🥈 Tier 2 | **.xyz** | Modern / experimental |
| 🥉 Tier 3 | **.app** | Consumer / mobile |
| 🥉 Tier 3 | **.so** | Short, modern |
| 🥉 Tier 3 | **.tech** | Technology companies |

**Fallback Domain Patterns:**
`get[name].com` · `use[name].com` · `try[name].com` · `[name]hq.com` · `hey[name].com` · `with[name].com` · `[name]labs.com` · `[name]app.com` · `[name]ai.com`

---

## Anti-Patterns to Flag

Always warn the user if candidates fall into these traps:

| Anti-Pattern | Why It's Bad |
|-------------|-------------|
| Too generic | Nothing to own (e.g., Smart, Flow, Data) |
| Too descriptive | Weak trademark, boxed-in future (e.g., FormBuilder) |
| Too trendy | Ages badly (e.g., GPT-something) |
| Too clever | Needs explanation (heavy puns) |
| Too long | Hard to brand (e.g., IntelligentWorkflowSystems) |
| Hard to say | Fails phone test |
| Hard to spell | Friction in sharing |
| Hyphenated | Feels cheap |
| Geographically boxed | Limits expansion |
| Domain anxiety name | Mediocre name chosen only because the .com was available |

---

## Expert Principles

- **Placek's Discomfort Principle**: Great names often feel slightly wrong at first — that's unfamiliarity, not badness. Sonos, Azure, BlackBerry were all initially rejected.
- **The Polarization Principle**: Mild disagreement is healthy. Flat indifference is a warning sign.
- **The 1+1=3 Compound Principle**: The best compounds (BlackBerry, Windsurf, PowerBook) create a richer story than either root alone.
- **The Competitor Envy Principle**: If your competitor launched with it and you'd feel jealous, it's strong.
- **The 1,000 Candidate Rule**: First 50 names are almost always the most generic. Quality emerges after volume.
- **The Domain is an Area Code Principle**: Never sacrifice a great name because of domain availability. The right name compounds in value for decades. A domain conflict is a one-time logistics problem.
- **Trust Before Cleverness**: The name should inspire trust and imagination, not just be clever.

---

## Naming Bias by Company Type

| Company Type | Best Name Bias |
|-------------|----------------|
| AI / ML startup | Invented, abstract, evocative |
| Developer tool | Abstract, technical, compound |
| Consumer app | Invented, playful, warm |
| Enterprise SaaS | Professional, abstract, stable |
| Security product | Hard consonants, mythic, trustworthy |
| Fintech | Short, credible, precise |
| Creative tool | Abstract, soft, elegant |
| Agent / assistant | Human, warm, memorable |

---

## Language Note

This skill supports naming projects in any language context. When the user communicates in Chinese (Traditional or Simplified), conduct the entire process in Chinese. The naming candidates themselves should match the target market language — usually English for tech/startup names, but ask if the user also needs Chinese brand names (中文品牌名).

---

## Reference

For the complete methodology including all generation methods, sound symbolism tables, and detailed scoring rubrics, read: `references/NAMING_SYSTEM.md`

---

## Save Output

After presenting the final recommendation to the user, save the deliverables to the project folder:

1. Use the `Project Folder` path from the context block
2. Write the complete output to `{Project Folder}/01-naming.md` using the Write tool
3. File structure:
   ```
   ---
   project: {project-name}
   module: 01-naming
   date: {today's date}
   ---

   # Brand Naming

   ## Final Recommendation
   [top 3 names with scores, domain situation, conflicts, rationale]

   ## Full Candidate Set
   [all candidates by perspective]

   ## Scoring Summary
   [scoring table for shortlisted names]
   ```
4. Confirm: "✅ Saved to `{project-name}/01-naming.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **Name secured!** The next step in the branding workflow is **brand positioning** — defining how your brand is perceived in the market. This feeds into everything else: messaging, visuals, and content. Want to start `brand-positioning` now?
