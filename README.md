# brand-builder

[![GitHub stars](https://img.shields.io/github/stars/Phlegonlabs/product-brand?style=flat-square)](https://github.com/Phlegonlabs/product-brand/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/Phlegonlabs/product-brand?style=flat-square)](https://github.com/Phlegonlabs/product-brand/network)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

A complete, 5-step brand-building skill for Claude Code — from naming to SEO content.

## What is this?

**brand-builder** is a Claude Code skill that turns your AI assistant into a senior brand strategist. It gives Claude a structured, professional-grade branding workflow so you can build a complete brand identity without hiring an agency.

The methodology is inspired by [Lexicon Branding](https://www.lexiconbranding.com/) — the naming firm behind **Vercel**, **BlackBerry**, **Azure**, **Sonos**, **Dasani**, and **OnStar**. Their three-cognitive-perspective naming process (semantic, acoustic, structural) is baked directly into Step ①.

### Who is this for?

- **Founders and indie hackers** who need a real brand, not a generic one
- **Developers** shipping a SaaS, CLI tool, or open-source project
- **Product teams** repositioning or launching a new product line
- **Designers and consultants** who want a structured branding workflow they can run inside Claude Code

### What it produces

Running all 5 steps gives you a complete brand package:

- **A registrable name** — 10 scored candidates (real words + engineered), domain-checked across `.com`, `.io`, `.xyz`, `.sh`
- **A positioning statement** — who you're for, what you do, and why you win
- **Voice and messaging** — tagline, messaging hierarchy, tone guidelines
- **Visual identity direction** — color palette, typography choices, logo brief
- **SEO content strategy** — topic clusters, keyword plan, content calendar

Each step builds on the previous one. You can also jump directly to any module if you already have a name or positioning.

---

## Install

```bash
npx skills add Phlegonlabs/product-brand
```

Or install globally (available in all projects):

```bash
npx skills add Phlegonlabs/product-brand -g
```

---

## Usage

Once installed, trigger with any branding-related request in Claude Code:

```
brand my product
name my company
I need a tagline
brand positioning
visual identity
SEO content strategy
```

Or invoke directly:

```
/brand-builder
```

Claude will guide you through a structured interview for each step, then generate the deliverables and save them to a project folder in your repo.

---

## What's included

| Step | Module | Output |
|------|--------|--------|
| ① | **Naming** | 10 registrable name candidates + domain strategy |
| ② | **Positioning** | Positioning statement, value prop, competitive map |
| ③ | **Voice & Messaging** | Tagline, messaging hierarchy, voice guidelines |
| ④ | **Visual Identity** | Color palette, typography, logo brief |
| ⑤ | **SEO Content** | Topic clusters, keyword plan, content calendar |

---

## How it works

The skill loads a reference module for each step. Each module contains:

1. **A discovery interview** — Claude asks structured questions about your product, audience, and market using interactive multiple-choice prompts
2. **A professional framework** — the same methodology used by top branding firms, applied to your specific answers
3. **Scored output** — candidates and options are ranked, not just listed, so you know which to prioritize
4. **A saved deliverable** — results are written to `{project-name}/0X-module-name.md` in your repo

Outputs from each step are passed forward as context, so later steps (positioning, voice, SEO) are informed by earlier decisions. No re-asking what you already answered.

---

## Domain checking

The naming module (Step ①) automatically checks domain availability across four primary TLDs:

- `.com` — strongest trust signal (Cloudflare Registrar, ~$10/yr)
- `.io` — developer standard (Cloudflare, ~$34/yr)
- `.xyz` — modern default, high availability (Cloudflare, ~$10/yr)
- `.sh` — short, dev-friendly (Namecheap / Porkbun, ~$29–40/yr)

> `.sh` domains are not available on Cloudflare — use [Namecheap](https://namecheap.com) or [Porkbun](https://porkbun.com).

---

## Requirements

Requires [Claude Code](https://claude.ai/code).

---

## License

[MIT](LICENSE)
