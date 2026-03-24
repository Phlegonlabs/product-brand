# brand-builder

A complete, 5-step brand-building skill for Claude Code — from naming to SEO content. Built on Lexicon Branding methodology (the firm behind Vercel, BlackBerry, Azure, Sonos).

## Install

```bash
npx skills add <owner>/product-brand
```

Or install globally (available in all projects):

```bash
npx skills add <owner>/product-brand -g
```

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

## What's included

| Step | Module | Output |
|------|--------|--------|
| ① | **Naming** | 10 registrable name candidates + domain strategy |
| ② | **Positioning** | Positioning statement, value prop, competitive map |
| ③ | **Voice & Messaging** | Tagline, messaging hierarchy, voice guidelines |
| ④ | **Visual Identity** | Color palette, typography, logo brief |
| ⑤ | **SEO Content** | Topic clusters, keyword plan, content calendar |

Each step builds on the previous one. You can also jump directly to any module.

## Domain checking

The naming module (Step ①) automatically checks domain availability across four primary TLDs:

- `.com` — strongest trust signal (Cloudflare Registrar, ~$10/yr)
- `.io` — developer standard (Cloudflare, ~$34/yr)
- `.xyz` — modern default, high availability (Cloudflare, ~$10/yr)
- `.sh` — short, dev-friendly (Namecheap / Porkbun, ~$29–40/yr)

> `.sh` domains are not available on Cloudflare — use [Namecheap](https://namecheap.com) or [Porkbun](https://porkbun.com).

## Supports Claude Code

Requires: [Claude Code](https://claude.ai/code)

## License

MIT
