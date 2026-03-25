
# Brand Namer — Professional Naming Skill

> **Company Branding Workflow: Step ① of 5**
> `① Naming` → ② Positioning → ③ Voice & Messaging → ④ Visual Identity → ⑤ SEO Content
>
> **This is the starting point.** Name first, because everything downstream — domain, positioning, visual identity — follows the name. Once you have a name, move to `brand-positioning`.
> No prerequisites. After this skill: run `brand-positioning`.

A structured, three-phase naming system built from Lexicon Branding methodology (the firm behind Vercel, BlackBerry, Azure, Sonos, Windsurf), startup pattern analysis, phonetic heuristics, trademark logic, and domain strategy. This skill does not just generate random names — it produces names that are distinctive, memorable, scalable, pronounceable, searchable, and brandable over a 10-year horizon.

**The three phases follow Lexicon's proven sequence: Identify → Invent → Implement.**

Domain availability is handled in the Implement phase — it is a logistics problem, not a naming problem. The right name matters far more than the exact .com. As Lexicon's David Placek puts it: "A domain is just an area code." Domain conflicts can always be resolved through prefixes, alternative extensions, or purchases at modest cost. Never sacrifice a great name for a mediocre one because of domain anxiety.

**The "Surprisingly Familiar" Principle:** Placek's defining insight: "The brain is lazy. It likes the familiar." The best names are "surprising, but surprisingly familiar" — they use familiar linguistic components (common morphemes, recognizable sound patterns, real-language roots) assembled in an unfamiliar configuration. This is why Lexicon's invented names sound natural rather than random: Vercel carries echoes of "versatile" and "excel" without being either. Pentium evokes "titanium" and "premium" without saying them. The brain processes these names faster because the components are already in its library, but the combination is new enough to be ownable. Every name this skill generates should pass the surprisingly-familiar test: novel enough to own, familiar enough to trust on first encounter.

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

**If onboarding was completed in this session**: The user already answered Target, Audience, and Description during onboarding. Skip Round 1 entirely and start at Round 2 (Diamond Framework). Use the onboarding answers:
- Map Project Type → Target: "Software / SaaS" or "Consumer product" → "Product"; "Agency / consulting" → "Company"
- Audience → carried directly
- Description → carried directly

If no onboarding context is available (user jumped directly to naming or returned in a new session), ask Round 1 normally.

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

### Round 3 — Style & Constraints

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Pick 1-2 style directions that fit your brand:"
- header: "Style"
- multiSelect: true
- options:
  - { label: "Short & Punchy", description: "4-6 letters, hard consonants, instant recall (e.g., Stripe, Snap)" }
  - { label: "Abstract / Minimal", description: "Non-literal, clean, category-scalable (e.g., Linear, Notion)" }
  - { label: "Technical", description: "Precise, developer-native, system-like (e.g., Vercel, Twilio)" }
  - { label: "Human / Playful", description: "Warm, approachable, consumer-friendly — or Premium/Mythic via 'Other'" }

**Q2:**
- question: "Any themes to AVOID in the name?"
- header: "Avoid"
- multiSelect: true
- options:
  - { label: "AI/GPT trend words", description: "No 'AI', 'GPT', 'neural', 'smart' — dates badly" }
  - { label: "Too-literal words", description: "Avoid function-first names like Pay, Wallet, Send, Auth" }
  - { label: "Crypto/web3 vibes", description: "No chain, block, token, mint — even if unintentional" }
  - { label: "No restrictions", description: "Open to any direction — let the brief lead" }

**Q3:**
- question: "Domain preference? (guideline, not a gate)"
- header: "Domain"
- multiSelect: true
- options:
  - { label: ".xyz preferred", description: "Modern, clean, highly available — primary default" }
  - { label: ".com preferred", description: "Strongest trust signal — will work hard to get it" }
  - { label: ".io is fine", description: "Developer-familiar, common for tools and platforms" }
  - { label: "Any TLD works", description: "Including .ai, .co, .dev — the name matters more" }

Then ask as a follow-up prose question if needed: language requirements, length preference, any geographic or linguistic constraints.

