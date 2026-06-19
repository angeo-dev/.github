# Angeo — AI Engine Optimization for Magento 2

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![PHP](https://img.shields.io/badge/php-%3E%3D8.1-8892BF.svg)
![Magento 2](https://img.shields.io/badge/Magento-2.4%2B-orange.svg)
![Adobe Commerce](https://img.shields.io/badge/Adobe%20Commerce-compatible-red.svg)

**Open-source AEO (AI Engine Optimization) modules that make Magento stores visible in ChatGPT (OpenAI), Gemini (Google), Perplexity, and Claude (Anthropic).**

Most Magento stores are invisible to AI by default. As AI shopping and agentic commerce become real discovery channels, the stores that win are the ones AI systems can read. If ChatGPT or Perplexity recommend products in your category, they're likely sending users to your competitors — not because of SEO, but because your store isn't readable by AI systems.

A suite of open-source modules that fix the technical signals AI systems rely on. Default Magento 2 installations typically score low on the AI-readiness signals measured by Angeo's 15-signal AEO framework. Most stores can significantly improve their AEO score in under 90 minutes.

---

## About Angeo

Angeo is a Magento 2 AEO studio focused on one question: when an AI assistant recommends products in your category, is your store in the answer? We build open-source modules that fix the structured-data, crawler-access, and feed signals that ChatGPT, Gemini, Perplexity, and Claude rely on — and we run them in our own work every day.

Angeo participates in Anthropic's Claude Partner Network (Registered tier) and builds Magento AI Commerce tooling using Claude alongside OpenAI and Google AI technologies.

Canonical definitions of the concepts behind this work live in our [AI Commerce glossary](https://angeo.dev/ai-commerce-stack-definition/).

---

## Why this matters now

AI assistants are becoming product discovery engines. Instead of browsing dozens of search results, users increasingly ask:

- "What's the best standing desk under €500?"
- "Which cast iron pan should I buy for induction?"
- "Where can I get replacement laptop batteries that ship to the EU?"

The assistant returns one or two specific recommendations — not a page of links. If AI systems cannot access and understand your catalog, your products may never be considered for those answers. SEO decides your Google ranking; AEO decides whether you exist inside the AI's response.

---

## What AI systems need

Before an AI assistant can recommend a product, four things usually need to happen:

1. **Crawlable** — AI bots can reach the store (robots.txt)
2. **Discoverable** — the catalog is mapped for machines (llms.txt, sitemap)
3. **Understandable** — products carry structured data (Product + Offer JSON-LD)
4. **Transactable** — the merchant exposes machine-readable commerce signals (ACP / UCP feeds)

Angeo modules focus on those technical foundations.

---

## What is AEO?

AEO (AI Engine Optimization) is the technical layer that makes your store readable by AI systems. If SEO is about ranking pages, AEO is about being included in answers.

It's the same idea other people call Generative Engine Optimization (GEO), AI Search Optimization, AI Visibility, or LLM Optimization — different names for the work of getting a catalog discovered, understood, and recommended by ChatGPT (OpenAI), Gemini (Google), Perplexity, and Claude (Anthropic).

Key signals: robots.txt AI bot access, an llms.txt catalog map, Product JSON-LD schema with `offers.availability`, and the product feeds required for ChatGPT Shopping (Agentic Commerce Protocol format).

AI-driven shopping is growing fast, and most stores haven't adapted yet. That window won't stay open.

---

## Why merchants use Angeo

- **Open-source and MIT licensed** — inspect every signal, no black box
- **Built specifically for Magento 2** — not a generic SEO plugin
- **Adobe Commerce compatible** — Open Source and Adobe Commerce both supported
- **Hyvä theme compatible** — works with modern Magento frontends
- **Multi-store ready** — per-store-view configuration where it matters
- **Based on emerging AI commerce standards** — ACP, UCP, llms.txt, schema.org
- **Actively maintained** — updated as the protocols and AI surfaces evolve

---

## Use cases

- Losing high-intent buyers from ChatGPT / AI recommendations
- Magento stores not appearing in ChatGPT, Perplexity, or Claude answers
- Preparing for ChatGPT Shopping / AI-driven product discovery
- Fixing incomplete product schema (availability, price, variants)
- Making product catalogs accessible to AI crawlers
- Registering an ACP product feed with OpenAI's merchant program
- Publishing a Universal Commerce Protocol (UCP) profile for Google's AI surfaces

---

## Module suite

Start with the audit module — it scores 15 AEO signals and tells you exactly which modules your store needs. Install only what you need, or use the full stack for maximum coverage. All repositories are public and MIT-licensed.

| Module | Role | What it does |
| --- | --- | --- |
| [module-aeo-audit](https://github.com/angeo-dev/module-aeo-audit) | Diagnostic | Scores 15 AEO signals — AI bots in robots.txt, llms.txt + llms.jsonl, Product/Organization/FAQ schema, return & shipping policies, sitemap.xml, UCP profile, AI product feed, OG tags, canonical + hreflang, JSON-LD quality, well-known endpoint |
| [module-aeo-brand-visibility](https://github.com/angeo-dev/module-aeo-brand-visibility) | Live audit | Queries ChatGPT, Claude, Perplexity, Gemini & Groq with brand-probing prompts; scores real-world AI recall, citation rate & recommendation presence. Extends the audit as a 16th signal |
| [module-robots-txt-aeo](https://github.com/angeo-dev/module-robots-txt-aeo) | Crawlability | Injects AI crawler rules (OAI-SearchBot, GPTBot, ChatGPT-User, PerplexityBot, Google-Extended, ClaudeBot, anthropic-ai, Claude-User, Applebot, Amazonbot, Meta-ExternalAgent) without overwriting your existing robots.txt |
| [module-llms-txt](https://github.com/angeo-dev/module-llms-txt) | Structure | Generates spec-compliant llms.txt and llms-full.txt per llmstxt.org, plus streaming JSONL for vector indexing. Multi-store, CLI, cron, Page Builder-aware |
| [module-rich-data](https://github.com/angeo-dev/module-rich-data) | Schema | Injects spec-compliant Product, Organization, BreadcrumbList, FAQPage, and WebSite JSON-LD |
| [module-openai-product-feed](https://github.com/angeo-dev/module-openai-product-feed) | Feed | AI-powered product feed for ChatGPT Shopping registration |
| [module-openai-product-feed-api](https://github.com/angeo-dev/module-openai-product-feed-api) | ACP API | Full 6-endpoint ACP REST surface: feeds, products (with pagination & variants), promotions. DB-persisted feeds |
| [module-openai-instant-checkout](https://github.com/angeo-dev/module-openai-instant-checkout) | ACP checkout | Agentic Commerce Protocol Instant Checkout — AI-driven purchases via a custom Agentic Checkout API |
| [module-ucp](https://github.com/angeo-dev/module-ucp) | UCP profile | Spec-compliant Universal Commerce Protocol profile generator. Serves `/.well-known/ucp` at protocol 2026-04-08 with ECDSA P-256 signing keys and per-store-view capability toggles |
| [module-ai-description-updater](https://github.com/angeo-dev/module-ai-description-updater) | Content | Generates and updates product descriptions using OpenAI, Anthropic Claude, or Google Gemini; Google Sheets source, dry-run, per-store prompts, cron |

All modules: MIT licensed · PHP 8.1+ · Magento 2.4+ · Adobe Commerce compatible · Hyvä theme compatible

---

## Quick start

⭐ Star the [audit repo](https://github.com/angeo-dev/module-aeo-audit) to track updates

```bash
# Check your store's current AEO score
composer require angeo/module-aeo-audit
bin/magento setup:upgrade
bin/magento angeo:aeo:audit
```

Each failed signal outputs the exact `composer require` command to fix it:

```
✗ FAIL  robots.txt — OAI-SearchBot blocked
        → Fix: composer require angeo/module-robots-txt-aeo

✗ FAIL  llms.txt — not found
        → Fix: composer require angeo/module-llms-txt

✗ FAIL  Product Schema — missing offers.availability
        → Fix: composer require angeo/module-rich-data
```

Not technical? Use the web audit → [angeo.dev/ai-magento-audit/](https://angeo.dev/ai-magento-audit/)

---

## AEO score interpretation

There is no official AEO standard, so these bands describe implementation strength across the signals Angeo measures — not compliance with an external spec.

| Score | Status | Typical situation |
| --- | --- | --- |
| 0–25% | Needs improvement | Default Magento install. AI crawlers blocked. |
| 26–50% | Needs improvement | Some fixes applied. Schema or feed missing. |
| 51–75% | Moderate | Core signals in place. Feed not registered. |
| 76–90% | Good | Strong foundation. Minor gaps. |
| 91–100% | Excellent | Strong AEO implementation across all measured signals. Ready for ChatGPT Shopping and AI commerce integrations. |

---

## Learn more

**AI Commerce glossary — canonical definitions:**

- [AI Commerce Stack](https://angeo.dev/ai-commerce-stack-definition/) — the five layers, from structured data to AI transactions
- [Magento AEO](https://angeo.dev/magento-aeo-definition/) — making a Magento store readable by AI
- [AI Commerce Visibility](https://angeo.dev/ai-commerce-visibility-definition/) — how AI selects which stores to recommend
- [Agentic Commerce Protocol (ACP & UCP)](https://angeo.dev/agentic-commerce-protocol-definition/) — how AI agents complete purchases

**Tools & guides:**

- [angeo.dev](https://angeo.dev) — documentation and guides
- [Free AEO self-assessment](https://angeo.dev/ai-magento-audit/) — web-based audit, no CLI required
- [Magento 2 AEO Guide 2026](https://angeo.dev/magento-2-aeo-guide/) — complete signal reference
- [Packagist](https://packagist.org/packages/angeo/) — all packages
