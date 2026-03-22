
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

## Phase 1: Identify

**Goal:** Build a complete brief before generating anything. Quantity of candidates means nothing without a sharp brief. This is the Diamond Framework in action — define what winning looks like before inventing anything.

### Round 1 — Project Basics

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "What are we naming?"
- header: "Target"
- multiSelect: false
- options:
  - { label: "Company", description: "The overall brand / organization name" }
  - { label: "Product", description: "A specific product or app" }
  - { label: "Agent / Assistant", description: "An AI agent, bot, or assistant" }
  - { label: "Feature / Codename", description: "A product feature or internal project codename" }

**Q2:**
- question: "Who is the primary target audience?"
- header: "Audience"
- multiSelect: true
- options:
  - { label: "Developers", description: "Engineers, DevOps, technical builders" }
  - { label: "Enterprise buyers", description: "B2B decision-makers, procurement, CTOs" }
  - { label: "Consumers", description: "General public, end users, individuals" }
  - { label: "Creators", description: "Designers, makers, indie builders — also Investors / internal teams via 'Other'" }

**Q3:**
- question: "Describe your product — what does it do?"
- header: "Description"
- multiSelect: false
- options:
  - { label: "I'll type it next", description: "I'll describe the product in my next message" }
  - { label: "Skip for now", description: "Proceed without a description — can add later" }

Then let the user type the description in their reply.

### Round 2 — The Diamond Framework

The Diamond Framework reframes naming from "find a word" to "define the desired customer experience." Four vertices:

- **Win:** What defines victory for this brand?
- **Have:** Current advantages to build from
- **Need:** What's still required to win
- **Say:** The one message the name must carry

Call `AskUserQuestion` with 3 questions (Diamond Framework — Win / Have / Need):

**Q1:**
- question: "What does winning look like for your brand? (Diamond: Win)"
- header: "Win"
- multiSelect: false
- options:
  - { label: "Category standard", description: "Become the default everyone references — 'the Stripe of X'" }
  - { label: "Most trusted", description: "Recognized as the most secure and reliable option" }
  - { label: "Best developer experience", description: "Fastest, most elegant, beloved by technical builders" }
  - { label: "Most innovative", description: "Leading the category with new ideas and approaches" }

**Q2:**
- question: "What's your biggest current advantage? (Diamond: Have)"
- header: "Have"
- multiSelect: false
- options:
  - { label: "Strong technology", description: "Superior technical solution that competitors can't match" }
  - { label: "Unique approach", description: "Different way of solving the problem — methodology or model" }
  - { label: "Community / traction", description: "Existing users, community, or first-mover status" }
  - { label: "None yet", description: "Early stage — also: team/founder reputation via 'Other'" }

**Q3:**
- question: "What do you still need to win? (Diamond: Need)"
- header: "Need"
- multiSelect: false
- options:
  - { label: "Brand recognition", description: "People need to know we exist" }
  - { label: "Developer adoption", description: "Need technical users to build with us" }
  - { label: "Enterprise trust", description: "Need credibility with serious buyers" }
  - { label: "Distribution", description: "Need better reach, partnerships, or channels" }

Then follow up with `AskUserQuestion` for the Say vertex:

**Q1:**
- question: "What one message should the name convey? (Diamond: Say)"
- header: "Say"
- multiSelect: false
- options:
  - { label: "Security & trust", description: "The name should feel safe, credible, reliable" }
  - { label: "Speed & efficiency", description: "Fast, lightweight, no friction" }
  - { label: "Innovation", description: "Forward-looking, cutting-edge, first-of-its-kind" }
  - { label: "Simplicity & clarity", description: "Easy, calm, minimal — or 'Power & scale' via 'Other'" }

### Round 3 — Tone & Style

Call `AskUserQuestion` with 2 questions:

**Q1:**
- question: "Pick 1-2 style directions that fit your brand:"
- header: "Style — want"
- multiSelect: true
- options:
  - { label: "Short & Punchy", description: "4-6 letters, hard consonants, instant recall (e.g., Stripe, Snap)" }
  - { label: "Abstract / Minimal", description: "Non-literal, clean, category-scalable (e.g., Linear, Notion)" }
  - { label: "Technical", description: "Precise, developer-native, system-like (e.g., Vercel, Twilio)" }
  - { label: "Human / Playful", description: "Warm, approachable, consumer-friendly — or Premium/Mythic via 'Other'" }

