
# SEO Content Strategy & Creation — Skill

> **Company Branding Workflow: Step ⑤ of 5**
> ① Naming → ② Positioning → ③ Voice & Messaging → ④ Visual Identity → `⑤ SEO Content`
>
> **Prerequisite**: Ideally the project folder contains outputs from previous steps (`01-naming.md` through `04-visual.md`). At minimum: positioning statement and brand voice guidelines. Can work standalone if the user just needs SEO help.
> **Input from project files**: Read any existing module outputs from the project folder — name candidates, positioning statement, value proposition, voice & tone guidelines, target audience.
> **What this step produces**: Topic clusters, keyword plan, content calendar, SEO-optimized articles, GEO optimization, technical SEO checklist.
> **This is the final step.** After completing all 5 skills, the user has a full brand foundation + content engine.

A structured framework for building content that ranks in both traditional search (Google) and AI search engines (ChatGPT, Perplexity, Google SGE). This skill covers strategy, keyword research, content creation, and optimization.

### Tool Usage Rule

**ALWAYS use the `AskUserQuestion` tool for all questions throughout this skill.** Every round of questions should be presented as interactive clickable choices.

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

**If the user completed previous branding steps**: Ask them to share their brand name + domain, positioning statement, voice guidelines, and visual identity summary. Use these as input to align SEO content with the established brand. Skip any discovery questions already answered.

### Round 1 — Business Context

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "What's your primary SEO goal?"
- header: "SEO goal"
- multiSelect: false
- options:
  - { label: "Drive organic traffic", description: "Get more visitors from Google search" }
  - { label: "Generate leads", description: "Convert search visitors into signups or demos" }
  - { label: "Rank for brand keywords", description: "Own search results for your product name and category" }
  - { label: "AI search citations", description: "Get cited by ChatGPT, Perplexity, Google SGE — also thought leadership via 'Other'" }

**Q2:**
- question: "What stage is your content at?"
- header: "Content stage"
- multiSelect: false
- options:
  - { label: "Starting from zero", description: "No content, no strategy — building from scratch" }
  - { label: "Some content, need strategy", description: "Have scattered content, need structure and direction" }
  - { label: "Lots of content, need optimization", description: "Content exists but isn't performing — needs refresh" }
  - { label: "Rebuilding after rebrand", description: "Existing content needs to be realigned with new brand" }

**Q3:**
- question: "Who is your target reader?"
- header: "Reader"
- multiSelect: true
- options:
  - { label: "Developers", description: "Engineers, DevOps, technical builders" }
  - { label: "Founders / startups", description: "Early-stage builders, solo founders, small teams" }
  - { label: "Enterprise buyers", description: "Decision-makers, procurement, executives" }
  - { label: "Consumers / general", description: "General public or broad tech audience" }

### Round 2 — Content Context

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "What type of content do you need right now?"
- header: "Content type"
- multiSelect: false
- options:
  - { label: "Full content strategy", description: "Topic clusters, keyword plan, content calendar — the full picture" }
  - { label: "Blog posts", description: "Individual articles targeting specific keywords" }
  - { label: "Pillar + cluster", description: "One comprehensive guide + supporting articles around a topic" }
  - { label: "Comparison pages", description: "'X vs Y' or 'X alternatives' pages — high commercial intent" }

**Q2:**
- question: "How often can you publish?"
- header: "Publish cadence"
- multiSelect: false
- options:
  - { label: "Weekly", description: "1 piece per week — sustainable for most teams" }
  - { label: "2-3x per week", description: "Aggressive growth mode — strong output" }
  - { label: "Monthly", description: "Focus on quality over quantity — 1 deep piece" }
  - { label: "Not sure yet", description: "Help me figure out the right cadence" }

**Q3:**
- question: "Which search surfaces matter to you?"
- header": "Search surface"
- multiSelect: true
- options:
  - { label: "Google organic", description: "Traditional search results — the foundation" }
  - { label: "AI search (GEO)", description: "ChatGPT, Perplexity, Google AI Overviews — growing fast" }
  - { label: "YouTube", description: "Video content that also drives search traffic" }
  - { label: "All of them", description: "Optimize for every surface — full coverage approach" }