---

## Phase 2: Invent

> "When you name something, you give it power." — The name is not a label; it is the foundational brand anchor. Naming initiates personality development for an enterprise. Everything that follows — positioning, voice, visual identity — flows from the name.

**Goal:** Generate a large, diverse candidate set from multiple cognitive perspectives before any filtering begins. Quantity enables quality — the first 50 names are almost always the most generic. The breakthroughs emerge after volume.

**Target: 60–100 candidates total.** Generate in three cognitive batches to maximize diversity.

> **Key principle from Lexicon:** Separate generation from evaluation entirely. No judgment during generation. Generate first, judge later. Teams that evaluate while generating produce smaller, safer, more forgettable candidate sets.

> **Multiple Exploration Cycles:** Lexicon repeats the generation process across different semantic territories over multiple periods. Single-session brainstorming produces "marginal results due to groupthink." If the first 60–100 candidates don't yield strong shortlist material, do not simply generate more of the same — shift to a completely different thematic territory (e.g., from "speed/precision" to "craft/artisanship" to "nature/organic") and run the three perspectives again. Each cycle should feel like a fresh start with different source concepts, not a continuation of the first. Two to three territory cycles typically surface breakthrough candidates that a single pass misses.

> **Professional context:** Lexicon's naming engagements typically span 8 weeks with 10–12 people working on creative development and trademark research in parallel. This skill compresses that process into a structured conversation — the rigor is preserved, the timeline is accelerated.

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

**Distribution target:** 70%+ should be Invented, Abstract, Compound, or **Morpheme-Engineered** types. These have the strongest trademark position and highest ownability. Counter-intuitively, invented names actually take less money to build into brands than existing words — they face no competition for meaning and generate more attention through unexpectedness.

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

**Sound Balance — The Trust-Imagination Duality:**

Every name must inspire both trust AND imagination simultaneously. Pure trust sounds (hard consonants, stable stops) feel reliable but boring. Pure imagination sounds (unusual clusters, exotic vowels) feel exciting but risky. The strongest Lexicon names blend both:

- **Azure:** "zure" phonetically echoes "sure" — providing trust through sound — while "A-" and the "zh" create distinctiveness and imagination.
- **Dasani:** Latin "san" (health/wellness) provides trust; crisp opening "da" and light "-i" ending create a fresh, imaginative sensory experience.
- **BlackBerry:** Explosive "b" and "k" (dynamism, trust) paired with soft "berry" (organic, approachable) — the compound itself embodies the duality.

**Practical rule:** After generating candidates, audit each for this balance. If a name sounds only reliable (too many hard stops, no flow), it will bore. If it sounds only creative (too many unusual clusters, no grounding), it will confuse. The sweet spot is when the listener feels both "I trust this" and "I'm curious about it" simultaneously.

---

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
| **Alliterative Construction** | Build a name with repeating initial consonants. Alliteration is one of the strongest memorability multipliers — the repeated sound creates a phonetic hook that dramatically increases recall in noise. | Coca-Cola, PayPal, Best Buy, Krispy Kreme, TikTok |
| **Palindromic / Symmetric Construction** | Create names that read identically forwards and backwards, or whose visual/phonetic halves mirror each other. Symmetrical structures enhance visual distinctiveness and auditory memorability. | Sonos (palindrome — mirrors itself, evokes sound waves), Navan (palindrome — suggests forward movement), Kayak, Civic |
| **Prefix/Suffix Matrix** | Define N prefixes and M suffixes from a semantic territory; systematically combine to generate N×M candidates. More rigorous than ad-hoc affixing — it exhausts a territory before moving on. | Lexicon generated 55 prefixes × 102 suffixes for Vercel → 60 candidates; repeated across 3 territories over 2 weeks |
| **Prefix / Suffix Grafting** | Attach systematic affixes to a root | Uber-, Shopify (-ify), Bitly (-ly), Calendly |
| **Truncation + Suffix** | Clip a word down to its root, then add a new ending | Accel(-a), Forgo(-io), Prism(-atic) |
| **Phonestheme Mining** | Use sound clusters that carry consistent psychological meaning across many words | gl- (light/vision): Glow, Gleam, Glint — sn- (quick/sharp): Snap, Swift — str- (force): Stripe, Strong |

