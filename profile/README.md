# Angeo — AI Engine Optimization for Magento 2

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![PHP](https://img.shields.io/badge/PHP-8.1%20%E2%80%93%208.5-8892BF.svg)
![Magento 2](https://img.shields.io/badge/Magento-2.4.6%20%E2%80%93%202.4.9-orange.svg)
![Adobe Commerce](https://img.shields.io/badge/Adobe%20Commerce-compatible-red.svg)
![Hyvä](https://img.shields.io/badge/Hyv%C3%A4-compatible-brightgreen.svg)

**Open-source modules that make Magento 2 stores visible to ChatGPT (OpenAI), Gemini (Google), Perplexity and Claude (Anthropic) — and let AI agents search, check and buy from them.**

Most Magento stores are invisible to AI by default. AI crawlers are blocked, product data is not structured, and there is no machine-readable way for an agent to shop. When an assistant recommends products in your category, it sends buyers to the stores it can read.

Angeo fixes the technical signals AI systems rely on: crawler access, `llms.txt`, JSON-LD schema, product feeds, and the agentic commerce protocols (UCP and MCP).

---

## About Angeo

Angeo is a Magento 2 AEO studio built around one question: when an AI assistant recommends products in your category, is your store in the answer?

We build open-source modules for the signals behind that answer and run them on our own demo store every day. Angeo is a member of Anthropic's Claude Partner Network (Registered tier) and builds Magento AI commerce tooling with Claude, OpenAI and Google AI technologies.

Definitions of the concepts behind this work live in our [AI Commerce glossary](https://angeo.dev/ai-commerce-stack-definition/).

---

## Why this matters now

AI assistants are becoming product discovery engines. People ask:

- "What's the best standing desk under €500?"
- "Which cast iron pan works on induction?"
- "Where can I buy replacement laptop batteries that ship to the EU?"

The assistant gives one or two answers — not a page of links. If AI systems cannot reach and understand your catalog, your products are never considered. SEO decides your Google ranking. AEO decides whether you are in the AI's answer.

---

## What AI systems need

Before an AI assistant can recommend or sell a product, four things must work:

1. **Crawlable** — AI bots can reach the store, and the WAF/CDN does not block them (robots.txt, bot verification)
2. **Discoverable** — the catalog is mapped for machines (llms.txt, Markdown mirrors, sitemap)
3. **Understandable** — products carry linked structured data (Product, Offer, merchant policies as JSON-LD)
4. **Transactable** — agents can query the catalog and check out (UCP profile, MCP server, product feeds)

Angeo modules cover all four layers.

---

## What is AEO?

AEO (AI Engine Optimization) is the technical layer that makes your store readable by AI systems. SEO is about ranking pages. AEO is about being included in answers.

Other people call it Generative Engine Optimization (GEO), AI Search Optimization, AI Visibility or LLM Optimization. The work is the same: get a catalog discovered, understood and recommended by AI assistants.

---

## Why merchants use Angeo

- **Open-source and MIT licensed** — inspect every signal, no black box
- **Built for Magento 2** — not a generic SEO plugin
- **Adobe Commerce and Mage-OS compatible**
- **Hyvä compatible** — frontend output works with Hyvä themes
- **Multi-store ready** — per-store-view configuration where it matters
- **Built on open standards** — llms.txt, schema.org, UCP, MCP, ACP, RFC 9309, RFC 9421
- **Actively maintained** — updated as protocols and AI surfaces change

---

## Module suite

Start with the audit module. It scores your store and tells you which modules you need. Install only what you need. All repositories are public and MIT licensed.

### Diagnose

| Module | What it does |
| --- | --- |
| [module-aeo-audit](https://github.com/angeo-dev/module-aeo-audit) | One CLI command scores 20 AEO signals in two layers: **configuration** (robots.txt, llms.txt v2, llms.jsonl, sitemap, Product / Organization / FAQ schema, merchant policies, UCP profile, AI feed, canonical + hreflang, Open Graph, well-known endpoints, agents.md, A2A agent card, Core Web Vitals) and **evidence** (WAF reality check with real AI crawler user agents, actual AI crawler activity). Exact fix commands, score trend dashboard, `--fail-on` CI gate |
| [module-aeo-brand-visibility](https://github.com/angeo-dev/module-aeo-brand-visibility) | Asks ChatGPT, Claude, Perplexity, Gemini and Groq real shopping questions and scores whether they name, cite and recommend your store. Repeated sampling with confidence intervals, competitor tracking, share of voice, multilingual. Plugs into the audit as a live signal |

### Make the store readable

| Module | What it does |
| --- | --- |
| [module-robots-txt-aeo](https://github.com/angeo-dev/module-robots-txt-aeo) | Adds rules for 20+ AI crawlers (OpenAI, Anthropic, Google, Perplexity, Apple, Meta, Amazon, Mistral and more) without overwriting your robots.txt. Lossless RFC 9309 parsing, Content-Usage signals, and crawler verification via Web Bot Auth (RFC 9421) and vendor IP ranges |
| [module-llms-txt](https://github.com/angeo-dev/module-llms-txt) | Generates `llms.txt`, `llms-full.txt` and `llms.jsonl` per llmstxt.org v2, plus on-the-fly Markdown page mirrors. MSI-aware stock, multi-store, CLI, cron. Also on the Adobe Commerce Marketplace |
| [module-rich-data](https://github.com/angeo-dev/module-rich-data) | Publishes one linked JSON-LD `@graph` per page: Product, Offer, Organization, BreadcrumbList, ItemList, FAQPage, WebSite, return and shipping policies, GTIN/MPN |
| [module-ai-description-updater](https://github.com/angeo-dev/module-ai-description-updater) | Writes and updates product descriptions with OpenAI, Claude, Gemini or Groq. Bulk CLI, cron, Google Sheets source, dry-run, per-store prompts |

### Let AI agents shop

| Module | What it does |
| --- | --- |
| [module-ucp](https://github.com/angeo-dev/module-ucp) | Universal Commerce Protocol profile at `/.well-known/ucp`, spec 2026-08-25: JWK signing keys, required capability schemas, authority binding, inbound RFC 9421 signature verification, per-store-view toggles |
| [module-ucp-catalog](https://github.com/angeo-dev/module-ucp-catalog) | The UCP `catalog.search` and `catalog.lookup` endpoints your profile advertises, validated against the official UCP JSON Schemas |
| [module-mcp-server](https://github.com/angeo-dev/module-mcp-server) | MCP server for Magento 2: gives Claude, ChatGPT and Gemini agents live, rate-limited, read-only access to search, product cards, categories and store info. Includes an "Add to Claude" widget |
| [module-mcp-checkout](https://github.com/angeo-dev/module-mcp-checkout) | Six MCP tools that take an agent from search to a placed guest order, with server-side guardrails (total caps, payment whitelist, rate limits) and pay-by-link handoff (Stripe, Mollie, Adyen) |
| [module-openai-product-feed](https://github.com/angeo-dev/module-openai-product-feed) | ACP-format product feed for ChatGPT product discovery. All product types, batch stock and category resolvers |
| [module-openai-product-feed-api](https://github.com/angeo-dev/module-openai-product-feed-api) | ACP REST endpoints for the feed: feeds, products with pagination and variants, promotions |

All Magento modules: MIT · PHP 8.1–8.5 · Magento 2.4.6–2.4.9 · Adobe Commerce compatible.

▶ See an AI agent place a real order on our demo store: [MCP checkout demo](https://www.youtube.com/watch?v=rjGcpQuBSQg)

### Beyond Magento modules

| Repository | What it is |
| --- | --- |
| [claude-for-commerce-magento](https://github.com/angeo-dev/claude-for-commerce-magento) | Magento 2 implementation of `StorefrontBackend` for Anthropic's [Claude Commerce Agents](https://github.com/anthropics/commerce-agents) blueprint — the Magento counterpart to Shopify's examples |
| [skills](https://github.com/angeo-dev/skills) | Agent Skills for AEO: audit any site for AI crawler access, llms.txt and structured data. A Claude Code plugin marketplace |
| [awesome-magento-aeo](https://github.com/angeo-dev/awesome-magento-aeo) | Curated list of modules, specifications and tools that make Magento and Adobe Commerce stores readable and transactable by AI |

---

## Quick start

⭐ Star the [audit repo](https://github.com/angeo-dev/module-aeo-audit) to follow updates.

```bash
# Check your store's current AEO score
composer require angeo/module-aeo-audit
bin/magento setup:upgrade
bin/magento angeo:aeo:audit
```

The report shows your score and the exact modules that fix each gap:

```
  AEO Score: [████████████████░░░░] 81% — Good
  ✓ Pass: 12  ⚠ Warn: 3  ✗ Fail: 1

  Critical fixes needed:
  → Install angeo/module-openai-product-feed and register at chatgpt.com/merchants

  💡 Fix with angeo modules:
     composer require angeo/module-openai-product-feed angeo/module-openai-product-feed-api
     composer require angeo/module-ucp
```

Not technical? Use the free web audit → [angeo.dev/ai-magento-audit/](https://angeo.dev/ai-magento-audit/)

---

## AEO score interpretation

There is no official AEO standard. These bands describe how strong the implementation is across the signals Angeo measures — not compliance with an external spec.

| Score | Status | Typical situation |
| --- | --- | --- |
| 0–25% | Needs improvement | Default Magento install. AI crawlers blocked. |
| 26–50% | Needs improvement | Some fixes applied. Schema or feed missing. |
| 51–75% | Moderate | Core signals in place. Agent-facing layer missing. |
| 76–90% | Good | Strong foundation. Minor gaps. |
| 91–100% | Excellent | Strong across all measured signals. Ready for AI agents. |

---

## Where to get the modules

- [Packagist](https://packagist.org/packages/angeo/) — all packages
- [Mage-OS Extension Directory](https://directory.mage-os.org/) — listed modules with quality badges
- Adobe Commerce Marketplace — AEO LLMs Txt Generator

---

## Learn more

**AI Commerce glossary:**

- [AI Commerce Stack](https://angeo.dev/ai-commerce-stack-definition/) — the five layers, from structured data to AI transactions
- [Magento AEO](https://angeo.dev/magento-aeo-definition/) — making a Magento store readable by AI
- [AI Commerce Visibility](https://angeo.dev/ai-commerce-visibility-definition/) — how AI selects which stores to recommend
- [Agentic Commerce Protocols (ACP, UCP)](https://angeo.dev/agentic-commerce-protocol-definition/) — how AI agents complete purchases

**Tools and guides:**

- [angeo.dev](https://angeo.dev) — documentation and guides
- [Free AEO self-assessment](https://angeo.dev/ai-magento-audit/) — web audit, no CLI needed
- [Magento 2 AEO Guide 2026](https://angeo.dev/magento-2-aeo-guide/) — full signal reference
- [Magento AEO scan case study](https://angeo.dev/aeo-scan-case-study/) — results from scanning live Magento stores