**Q2:**
- question: "Which styles do you NOT want?"
- header: "Style — avoid"
- multiSelect: true
- options:
  - { label: "Short & Punchy", description: "Avoid very short, hard-sounding names" }
  - { label: "Abstract / Minimal", description: "Avoid names that feel too vague or cold" }
  - { label: "Technical", description: "Avoid names that feel too nerdy or niche" }
  - { label: "Human / Playful", description: "Avoid names that feel too casual, cute, or consumer-focused" }

### Round 4 — Constraints

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Any themes to AVOID in the name?"
- header: "Avoid themes"
- multiSelect: true
- options:
  - { label: "AI/GPT trend words", description: "No 'AI', 'GPT', 'neural', 'smart' — dates badly" }
  - { label: "Too-literal words", description: "Avoid function-first names like Pay, Wallet, Send, Auth" }
  - { label: "Crypto/web3 vibes", description: "No chain, block, token, mint — even if unintentional" }
  - { label: "No restrictions", description: "Open to any direction — let the brief lead" }

**Q2:**
- question: "Any themes you're drawn to?"
- header: "Draw to"
- multiSelect: true
- options:
  - { label: "Trust & safety", description: "Names that feel secure, stable, reliable" }
  - { label: "Speed & flow", description: "Names that feel fast, smooth, effortless" }
  - { label: "Infrastructure", description: "Names that feel like solid, serious plumbing" }
  - { label: "No preference", description: "Surprise me — let the brief guide the direction" }

**Q3:**
- question: "Domain preference? (guideline, not a gate)"
- header: "Domain"
- multiSelect: true
- options:
  - { label: ".com preferred", description: "Strongest trust signal — will work hard to get it" }
  - { label: ".ai is fine", description: "Good for AI-native companies, modern and accepted" }
  - { label: ".io is fine", description: "Developer-familiar, common for tools and platforms" }
  - { label: "Any TLD works", description: "Including .co, .dev, .xyz — the name matters more" }

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
| 9 | **Morpheme-Engineered** | Sub-word meaning units extracted from concept words and assembled into a new word — Lexicon's core technique | Vercel, Verizon, Accenture, Pinterest | Strongest (Fanciful) |
| 10 | **Eponymous / Founder** | Named after a founder or person | Tesla, Disney, Dell, Dyson, Bloomberg | Moderate |
| 11 | **Personification** | A human first name given to a non-human entity | Alexa, Siri, Oscar, Alice, Ada | Strong |
| 12 | **Onomatopoeia** | A word that mimics a sound or action | Zoom, Ping, Snap, Twitter, Bing | Moderate-Strong |
| 13 | **Truncation / Clipping** | Clipped from a longer word or phrase | Intel, Cisco, FedEx, Amex | Moderate |
| 14 | **Alphanumeric** | Contains numerals as part of the name | 3M, 1Password, 7-Eleven, 23andMe | Moderate |

**Distribution target:** 70%+ should be Invented, Abstract, Compound, or **Morpheme-Engineered** types. These have the strongest trademark position and highest ownability.

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

Sound shapes perception. Every letter class below is equally viable — choose based on the emotional register the product needs, not personal preference. No single letter or cluster is inherently superior.

| Letter / Sound | Emotional Register | Best For | Example Names |
|----------------|-------------------|----------|---------------|
| **S, Sl, Str** | Flow, speed, smoothness | Tools, productivity, dev | Stripe, Slack, Stream, Sonos |
| **R** | Reliable, grounded, rolling momentum | Infrastructure, B2B, fintech | Relay, Ramp, Render, Ripple |
| **L** | Light, elegant, calm clarity | Creative tools, consumer, design | Linear, Loom, Lark, Lattice |
| **K, hard C** | Sharp, decisive, confident | Security, performance, enterprise | Clerk, Cribl, Kafka, Okta |
| **T** | Precise, technical, direct | Dev tools, data, APIs | Twilio, Turso, Tinybird |
| **P** | Purposeful, clear, polished | Consumer, SaaS, productivity | Plex, Plaid, Pulumi, Postman |
| **N** | Neutral, modern, approachable | Platforms, broad B2B | Notion, Netlify, Neon, Novu |
| **F** | Fast, forward, confident | Speed-first products, finance | Fly, Forge, Fauna, Figma |
| **B** | Stable, trustworthy, grounded | Infrastructure, finance, security | BlackBerry, Basecamp, Brex |
| **V** | Vibrant, alive, kinetic | Agent, AI, dynamic platforms | Vercel, Vimeo, Vertex |
| **Z** | Distinctive, modern, energetic | Consumer, video, attention-grabbing | Zoom, Zappos, Zed |
| **X** | Futuristic, technical, unknown | Deep tech, research, frontier | Xero, Oxide, Phoenix |
| **Open vowels (O, A)** | Warm, broad, human | Consumer, global, horizontal | Canva, Notion, Asana, Okta |
| **Soft clusters (Gl, Fl, Sl)** | Light, vision, motion | Creative, design, visual tools | Glide, Flow, Slate |