> **The Prefix/Suffix Matrix — Lexicon's Volume Engine:**
> For the Vercel project, Lexicon extracted 55 prefixes and 102 suffixes from speed/accuracy/reliability concepts across Greek, Latin, and Sanskrit — then systematically combined them to produce 60 candidates. They repeated the process three times over two weeks across different semantic territories, yielding hundreds of candidates from structured combination alone. To apply this method:
> 1. Choose a semantic territory (e.g., "precision + speed")
> 2. Extract 15–30 prefixes from concept words in that territory (e.g., ver-, vel-, ac-, cel-, str-, flo-, rel-)
> 3. Extract 20–40 suffixes from concept words and classical roots (e.g., -el, -on, -ix, -a, -um, -is, -al, -en)
> 4. Systematically test combinations — keep those that sound natural and pass the phone test
> 5. If the first territory yields fewer than 15 strong candidates, shift to a new territory and repeat

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
- `"[name].xyz"` — if an active website appears, .xyz is TAKEN
- `"[name].com"` — if an active website appears, .com is TAKEN
- `"[name].io"` — if an active website appears, .io is TAKEN
- `"[name].sh"` — if an active website appears, .sh is TAKEN

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

**Then automatically select the top 10 registrable candidates:**

From the scored ~20 candidates, auto-select the top 10 by Total score where:
1. Conflict status is not 🔴 (already eliminated in pre-screen)
2. Domain Availability score >= 3 (meaning at least .ai-only or .io+.co available)

If fewer than 10 meet Domain >= 3, relax to Domain >= 2 to fill remaining slots.

**Balance rule:** The 10 candidates must include a balanced mix — approximately 5 real words / cross-language real words AND 5 morpheme-engineered / fanciful names. If auto-selection produces an imbalanced set (e.g., 8 engineered + 2 real words), replace the excess from the overrepresented category with the next-highest-scoring name from the underrepresented category. Label each candidate's type in the shortlist table.

After the matrix, output:

> 根据可注册性（无冲突 + 域名可用）和总分，以下 10 个候选名进入深度审查：

| Name | Total /55 | Type | Domain Status | Brand Logic |
|------|-----------|------|---------------|-------------|
| [Name A] | XX | Real word | .ai/.io available | [one-line] |
| [Name B] | XX | Engineered | .com available | [one-line] |
| ... | ... | ... | ... | ... |

Proceed to Phase 3 with these 10 names. Do NOT ask the user to choose — present all 10 as equal candidates.

> **Note:** If the user finds none of these appealing after reviewing, generate another batch of 20–30 names with adjusted direction and repeat the pre-screen.

---

## Phase 3: Implement

**Goal:** Take the top 10 registrable candidates through full evidence — conflict deep-dive, domain verification, and final scoring — then present all 10 as equal candidates for the user to consider.

The top 10 names were automatically selected in Phase 2 based on registrability (clean conflicts + domain availability), total score, and balance (approximately 5 real words + 5 engineered). Proceed to conflict screening and domain verification for all 10.

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
| .xyz | ✅ Available / ❌ Taken |
| .com | ✅ / ❌ |
| .io  | ✅ / ❌ |
| .sh  | ✅ / ❌ |