### Round 3 — Competitive & Keyword Context

Call `AskUserQuestion` with 3 questions:

**Q1:**
- question: "Do you have existing keyword research?"
- header: "Keywords"
- multiSelect: false
- options:
  - { label: "Yes, I'll share it", description: "I have a keyword list — I'll paste it in the next message" }
  - { label: "Some ideas, nothing formal", description: "I know roughly what to target but haven't done proper research" }
  - { label: "Starting from scratch", description: "No keyword research done yet — need to build from zero" }

**Q2:**
- question: "What's your domain authority roughly?"
- header: "Domain authority"
- multiSelect: false
- options:
  - { label: "Brand new (DA 0-10)", description: "New domain — focus on low-difficulty, long-tail keywords" }
  - { label: "Early stage (DA 10-30)", description: "Some traction — mix of long-tail and mid-difficulty" }
  - { label: "Growing (DA 30-50)", description: "Established presence — can compete on higher-value terms" }
  - { label: "Not sure", description: "I haven't checked — will look it up" }

**Q3:**
- question: "What SEO tools do you have access to?"
- header: "SEO tools"
- multiSelect: true
- options:
  - { label: "Ahrefs / SEMrush", description: "Paid keyword research and competitor analysis tools" }
  - { label: "Google Search Console", description: "Free — see what queries bring traffic to your site" }
  - { label: "Google Analytics 4", description: "Free — track traffic, user behavior, conversions" }
  - { label: "None / free only", description: "No paid tools — use free alternatives like Ubersuggest, AlsoAsked" }

---

## Phase 2: Keyword & Topic Research

### Step 1: Identify Topic Clusters

Based on discovery answers, map out **3-5 topic clusters**. Each cluster has:

| Component | What It Is | Example |
|-----------|-----------|---------|
| **Pillar Topic** | Broad theme you want to own | "Agent Payments" |
| **Pillar Page** | Comprehensive guide (2000-4000 words) | "The Complete Guide to AI Agent Payments" |
| **Cluster Articles** | 5-10 supporting articles targeting long-tail keywords | "How to Set Up Agent-to-Agent Payments", "Agent Payment Security Best Practices" |
| **Internal Links** | Every cluster article links to the pillar, pillar links to each cluster | Hub-and-spoke model |

### Step 2: Keyword Research Framework

For each topic cluster, identify keywords across **4 intent levels**:

| Intent | What User Wants | Keyword Pattern | Conversion |
|--------|----------------|----------------|------------|
| **Informational** | Learn something | "what is X", "how does X work", "X guide" | Low (awareness) |
| **Navigational** | Find a specific thing | "[brand] pricing", "[brand] docs" | Medium |
| **Commercial** | Compare options | "best X for Y", "X vs Y", "X alternatives" | High |
| **Transactional** | Buy / sign up | "X pricing", "buy X", "X free trial" | Highest |

**For new domains (DA 0-30)**: Focus 70% on informational long-tail, 20% commercial, 10% transactional. You can't compete on high-volume terms yet.

**For growing domains (DA 30+)**: Balance across all 4 intents.

### Step 3: Keyword Selection Criteria

For each keyword, evaluate:

| Factor | Question | Priority |
|--------|----------|----------|
| **Search Volume** | How many monthly searches? | Medium |
| **Keyword Difficulty** | How hard to rank for? (target KD < 30 for new sites) | High |
| **Business Relevance** | Does this connect to our product? | Highest |
| **Intent Match** | Does our content satisfy this search intent? | High |
| **SERP Opportunity** | Are current results weak? Can we do better? | Medium |

### Step 4: Present Keyword Plan

Output a keyword plan table:

| Keyword | Volume | KD | Intent | Cluster | Content Type | Priority |
|---------|--------|----|----- --|---------|-------------|----------|
| | | | | | | |

Use web search to validate keyword ideas if needed.