**Diversity rules — starting letters:** No more than 2–3 names in the ~20 shortlist should share the same starting letter.

**Diversity rules — suffix families (CRITICAL):** Names cluster by suffix before they cluster by starting letter. Use the suffix family taxonomy below. **Hard cap: max 3 names per suffix family in the final ~20.** Target: at least 4 different suffix families represented.

| Suffix Family | Endings | Emotional Register | Real Brand Examples |
|---------------|---------|-------------------|---------------------|
| **X-family** | -ex, -ox, -ix, -ax, -vex, -vox, -nox | Technical, futuristic, hard | Krenox, Narvex |
| **Open Vowel** | -a, -ia, -io, -o, -ra, -va | Warm, global, approachable | Figma, Canva, Striva |
| **Latin/Classical** | -um, -em, -us, -is, -al | Authoritative, precise | Vectum, Nexus, Corlem |
| **Soft N** | -en, -on, -an, -ven, -von | Flowing, platform-like | Zolven, Notion, Lumen |
| **R-ending** | -er, -ar, -or, -ur | Grounded, active, agent-like | Norvar, Render, Linear |
| **Consonant Stop** | -ek, -ik, -el, -ol, -rl | Short, crisp, decisive | Slack, Strelv, Torvel |
| **Compound / Real Word** | two real morphemes joined | Narrative, warm, memorable | BlackBerry, Windsurf |

**Self-audit after generation:** After generating 60–100 candidates, tally the suffix family distribution across your strongest 20–30 picks. If any single family has more than 3 entries, replace the excess with new names from families with 0–1 entries. Do not shortlist until the distribution is balanced.

### Generation Methods

| Method | How | Example |
|--------|-----|---------|
| **Root Mutation** | Compress/twist a concept root | measure→mezura, vector→vektum, relay→relva |
| **Portmanteau** | Blend two uncommon roots | signal+forge→sigora, trust+velocity→trelva, flow+nexus→flonex |
| **Consonant Cluster** | Add rare clusters to simple roots | flow→flokr, trust→trelvis, core→corvix |
| **Vowel Swap** | Replace expected vowels with unusual ones | cover→covira, relay→relua, forge→forgal |
| **Collision Compound** | Join semantically unrelated but emotionally aligned words | Wind+Surf, Black+Berry, Power+Book |
| **Classical Roots** | Greek/Latin roots create technical abstraction | lumen, nexus, vertex, axis |
| **Cross-Language Blend** | Mix roots from 2+ languages | Latin lux + Japanese ki→lukzai |
| **Real-Word Theft** | Use a real word from the wrong category | Stripe, Notion, Linear, Ramp |
| **Morpheme Engineering** | Extract sub-word meaning units from concept words → combine into a new word that carries semantic DNA without being recognizable as either source | versatile+accelerate→Vercel, veritas+horizon→Verizon, accent+future→Accenture |
| **Syllable Splicing** | Extract specific syllables from words and reassemble | Spotify (spot+ify), Netflix (net+flix), Instagram (instant+telegram) |
| **Letter Subtraction** | Remove letters (usually vowels) from an existing word | Flickr, Tumblr, Grindr, Scribd |
| **Reduplication** | Repeat a syllable or sound pattern | TikTok, Lululemon, Bonbon, Murmur |
| **Alliterative Construction** | Build a name with repeating initial consonants | Coca-Cola, PayPal, Best Buy, Krispy Kreme |
| **Prefix / Suffix Grafting** | Attach systematic affixes to a root | Uber-, Shopify (-ify), Bitly (-ly), Calendly |
| **Truncation + Suffix** | Clip a word down to its root, then add a new ending | Accel(-a), Forgo(-io), Prism(-atic) |
| **Phonestheme Mining** | Use sound clusters that carry consistent psychological meaning across many words | gl- (light/vision): Glow, Gleam, Glint — sn- (quick/sharp): Snap, Swift — str- (force): Stripe, Strong |