**评分（/55）：**
| 维度 | 分 | 理由 |
|------|----|----|
| Memorability | 4 | [why] |
| Pronounceability | 5 | [why] |
| ... | ... | ... |
| Domain Availability | 4 | .xyz/.io 可用，.com 监控中 |
| **Total** | **XX** | |
```

After all evidence blocks are presented, output the Scoring Matrix (all names × all dimensions) and Top 3 recommendation.

---

### Step 1: Conflict Screening

Run conflict checks on ALL first-pass survivors **before scoring**. This saves time and prevents scoring names that will be eliminated.

**Efficiency rule: run all conflict searches in parallel.** Use multiple WebSearch calls in a single message (or Agent tool batches) — never search one name at a time sequentially. For 10–12 names, split into 2–3 parallel batches of 4–5 names each — this takes 2–3 rounds instead of 12 sequential rounds.

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

**Multilingual screening:** Lexicon analyzes name candidates across 20+ languages using a network of 250+ linguists — including languages less commonly checked such as Indonesian, Malay, Turkish, and Swahili. For this skill, apply a practical lightweight version: beyond the target market's primary languages, always check the name against Spanish, Portuguese, Arabic, Hindi, Mandarin, Japanese, and Korean. These cover the largest global populations where unintended meanings cause the most reputational damage. Flag any candidate where the name sounds like a common word with negative, vulgar, or comical meaning in any of these languages — not just exact matches, but phonetic similarity to sensitive words.

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
| 5 | All four primary TLDs available (.xyz + .com + .io + .sh) |
| 4 | Three of four primary TLDs available |
| 3 | Two of four primary TLDs available |
| 2 | One primary TLD or only secondary TLDs available (.ai, .co, .dev) |
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

**Then, present all 10 registrable candidates with equal weight:**

For each of the 10 candidates, present a card in this format:

| Field | Details |
|-------|---------|
| **Name** | The name |
| **Type** | Real word / Cross-language / Morpheme-engineered / Fanciful |
| **Score** | Total /55 (reference matrix above) |
| **Domain Path** | Best available domain + registration strategy |
| **Conflicts** | Conflict screening result (🟢/🟡/🔴) |
| **Brand Rationale** | Why this name works — roots, sound psychology, strategic fit |

Do NOT rank them gold/silver/bronze or declare a winner. All 10 are presented as equal candidates.

If conflict screening eliminates one of the 10, pull up the next scored candidate from the ~20 pool (maintaining the real word / engineered balance).

**Closing section — output after all 10 candidate cards:**

---

### What's Next

这 10 个名字都通过了可注册性检验（无冲突 + 域名可用）。命名决策不需要着急——好名字需要时间发酵。

**不需要现在做决定。** 把这 10 个名字放在那里，边用边感受。

**准备好之后：**
1. **48小时沉淀测试** — 把你最有感觉的名字反复念两天。好名字越念越对，越念越有感觉。
2. **手动验证域名可用性** — `.xyz` / `.com` / `.io` 在 `dash.cloudflare.com/domains` 确认；`.sh` 域名 Cloudflare 不支持，请在 `namecheap.com` 或 `porkbun.com` 查询
3. **注册域名** — `.xyz` / `.com` / `.io` 用 Cloudflare Registrar 以成本价注册；`.sh` 用 Namecheap 或 Porkbun（约 $29–40/yr）
4. **商标咨询** — 10 个候选名都属于强商标类别（非描述性），建议在决策后尽早咨询

**现在可以继续品牌定位：** 品牌定位是战略层工作，不依赖于最终名字。所有 10 个候选名将携带到后续步骤——不需要现在选定，随时可以在单独的会话中继续。

---

## Appendix: Domain Reference

### Domain Availability Verification

| Tier | Method | Reliability |
|------|--------|-------------|
| 1 | WebSearch `"[name].com"` / `"[name].sh"` | Moderate — shows active sites |
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
| .sh | ~$29–40/yr | **Not on Cloudflare** — use Namecheap or Porkbun |
| .app | ~$14.00/yr | Forces HTTPS; consumer/mobile |
| .tech | ~$4.47/yr | Budget-friendly tech signal |

⚠️ Prices may change — verify at dash.cloudflare.com.

### TLD Priority Reference

| Priority | TLD | Best For |
|----------|-----|----------|
| 🥇 Tier 1 | **.xyz** | Primary default — modern, clean, high availability |
| 🥇 Tier 1 | **.com** | Strongest trust signal |
| 🥇 Tier 1 | **.io** | Developer tools, tech standard |
| 🥇 Tier 1 | **.sh** | Short, dev-friendly, shell/script association |
| 🥈 Tier 2 | **.ai** | AI / ML companies |
| 🥈 Tier 2 | **.co** | Short fallback |
| 🥈 Tier 2 | **.dev** | Developer-facing |
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
- **Name as First Growth Lever**: The name is "the cheapest ROI investment in the growth funnel." It works on Day 1 — seizing semantic territory before any marketing spend. Invented names require less money to build into brands than existing words because they generate more attention through unexpectedness and face no competition for meaning. A great name compounds in value from the moment it ships.

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

**Vercel** — See full case study in Rebrand Case Studies below. *Takeaway: when a name blocks growth, renaming is a strategic investment, not vanity.*

**Spotify** — Daniel Ek and Martin Lorentzon were shouting name ideas from different rooms. Ek misheard one as "Spotify," Googled it, found zero results, and registered the domain within minutes. Later rationalized as "spot + identify." *Takeaway: happy accidents work. The story doesn't need to come first.*

**Figma** — From Latin "fingere" (to shape/mold). Short, pronounceable, high searchability, .com domain available. Classical root adds semantic depth without being obvious. *Takeaway: classical roots reward discovery — users find meaning in the name over time.*

**Pentium** — Intel needed to escape from forgettable alphanumeric chip names (386, 486). Lexicon established a criterion: develop a name resembling fundamental elements of computing. The "-ium" suffix (evoking titanium, sodium, palladium) signaled elemental, foundational strength. When Lexicon presented the name, Intel's executive committee split — some wanted the safe "Pro Chip," others were drawn to the bold Pentium. CEO Andy Grove recognized the polarization itself as a strength signal: "I see the polarization here... that tells me there's energy for Pentium." Consumers began actively requesting Pentium computers by name within months. *Takeaway: the "-ium" suffix signals elemental power. When a leadership team is polarized on a name, that tension is a signal of strength, not a reason to retreat.*

### Compound / Portmanteau

**Shopify** — Original company name was "Jaded Pixel." Co-founder Scott Lake combined "shopping" + "simplify" and found the domain available. *Takeaway: 1+1=3. Compounds communicate instantly without being too literal.*

**Supabase** — Paul Copplestone was brainstorming database names, tried "ultrabase" and "hyperbase" — nothing available. He put "supabase" as a placeholder joke inspired partly by Nicki Minaj's "Super Bass." After unexpectedly hitting #1 on Hacker News, they couldn't change it. *Takeaway: viral momentum locks in names. Even jokes become permanent once they gain traction.*

**BlackBerry** — Lexicon's brief from RIM: the device name shouldn't stress or elevate blood pressure, but do the exact opposite — "calming, like fresh fruit, like a summer vacation." The team wrote words on butcher paper; someone wrote "strawberry," someone else wrote "blackberry." Lexicon rejected "Strawberry" as insufficiently vigorous for a business device. "BlackBerry" won because the explosive consonants "b" and "k" convey dynamism and decisiveness, while "berry" carries organic warmth and approachability — the compound embodies the trust-imagination duality: serious enough for enterprise, natural enough for everyday use. *Takeaway: sound psychology is not abstract — the specific phonetic choice directly shaped user perception of the product's personality.*

**Swiffer** — Procter & Gamble hired Lexicon for what looked like an improved mop. Lexicon's research with 25 consumers revealed that mopping was universally hated — a dreaded chore. Rather than naming around "cleaning" (the function people despised), Lexicon reframed around the experience they wanted to create: "fun rather than function." They explored actions (sweeping, wiping, washing) and emotional associations with toys and vacation activities. "Swiffer" — light, fast, playful in sound — achieved 80% consumer preference in testing. *Takeaway: name the experience you want to create, not the task you're replacing. The brief should be about desired feeling, not product function.*

**Canva** — During a team session, a French engineer noted that "canvas" is pronounced "canva" in French. The truncation became the final name. *Takeaway: cross-language pronunciation can reveal cleaner forms hidden inside familiar words.*

---

### Rebrand Case Studies

**Navan (formerly TripActions)** — "TripActions" described the product accurately (travel + actions) but locked the company into travel. After expanding into expense management and corporate payments, the original name became a ceiling. Lexicon created "Navan" — a palindrome (reads the same forwards and backwards) that suggests forward movement while remaining completely category-flexible. The palindromic structure creates visual memorability and semantic openness. Revenue grew from $150M to $500M post-rebrand. *Takeaway: descriptive names become ceilings at the moment of expansion. Palindromic structure provides visual distinctiveness and infinite semantic flexibility.*

**Vercel (formerly Zeit)** — Zeit (German for "time") struggled to attract English-speaking investment despite strong technical fundamentals. Lexicon ran morpheme engineering across five languages, building a matrix of 55 prefixes and 102 suffixes from speed/accuracy/reliability concepts in Greek, Latin, and Sanskrit. They generated 60 candidates, evaluated them through sound-symbolism analysis to identify fast-sounding letters, then repeated the process across three different semantic territories over two weeks. The winning name, Vercel: six letters, "ver-" from versatile/veritas/accelerate, "-cel" from excel/accelerate. "V" was chosen as the most vibrant consonant in English. "Surprising, but surprisingly familiar." The rebrand coincided with a $21M Series A in April 2020. *Takeaway: professional naming uses systematic methodology (prefix/suffix matrices, multi-territory cycles, sound science) — not vibes. The right name unlocks investment.*

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

### AI Naming — Lexicon Principles

Placek has specific guidance for naming AI ventures, developed through extensive research across nine countries:

- **Avoid anthropomorphic language for corporate AI products.** Names that sound too human overpromise — they set expectations of human-level understanding and create backlash when the product falls short. Reserve personification names (Alexa, Siri) for consumer assistants where personality is the product.
- **Blend hardness and softness.** AI names must convey "technology's reliability while remaining approachable." Pure-tech names (GPT, anything-LLM) feel harsh and clinical. Pure-soft names feel unserious for enterprise. Target the register of "Lexus" — technological trustworthiness fused with user-friendliness.
- **Corporate AI names need flexibility.** If the AI product will spawn multiple sub-products or features, the parent name must be abstract enough to serve as an umbrella. Names that lock into a single capability ("ChattingAI", "CodeHelper") become ceilings.
- **Product-level AI names can be more playful.** A specific AI feature or consumer-facing assistant has more latitude for warmth, personality, and even whimsy than the corporate brand.
- **Sound balance is critical for AI.** Lexicon's research across nine countries identified that "V" universally signals "aliveness, movement, vitality" — making it a strong choice for AI products that need to feel dynamic (Vercel, Vertex, Vivid). Hard stops (K, T, B) add trustworthiness. Soft clusters (Sl, Fl, L) add approachability. An AI corporate brand should have at least one of each register.

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

   ## Discovery Inputs
   - **Target**: [Company / Product / Agent / Feature]
   - **Audience**: [from Round 1 Q2 or onboarding]
   - **Description**: [user's typed description]
   - **Diamond Win**: [from Round 2]
   - **Diamond Have**: [from Round 2]
   - **Diamond Need**: [from Round 2]
   - **Diamond Say**: [from Round 2]
   - **Style direction**: [from Round 3 Q1]
   - **Avoid themes**: [from Round 3 Q2]
   - **Domain preference**: [from Round 3 Q3]

   ## Scoring Matrix
   [11-dimension × N-name matrix table, totals /55]

   ## 10 Registrable Candidates
   [10 names with equal presentation: type, score, domain situation, conflicts, brand rationale — balanced ~5 real words + ~5 engineered]

   ## Full Candidate Set
   [all candidates by perspective]

   ## Scoring Summary
   [scoring table for shortlisted names]
   ```
4. Confirm: "✅ Saved to `{project-name}/01-naming.md`"

---

## Workflow: Next Step

After completing this skill, prompt the user:

> **10 个可注册候选名已就绪！** 你不需要现在做决定——好名字需要时间发酵。下一步是 **品牌定位**——我们可以用任意一个候选名作为工作名称开始定位，定位完成后再做最终命名决策。要现在开始 `brand-positioning` 吗？