---

## Phase 3: Content Creation

### Blog Post / Article Template

For each piece of content, follow this structure:

#### Pre-Writing Brief

| Field | Details |
|-------|---------|
| **Target Keyword** | Primary keyword to rank for |
| **Secondary Keywords** | 3-5 related terms to include naturally |
| **Search Intent** | What the reader expects to find |
| **Target Word Count** | Based on SERP analysis (typically 1500-3000 for blog posts) |
| **Audience** | Who is reading this and what do they know already |
| **Unique Angle** | What makes our take different from page 1 results |
| **CTA** | What action should the reader take after reading |

#### Content Structure (SEO + GEO Optimized)

```
Title: [Primary keyword near front] — [compelling hook]
Meta description: [150-160 chars, includes keyword, compelling reason to click]

## [H2: Direct answer to the search query — first 100 words]
   ← This "answer-first" paragraph is critical for AI search citations
   ← Include primary keyword in first 100 words

## [H2: Section covering main subtopic 1]
### [H3: Specific point]
### [H3: Specific point]

## [H2: Section covering main subtopic 2]
### [H3: Specific point]

## [H2: Practical section — how-to / examples / comparison]
   ← Tables, lists, step-by-step — structured data that AI can parse

## [H2: FAQ section]
   ← 3-5 real questions people ask (from "People Also Ask")
   ← Each Q&A is a snippet opportunity

## [H2: Conclusion + CTA]
```

#### SEO On-Page Checklist

For every piece of content, verify:

- ✅ Primary keyword in title tag (near front)
- ✅ Primary keyword in H1
- ✅ Primary keyword in first 100 words
- ✅ Primary keyword in URL slug
- ✅ Primary keyword in meta description
- ✅ Secondary keywords in H2/H3 headers
- ✅ Internal links to pillar page and 2-3 related articles
- ✅ External links to 2-3 authoritative sources
- ✅ Alt text on all images (descriptive, include keyword if natural)
- ✅ Meta description 150-160 characters, compelling
- ✅ URL slug is short, clean, keyword-rich (no stop words)
- ✅ Content is longer and more comprehensive than current page 1 results

#### GEO (Generative Engine Optimization) Checklist

To get cited by AI search engines (ChatGPT, Perplexity, Google SGE):

- ✅ **Answer-first structure**: Lead every section with a clear 1-2 sentence answer before expanding
- ✅ **FAQ format**: Include explicit Q&A sections (AI loves pulling these)
- ✅ **Structured data**: Use tables, numbered lists, and comparison matrices
- ✅ **Schema markup**: Implement FAQ schema, How-To schema, Article schema
- ✅ **Factual density**: Include specific numbers, statistics, dates — AI prefers citable facts
- ✅ **Source attribution**: Cite sources clearly — AI systems trust content that references authorities
- ✅ **Modular paragraphs**: Each paragraph should make sense standalone (AI extracts chunks)
- ✅ **Conversational hooks**: Include long-tail, question-based phrases that match how people prompt AI

---

## Phase 4: Content Strategy & Calendar

### Pillar + Cluster Publishing Plan

For each topic cluster, plan publishing order:

1. **Week 1-2**: Publish 2-3 cluster articles (build supporting content first)
2. **Week 3**: Publish pillar page (link to all cluster articles)
3. **Week 4+**: Publish remaining cluster articles, all linking to pillar
4. **Ongoing**: Update pillar page quarterly with new data/insights

### Content Calendar Template

| Week | Title | Keyword | Type | Cluster | Word Count | Status |
|------|-------|---------|------|---------|-----------|--------|
| | | | | | | |

### Content Types to Mix

| Type | Purpose | SEO Value | Frequency |
|------|---------|-----------|-----------|
| **How-to Guide** | Solve a specific problem | High (informational) | Weekly |
| **Comparison Post** | "X vs Y" | Very High (commercial) | Biweekly |
| **Listicle** | "Top 10 X for Y" | High (commercial) | Biweekly |
| **Pillar Guide** | Comprehensive topic coverage | Very High (authority) | Monthly |
| **Case Study** | Social proof + long-tail | Medium | Monthly |
| **Glossary / Definition** | "What is X" | High (informational, AI-friendly) | As needed |
| **Original Research** | Unique data, linkable | Very High (backlinks) | Quarterly |
| **Comparison Landing** | Product vs competitor | Very High (transactional) | As needed |