> **Real-world naming patterns** (use as generation prompts alongside the methods above):
> 1. **Repurposed real word** — pick a word that metaphorically fits the outcome (Linear, Notion, Clerk, Render, Stripe)
> 2. **Morpheme compound** — fuse two meaning-rich roots (Shopify=shop+simplify, Vercel=versatile+excel, Supabase=supa+base)
> 3. **Classical/foreign root** — Latin, Greek, or foreign word with fitting meaning (Figma←Latin "fingere"=to shape, Prisma←Greek "to cut", Turso←Finnish mythology)
> 4. **Truncation** — shorten a real word to something new (Canva←canvas, Intel←integrated electronics, FedEx←Federal Express)
> 5. **Sound-first coinage** — invent a word optimized for phonetic impact, rationalize meaning later (Spotify←misheard word, Twilio←"two-way")
> 6. **Deadline default** — brainstorm freely, then set a hard cutoff and commit to the best option in hand (Stripe: if nothing better by Dec 20, default to "Stripe")
> 7. **Placeholder promotion** — start with a working name; let traction decide (Slack started as a codename, Supabase started as a placeholder joke)

### Morpheme Engineering — Lexicon's Core Technique

This is the method behind Vercel, Verizon, Accenture, and Pinterest. Unlike portmanteau (which blends two recognizable whole words), morpheme engineering extracts sub-word meaning units and assembles them into a word that carries semantic DNA without being recognizable as either source word. The result sounds natural and linguistic — not invented — yet is completely ownable.

**4-Step Process:**

**Step 1 — Concept Harvest.** List 15–20 words that capture what the brand should evoke.
> For Vercel: *versatile, velocity, accelerate, excel, vertical, universal, veritas*

**Step 2 — Morpheme Extraction.** Break each word into its meaningful fragments.
```
versatile  → ver- | -sat- | -ile
accelerate → ac-  | -cel- | -erate
excel      → ex-  | -cel
veritas    → ver- | -itas
universal  → uni- | -ver- | -sal
```

**Step 3 — Combination Matrix.** Test fragment pairings systematically. Look for combinations that:
- Sound like a real word but aren't
- Carry the emotional weight of the source roots
- Pass the phone test on first attempt

```
ver + cel  → Vercel  ✓
ver + sat  → Versat
ac  + cel  → Accel   (too literal)
ex  + ile  → Exile   (exists — skip)
uni + vel  → Univel
```

**Step 4 — Phonetic Validation.** Run top candidates through:
- Pronounceable on first attempt?
- Sounds like a real word but isn't?
- Right psychological register? (apply Sound Psychology table)
- Passes phone test — can be spelled after hearing once?

**Why this method produces the strongest names:**
- Highest trademark strength — fanciful category, no prior meaning
- Carries layered semantic meaning that rewards discovery
- Sounds natural and linguistic, not random or invented
- Impossible to reverse-engineer the source words — maximum ownability

### Suffix Audit (run before shortlisting)

After generating all 60–100 candidates, tally the suffix family distribution across your 20–30 strongest picks using the table above. Example audit:

```
X-family (-ex/-ox/-vox/-nox):  8 names  ← over limit, must reduce to 3
Open Vowel (-a/-ia/-o):         2 names
Latin/Classical (-um/-us/-al):  1 name
Soft N (-en/-on/-ven):          4 names  ← over limit, reduce to 3
R-ending (-ar/-or/-er):         1 name
Consonant Stop (-ek/-el):       1 name
Compound/Real Word:             0 names  ← underrepresented, add 1-2
```

Replace excess names with new names from underrepresented families. Do NOT proceed to conflict pre-screening until at least 4 suffix families are represented and no family exceeds 3.

### Presenting the Candidate Set

After generating all 60–100 candidates across three perspectives, run a **Conflict Pre-Screen** to produce a clean shortlist — before showing the user anything.

**Pre-Screen — efficiency rule: run searches in parallel**
1. Identify the 20–30 strongest-looking candidates from all three perspectives
2. Run 1 WebSearch per name (bare name only, no qualifiers) — use parallel Agent tool calls in batches of 4–6 names each to maximize speed
3. Eliminate any 🔴 blocker (existing company, consumer brand, famous person, geographic name)
4. Target output: **~20 surviving candidates**