---

## Phase 5: Technical SEO Essentials

Quick checklist for content to perform:

### Must-Have Technical Foundation

- ✅ Site loads in < 2.5 seconds (Core Web Vitals LCP)
- ✅ Mobile-responsive design
- ✅ HTTPS enabled
- ✅ XML sitemap submitted to Google Search Console
- ✅ Robots.txt properly configured
- ✅ No duplicate content / canonical tags set
- ✅ Clean URL structure (no parameters, no dates in URLs)
- ✅ Internal linking structure reflects topic clusters
- ✅ Schema markup on key pages (Article, FAQ, How-To, Product)

### Free SEO Tools Reference

| Tool | URL | What It Does |
|------|-----|-------------|
| **Google Search Console** | search.google.com/search-console | Track rankings, clicks, indexing issues |
| **Google Analytics 4** | analytics.google.com | Traffic, user behavior, conversions |
| **Google Trends** | trends.google.com | Keyword trend data, seasonal patterns |
| **Ahrefs Webmaster Tools** | ahrefs.com/webmaster-tools | Free backlink checker, site audit |
| **AnswerThePublic** | answerthepublic.com | Find questions people ask about a topic |
| **AlsoAsked** | alsoasked.com | Map "People Also Ask" question trees |
| **Ubersuggest** | neilpatel.com/ubersuggest | Free keyword research (limited) |
| **PageSpeed Insights** | pagespeed.web.dev | Core Web Vitals testing |
| **Schema Markup Generator** | technicalseo.com/tools/schema-markup-generator | Generate structured data |
| **Rich Results Test** | search.google.com/test/rich-results | Validate structured data markup |
| **SparkToro** | sparktoro.com | Audience research — find where your audience hangs out |
| **Screaming Frog** | screamingfrog.co.uk (free up to 500 URLs) | Site crawl, find broken links, audit redirects |
| **DrLinkCheck** | drlinkcheck.com | Free broken link scanner |
| **Surfer SEO** | surferseo.com | Content optimization scoring (paid) |
| **Clearscope** | clearscope.io | Content grading against top results (paid) |

---

## Phase 6: E-E-A-T & Authority Building

In 2026, Google's ranking system heavily rewards E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness). This is especially critical for YMYL (Your Money Your Life) topics like fintech, health, and security.

### E-E-A-T Checklist

**Experience (NEW — added 2023, still critical):**
- ✅ Show first-hand experience with the topic (case studies, screenshots, personal results)
- ✅ Include "we built this" or "we tested this" language when applicable
- ✅ Use original images/screenshots instead of stock photos
- ✅ Share specific data from your own product/business

**Expertise:**
- ✅ Author bios on every article with credentials and links
- ✅ Use `ProfilePage` and `Person` schema markup for authors
- ✅ Authors should have published history on the topic (cross-link to other works)
- ✅ Technical content should be reviewed by subject matter experts

**Authoritativeness:**
- ✅ Build topical authority through comprehensive topic clusters (not random articles)
- ✅ Earn mentions and links from recognized industry sources
- ✅ Contribute guest posts to respected publications
- ✅ Get cited in industry reports, podcasts, and newsletters

**Trustworthiness:**
- ✅ HTTPS everywhere
- ✅ Clear privacy policy, terms of service, contact information
- ✅ Accurate, well-sourced content with citations
- ✅ Regular content updates (stale content signals low trust)
- ✅ Transparent about who you are (About page, team page, physical address if applicable)

### Off-Page Authority Building