**IMPORTANT: Do NOT show the user anything during pre-screening. No intermediate updates, no "checking..." messages.** Run all searches silently.

**Domain Pre-Check — run in the same silent pass as conflict pre-screening:**

For each of the ~20 surviving candidates, run WebSearch to determine domain availability:
- `"[name].com"` — if an active website appears, .com is TAKEN
- `"[name].ai"` — if an active website appears, .ai is TAKEN
- `"[name].io"` — if an active website appears, .io is TAKEN

Interpret results:
- Active company website in results → TAKEN
- Domain parking / "for sale" page → TAKEN (but may be purchasable)
- No website results / domain listed as available → Likely AVAILABLE
- Inconclusive → Note for user manual verification on Cloudflare; score as 2

**Do NOT run bash, Python, curl, WHOIS, or RDAP commands.** WebSearch only. If uncertain, ask the user to verify at `dash.cloudflare.com/domains`.

Use domain results to apply the real Domain Availability score (1–5 rubric) before scoring.

**Score all ~20 surviving candidates immediately** on the 11-dimension matrix (1–5 per dimension, max 55). Use the conflict pre-screen results for Distinctiveness, Searchability, and Trademark Strength. Use the domain pre-check results for Domain Availability (real score, not provisional).

**Present the full scoring matrix as the first output to the user:**

| Name | Perspective | Mem | Pro | Spl | Dis | Fit | Sca | Sea | TM | Int | Pho | Dom | **Total** |
|------|-------------|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----------|
| Forvel | A | 4 | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 4 | 4 | 4 | **52** |
| Orbvel | C | 4 | 4 | 4 | 4 | 4 | 5 | 4 | 5 | 4 | 4 | 2 | **44** |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

Column key: Mem=Memorability, Pro=Pronounceability, Spl=Spellability, Dis=Distinctiveness, Fit=Brand Fit, Sca=Scalability, Sea=Searchability, TM=Trademark Strength, Int=International Safety, Pho=Phonetic Quality, Dom=Domain Availability (real)

Sort by Total descending. Include all ~20 names — don't pre-select for the user.

**Then automatically select the top 5 registrable candidates:**

From the scored ~20 candidates, auto-select the top 5 by Total score where:
1. Conflict status is not 🔴 (already eliminated in pre-screen)
2. Domain Availability score >= 3 (meaning at least .ai-only or .io+.co available)

If fewer than 5 meet Domain >= 3, relax to Domain >= 2 to fill remaining slots.

After the matrix, output:

> 根据可注册性（无冲突 + 域名可用）和总分，以下 5 个候选名进入深度审查：

| Name | Total /55 | Domain Status | Brand Logic |
|------|-----------|---------------|-------------|
| [Name A] | XX | .ai/.io available | [one-line] |
| [Name B] | XX | .com available | [one-line] |
| ... | ... | ... | ... |

Proceed to Phase 3 with these 5 names. Do NOT ask the user to choose — present all 5 as equal candidates.

> **Note:** If the user finds none of these appealing after reviewing, generate another batch of 20–30 names with adjusted direction and repeat the pre-screen.

---

## Phase 3: Implement

**Goal:** Take the top 5 registrable candidates through full evidence — conflict deep-dive, domain verification, and final scoring — then present all 5 as equal candidates for the user to consider.

The top 5 names were automatically selected in Phase 2 based on registrability (clean conflicts + domain availability) and total score. Proceed to conflict screening and domain verification for all 5.

### Output Rule

Phase 3 outputs in two rounds. Do not merge them.

**Round 1 — Name Overview Table (output immediately, before any searching):**

Present a clean table confirming which names are entering Phase 3:

| 名字 | 视角 | 品牌逻辑 |
|------|------|---------|
| [Name A] | A / B / C | [one-line] |
| [Name B] | ... | ... |

**Round 2 — Detailed Evidence per Name (output after all searches complete):**

For each name that survives conflict screening, present a structured evidence block:

```
### [Name]

**冲突检验：** 🟢/🟡/🔴
- 搜索 1 "[Name]"：[摘要 — 有/无冲突，来源]
- 搜索 2 "[Name]" company/brand：[摘要]
- 判定：[Clean / Minor conflict with X (different industry) / Blocker — X in same space]

**域名可用性：**
| TLD | 状态 |
|-----|------|
| .com | ✅ Available / ❌ Taken |
| .ai  | ✅ / ❌ |
| .io  | ✅ / ❌ |
| .co  | ✅ / ❌ |

**评分（/55）：**
| 维度 | 分 | 理由 |
|------|----|----|
| Memorability | 4 | [why] |
| Pronounceability | 5 | [why] |
| ... | ... | ... |
| Domain Availability | 4 | .ai/.io/.co 可用，.com 监控中 |
| **Total** | **XX** | |
```

After all evidence blocks are presented, output the Scoring Matrix (all names × all dimensions) and Top 3 recommendation.

---

### Step 1: Conflict Screening

Run conflict checks on ALL first-pass survivors **before scoring**. This saves time and prevents scoring names that will be eliminated.

**Efficiency rule: run all conflict searches in parallel.** Use multiple WebSearch calls in a single message (or Agent tool batches) — never search one name at a time sequentially. For 5–8 names, this takes one round instead of 8 rounds.

**For each surviving name, run at minimum 2 WebSearch queries:**

1. `"[name]"` — bare name, no qualifiers. Read the FULL first page. Look for: companies (any industry), consumer brands, food/products, famous people, geographic names, Wikipedia entries.
2. `"[name]" company` OR `"[name]" brand` OR `"[name]" product` — catch consumer brand and food conflicts that the first search may rank lower.

**If the name looks clean after those 2 searches, also run:**
3. `site:[name].com` — check if an active website exists at that domain.

**Output conflict findings as part of Round 2 evidence blocks** (see Two-Round Output Rule above) — not as intermediate progress updates.

**Conflict flags:**
- 🟢 Clean — no meaningful conflicts found across all searches
- 🟡 Minor — same name exists in a clearly unrelated industry (e.g. a local restaurant); note it but keep the name. If a well-known consumer brand (food, clothing) shares the name, also flag 🟡 and reduce Searchability score by 1–2 points.
- 🔴 Blocker — same name in same or adjacent category → eliminate immediately

**Also check:** social handle availability on X (Twitter), LinkedIn, GitHub, Product Hunt for top survivors.

If a target-language market is specified, check for profanity, negative connotations, or awkward sound-alikes.

### Step 2: Domain Verification

Domain availability was already checked via WebSearch in Phase 2 during the pre-screen pass. The Domain Availability scores in the matrix reflect those results.

For any names where Phase 2 results were inconclusive, ask the user to manually verify on Cloudflare before the final recommendation:

Use `AskUserQuestion` with the specific TLDs to check: `dash.cloudflare.com/domains`

Always ask the user to confirm the top 1–2 candidates on Cloudflare before registering — WebSearch results indicate *likely* availability, not ground truth.

**Domain resolution options (for final recommendation):**
- **Available at standard price** → Register on Cloudflare at-cost
- **Taken — .ai/.io available** → Use alternate TLD (entirely normal for modern AI/dev startups)
- **Taken — variant available** → `get[name].com` or `use[name].com` are legitimate launch options
- **Taken — worth buying** → For a truly great name, $5K–$30K domain purchase is rational; the name compounds in value for decades

### Step 3: Update Scores with Real Evidence

The user's selected names already have provisional scores from Phase 2. Now update the scores for these names using real evidence: apply conflict findings to Distinctiveness and Searchability, and replace the provisional Domain Availability score (3) with the real result from Step 2.

| Category | Question |
|----------|----------|
| **Memorability** | Will people remember it after one exposure? |
| **Pronounceability** | Can most users say it correctly? |
| **Spellability** | Can users spell it after hearing it? |
| **Distinctiveness** | Does it stand apart from same-category brands? Lower if 🟡 conflict exists. |
| **Brand Fit** | Does it feel right for this product and audience? |
| **Scalability** | Will it still work after expansion or pivot? |
| **Searchability** | Can it rank and be found without noise? Lower if consumer brand conflict creates search noise. |
| **Trademark Strength** | Is it likely ownable (not descriptive)? |
| **International Safety** | Does it travel well across markets? |
| **Phonetic Quality** | Does the sound carry the right psychological register? |
| **Domain Availability** | Are priority TLDs available? Use results from Step 3. |

**Domain Availability scoring rubric:**