| Tactic | Effort | Impact | How |
|--------|--------|--------|-----|
| **Guest posting** | Medium | High | Write for industry publications (not link farms) |
| **Original research** | High | Very High | Publish unique data/surveys — most linkable asset type |
| **HARO / Connectively** | Low | Medium | Respond to journalist queries for press mentions |
| **Podcast guesting** | Medium | Medium | Appear on niche podcasts, get show notes links |
| **Community presence** | Low | Medium | Answer questions on Reddit, Stack Overflow, Hacker News |
| **Open-source / free tools** | High | Very High | Build a free calculator, checker, or template that earns links |
| **Digital PR** | High | Very High | Newsworthy launches, data studies, contrarian takes |

---

## Phase 7: Content Maintenance & Optimization Cadence

SEO is not "publish and forget." Content decays. A maintenance rhythm is essential.

### Quarterly SEO Operating Rhythm

| Timeframe | Action |
|-----------|--------|
| **Weekly** | Publish new content per calendar; monitor Search Console for indexing issues |
| **Monthly** | Check top 20 pages for ranking changes; update any declining pages; review keyword cannibalization |
| **Quarterly** | Full content audit: identify top performers (double down), underperformers (update or consolidate), and dead weight (prune or redirect). Review and refresh pillar pages with new data/insights. Technical SEO audit (broken links, Core Web Vitals, mobile issues). Competitive analysis: what new content are competitors ranking for? |
| **Biannually** | Comprehensive site-wide audit; review topic cluster strategy; assess if new clusters are needed |

### Content Refresh Best Practices

When updating existing content:

- ✅ Update statistics, data points, and screenshots to current year
- ✅ Add new sections covering subtopics you missed originally
- ✅ Improve internal linking to newer articles
- ✅ Refresh meta title and description (test new CTR hooks)
- ✅ Add FAQ schema if not already present
- ✅ Re-submit URL to Google Search Console after major updates
- ✅ Add "Last updated: [date]" to build trust

### Content Pruning Decision Framework

For underperforming pages (no traffic for 6+ months):

| Signal | Action |
|--------|--------|
| Has backlinks but no traffic | Update and improve content; keep URL |
| Overlaps with a better-performing page | Merge content into the stronger page; 301 redirect old URL |
| No backlinks, no traffic, thin content | Delete and 301 redirect to most relevant remaining page |
| Outdated topic (no longer relevant) | Remove; redirect to parent topic page |

---

## Phase 8: GEO — Generative Engine Optimization (Deep Dive)

In 2026, AI search (ChatGPT, Perplexity, Google SGE/AI Overviews) drives a growing share of discovery. Being cited by AI requires specific optimization beyond traditional SEO.

### How AI Search Works (RAG Pipeline)

1. User prompts AI with a question
2. AI's retrieval system searches its index for relevant "chunks" of content
3. AI selects the most authoritative, structured, factual chunks
4. AI generates an answer, citing sources

**Your goal**: Make your content easy to chunk, retrieve, and cite.

### GEO Best Practices (Comprehensive)

**Content Structure for AI Retrieval:**

- ✅ **BLUF (Bottom Line Up Front)**: Start every section with a clear 1-2 sentence answer before expanding. AI extracts these first sentences as citations.
- ✅ **Modular paragraphs**: Each paragraph should make sense standalone. AI doesn't read your whole article — it extracts chunks.
- ✅ **Explicit definitions**: When introducing a concept, include a clear "X is Y" definition sentence. AI loves citing definitions.
- ✅ **Numbered/bulleted lists for processes**: AI extracts step-by-step lists much more reliably than prose.
- ✅ **Tables for comparisons**: Structured data is easier for AI to parse than paragraphs comparing things.
- ✅ **FAQ sections**: Explicit Q&A format maps directly to how users prompt AI. Include 5-10 real questions.

**Factual Density & Citability:**

- ✅ Include specific numbers, percentages, dates, and statistics — AI prefers citable facts over opinions
- ✅ Cite your sources clearly — AI trusts content that references authoritative sources
- ✅ Include original data when possible — unique stats are highly citable because no other source has them
- ✅ Use precise language over vague language ("reduces processing time by 40%" > "significantly faster")

**Technical GEO Optimization:**

- ✅ Implement FAQ schema, How-To schema, Article schema — structured data is the language LLMs understand best
- ✅ Use semantic HTML (proper H1-H6 hierarchy, `<article>`, `<section>`, `<aside>`)
- ✅ Include `Speakable` schema for key content you want voice assistants to read
- ✅ Use `Organization` and `Person` (author) schema to connect content to entities
- ✅ Ensure clean, fast-loading pages — AI crawlers skip slow or broken pages just like Google

**Content Types That Get Cited Most by AI:**

| Content Type | AI Citation Rate | Why |
|-------------|-----------------|-----|
| Definitive guides | Very High | Comprehensive coverage = trusted source |
| Comparison pages | Very High | Direct answers to "X vs Y" prompts |
| How-to tutorials | High | Step-by-step format maps to AI extraction |
| FAQ pages | High | Direct question-answer mapping |
| Original research / data | Very High | Unique data = must-cite source |
| Glossary / definitions | High | Clean definition sentences are highly extractable |
| Opinion / thought pieces | Low | AI prefers factual consensus over individual opinions |

### AI Search Bot Management

In 2026, manage which AI bots can crawl your content:

| Bot | Owner | Purpose | Allow? |
|-----|-------|---------|--------|
| Googlebot | Google | Traditional search + AI Overviews | ✅ Yes |
| OAI-SearchBot | OpenAI | ChatGPT search | ✅ Yes (visibility) |
| PerplexityBot | Perplexity | Perplexity search | ✅ Yes (visibility) |
| ClaudeBot | Anthropic | Claude search | ✅ Yes (visibility) |
| GPTBot | OpenAI | Training data | ⚠️ Optional (training, not search) |
| CCBot | Common Crawl | Training data | ⚠️ Optional |

Configure in `robots.txt` based on your comfort level with AI training vs. search visibility.

---

## Phase 9: Avoiding Common SEO Mistakes

### Critical Anti-Patterns

| Mistake | Why It Hurts | Fix |
|---------|-------------|-----|
| **Keyword stuffing** | Google penalizes unnatural keyword density | Write naturally; use LSI/semantic keywords |
| **Duplicate content** | Confuses Google on which page to rank | Use canonical tags; consolidate similar pages |
| **Keyword cannibalization** | Multiple pages competing for same keyword | One page per keyword; merge competing pages |
| **Ignoring search intent** | Content doesn't match what user actually wants | Analyze SERP: what type of content ranks? Match it. |
| **Thin content** | Not enough depth to satisfy the query | Aim for most comprehensive result on page 1 |
| **Neglecting mobile** | Google uses mobile-first indexing | Test every page on mobile; responsive design |
| **Slow page speed** | Directly hurts rankings + user experience | Target LCP < 2.5s, INP < 200ms, CLS < 0.1 |
| **No internal linking** | Google can't discover or understand site structure | Every page links to 3-5 related pages |
| **Stale content** | Signals low trust and outdated info | Refresh top pages quarterly with new data |
| **Ignoring AI search** | Missing growing share of discovery | Implement GEO best practices alongside SEO |
| **Building links from link farms** | Google penalizes manipulative link schemes | Earn links through quality content and outreach |
| **No schema markup** | Missing rich result opportunities + AI citability | Add Article, FAQ, How-To, Product schema |
| **Dates in URLs** | Makes content look old, hard to update | Use clean slugs: /topic-keyword/ not /2026/01/topic/ |
| **Ignoring Core Web Vitals** | INP has replaced FID as the responsiveness metric | Optimize Interaction to Next Paint, not just LCP |

### The "Corpus of Content" Model

Instead of publishing endlessly, focus on a **curated corpus of 50-200 high-quality pages**:

1. Identify your 4-6 topical pillars (aligned with business offerings)
2. Build 10-30 pages per pillar (pillar + clusters + supporting)
3. Invest more time updating existing pages than creating new ones
4. Prune anything that doesn't serve a clear purpose
5. Quality of the corpus > Quantity of pages