| Score | Condition |
|-------|-----------|
| 5 | .com available |
| 4 | .ai + at least one other TLD (.io or .co) available |
| 3 | .ai only available, OR .io + .co available (no .ai) |
| 2 | Only one secondary TLD available (.io or .co) |
| 1 | Only fallback patterns available (get[name].com, use[name].com) |

**Thresholds (out of 55):**
- 44+ = Strong shortlist candidate
- 35–43 = Review manually
- <35 = Likely too weak

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

### Step 4: Final Recommendation

**First, output the Scoring Matrix** — all shortlisted names side-by-side across all 11 dimensions:

```
| Dimension            | [Name A] | [Name B] | [Name C] |
|----------------------|----------|----------|----------|
| Memorability         |    4     |    4     |    3     |
| Pronounceability     |    5     |    5     |    4     |
| Spellability         |    5     |    5     |    4     |
| Distinctiveness      |    5     |    4     |    4     |
| Brand Fit            |    5     |    5     |    4     |
| Scalability          |    5     |    5     |    5     |
| Searchability        |    5     |    4     |    5     |
| Trademark Strength   |    5     |    5     |    5     |
| International Safety |    4     |    4     |    4     |
| Phonetic Quality     |    4     |    4     |    3     |
| Domain Availability  |    4     |    3     |    2     |
| **Total /55**        |  **51**  |  **48**  |  **43**  |
```

**Then, present all 5 registrable candidates with equal weight:**

For each of the 5 candidates, present a card in this format:

| Field | Details |
|-------|---------|
| **Name** | The name |
| **Score** | Total /55 (reference matrix above) |
| **Domain Path** | Best available domain + registration strategy |
| **Conflicts** | Conflict screening result (🟢/🟡/🔴) |
| **Brand Rationale** | Why this name works — roots, sound psychology, strategic fit |

Do NOT rank them gold/silver/bronze or declare a winner. All 5 are presented as equal candidates.

If conflict screening eliminates one of the 5, pull up the next scored candidate from the ~20 pool.

**Closing section — output after all 5 candidate cards:**

---

### What's Next

这 5 个名字都通过了可注册性检验（无冲突 + 域名可用）。命名决策不需要着急——好名字需要时间发酵。

**不需要现在做决定。** 把这 5 个名字放在那里，边用边感受。

**准备好之后：**
1. **48小时沉淀测试** — 把你最有感觉的名字反复念两天。好名字越念越对，越念越有感觉。
2. **Cloudflare 手动验证** — 在 `dash.cloudflare.com/domains` 确认域名可用性（WebSearch 结果仅供参考，不是最终状态）
3. **注册域名** — Cloudflare Registrar 以成本价注册
4. **商标咨询** — 5 个候选名都属于强商标类别（非描述性），建议在决策后尽早咨询

**现在可以继续品牌定位：** 品牌定位是战略层工作，不依赖于最终名字。选任意一个候选名作为工作名称（working name），定位完成后再做最终命名决策。

---

## Appendix: Domain Reference

### Domain Availability Verification

| Tier | Method | Reliability |
|------|--------|-------------|
| 1 | WebSearch `"[name].com"` / `"[name].ai"` | Moderate — shows active sites |
| 2 | User manual check on `dash.cloudflare.com/domains` | Ground truth |

Domain availability is checked in Phase 2 via WebSearch during the pre-screen pass. **Do not run bash, Python, curl, or WHOIS commands.** If WebSearch results are inconclusive, ask the user to verify on Cloudflare.

**Recommended registrar:** Cloudflare Registrar (at-cost): `dash.cloudflare.com/domains`

**Premium Domain Marketplaces (if target domain is taken):**

| Marketplace | Notes |
|-------------|-------|
| **Sedo** | Largest marketplace; auction + fixed price |
| **Dan.com** | Simple buy/lease; installment plans |
| **Afternic** | GoDaddy's marketplace; huge inventory |
| **BrandBucket** | Curated premium names $1K–$50K; includes logo |

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
- **Resend's Criteria Filter**: Set explicit, measurable naming criteria before generating (e.g., .com available, <10 chars, product-connected, pronounceable) and filter against them ruthlessly. Named criteria beat gut feeling every time.
- **The Placeholder Trap**: Temporary names become permanent faster than expected (Slack, Supabase, Stripe). If you're not ready to commit, avoid letting a placeholder gain traction.