This model works because Google rewards depth and freshness over volume.

---

## Output Formats

Depending on what the user needs, deliver:

| Request | Output |
|---------|--------|
| "Build me a content strategy" | Topic clusters + keyword plan + content calendar |
| "Write a blog post about X" | Full article with SEO brief + content + meta tags |
| "Help me with keyword research" | Keyword plan table with volume, KD, intent |
| "Optimize this existing content" | Audit + specific recommendations + rewritten sections |
| "Create a pillar page" | Full pillar content (2000-4000 words) + cluster plan |
| "Help me rank in AI search" | GEO audit + content restructuring recommendations |
| "Do an SEO audit" | Technical checklist + content audit + priority fixes |

---

## Expert Principles

- **Search intent > Keywords.** A page that perfectly matches intent will beat a page stuffed with the right keyword.
- **10x content or don't bother.** If your article isn't meaningfully better than what's already on page 1, it won't rank.
- **Consistency > Volume.** Publishing 1 excellent article per week beats 5 mediocre ones.
- **Update > Create.** Refreshing a declining page often delivers faster ROI than writing new content.
- **Earn links, don't build them.** Original research, unique data, and genuinely useful tools earn natural backlinks.
- **Write for humans, optimize for machines.** If it reads like it was written for Google, it won't convert.
- **AI search is additive, not replacement.** Optimize for both Google AND AI search — they reward similar qualities (authority, clarity, structure).
- **New sites: go long-tail.** Target keywords with KD < 30 and volume 100-1000. Win small, then scale up.
- **BLUF everything.** Bottom Line Up Front — answer the question in the first 2 sentences, then expand. Works for both humans and AI.
- **Topical authority > Random articles.** 20 articles deeply covering one topic beats 100 articles scattered across 50 topics.
- **Schema is the language of AI.** If you're not using structured data, you're invisible to LLMs and missing rich result opportunities.
- **E-E-A-T is not optional.** Experience, Expertise, Authority, Trust — Google and AI both use these signals. Show your credentials, cite sources, be transparent.
- **INP is the new FID.** Interaction to Next Paint has replaced First Input Delay. Optimize for responsiveness, not just load time.
- **Manage your AI bot access.** Decide which AI crawlers can access your content. Allow search bots (OAI-SearchBot, PerplexityBot). Consider blocking training-only bots if you prefer.
- **The corpus model wins.** Focus on 50-200 excellent pages, not 1000 mediocre ones. Depth and freshness beat volume.

---

## Language Note

Conduct the entire process in the user's language. SEO content should be written in the language of the target market. For multilingual SEO, each language needs its own keyword research — never just translate keywords.

---

## Save Output

After presenting the SEO deliverables to the user, save them to the project folder:

1. Use the `Project Folder` path from the context block
2. Write the complete output to `{Project Folder}/05-seo.md` using the Write tool
3. File structure:
   ```
   ---
   project: {project-name}
   module: 05-seo
   date: {today's date}
   ---

   # SEO Content Strategy

   ## Topic Clusters
   [3-5 clusters with pillar + supporting topics]

   ## Keyword Plan
   [keywords by intent level: informational / navigational / commercial / transactional]

   ## Content Calendar
   [publishing plan per cluster]

   ## Content Type Mix

   ## Technical SEO Checklist

   ## E-E-A-T Action Items

   ## GEO (AI Search) Checklist
   ```
4. Confirm: "✅ Saved to `{project-name}/05-seo.md`"

---

## Workflow: Complete

After completing this skill, prompt the user:

> **Full branding workflow complete!** You now have all 5 foundations in place:
> ✅ Name + Domain (brand-naming)
> ✅ Positioning & Strategy (brand-positioning)
> ✅ Voice & Messaging (brand-voice)
> ✅ Visual Direction (brand-visual)
> ✅ SEO Content Strategy (seo-content)
>
> **Suggested next actions**: Register your domain on Cloudflare → brief a designer with your visual direction doc → start publishing your first pillar content.