---

## Real-World Naming Case Studies

How great tech brands got their names — organized by naming approach.

### Real Word (Repurposed)

**Stripe** — The Collison brothers tried PayDemon, /dev/payments, PayForge. Unable to decide, they set a hard deadline: if nothing better by December 20, 2010, they'd go with "Stripe." The deadline decided. *Takeaway: constraints produce decisions. Deadlines work.*

**Notion** — "An idea." A real English word mapped directly to the product's purpose as a workspace for ideas and concepts. No agency, no process — just the right metaphor. *Takeaway: the simplest word that fits the outcome usually wins.*

**Linear** — CEO Karri Saarinen: "people want linear processes and outcomes." The name describes the desired state, not the product's features. *Takeaway: name the feeling, not the feature.*

**Slack** — Stewart Butterfield's internal codename that stuck. Later backronymed to "Searchable Log of All Conversation and Knowledge" (the acronym came after, not before). *Takeaway: placeholders become permanent faster than you think. Post-hoc stories are fine.*

**Resend** — Zeno Rocha set four explicit criteria before generating: .com TLD, fewer than 10 characters, connected to the product, easy to type and pronounce. "Resend" met all four. *Takeaway: write your criteria down first. They filter faster than intuition.*

### Coined / Morpheme-Engineered

**Vercel** — Lexicon Branding was hired to rename Zeit (German for "time"), which struggled to attract investment. Lexicon ran morpheme engineering across five languages: "ver-" from versatile/accelerate, "-cel" from excel. "V" was chosen as the most vibrant consonant in English. Rebranded in April 2020, coinciding with a $21M Series A. *Takeaway: professional naming uses sound science, not just vibes. The rebrand unlocked investment.*

**Spotify** — Daniel Ek and Martin Lorentzon were shouting name ideas from different rooms. Ek misheard one as "Spotify," Googled it, found zero results, and registered the domain within minutes. Later rationalized as "spot + identify." *Takeaway: happy accidents work. The story doesn't need to come first.*

**Figma** — From Latin "fingere" (to shape/mold). Short, pronounceable, high searchability, .com domain available. Classical root adds semantic depth without being obvious. *Takeaway: classical roots reward discovery — users find meaning in the name over time.*

### Compound / Portmanteau

**Shopify** — Original company name was "Jaded Pixel." Co-founder Scott Lake combined "shopping" + "simplify" and found the domain available. *Takeaway: 1+1=3. Compounds communicate instantly without being too literal.*

**Supabase** — Paul Copplestone was brainstorming database names, tried "ultrabase" and "hyperbase" — nothing available. He put "supabase" as a placeholder joke inspired partly by Nicki Minaj's "Super Bass." After unexpectedly hitting #1 on Hacker News, they couldn't change it. *Takeaway: viral momentum locks in names. Even jokes become permanent once they gain traction.*

**Canva** — During a team session, a French engineer noted that "canvas" is pronounced "canva" in French. The truncation became the final name. *Takeaway: cross-language pronunciation can reveal cleaner forms hidden inside familiar words.*

---

## Naming Bias by Company Type

| Company Type | Best Name Bias |
|-------------|----------------|
| AI / ML startup | Invented, abstract, evocative, morpheme-engineered |
| Developer tool | Abstract, technical, compound, truncation |
| Consumer app | Invented, playful, warm, personification, onomatopoeia |
| Enterprise SaaS | Professional, abstract, stable, morpheme-engineered |
| Security product | Hard consonants, mythic, trustworthy |
| Fintech | Short, credible, precise, alphanumeric |
| Creative tool | Abstract, soft, elegant |
| Agent / assistant | Personification, human, warm, memorable |

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

   ## Scoring Matrix
   [11-dimension × N-name matrix table, totals /55]

   ## 5 Registrable Candidates
   [5 names with equal presentation: score, domain situation, conflicts, brand rationale]

   ## Full Candidate Set
   [all candidates by perspective]

   ## Scoring Summary
   [scoring table for shortlisted names]
   ```
4. Confirm: "✅ Saved to `{project-name}/01-naming.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **5 个可注册候选名已就绪！** 你不需要现在做决定——好名字需要时间发酵。下一步是 **品牌定位**——我们可以用任意一个候选名作为工作名称开始定位，定位完成后再做最终命名决策。要现在开始 `brand-positioning` 吗？
