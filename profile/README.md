# Angeo — AI Engine Optimization for Magento 2

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![PHP](https://img.shields.io/badge/php-%3E%3D8.2-8892BF.svg)
![Magento 2](https://img.shields.io/badge/Magento-2.4%2B-orange.svg)
![Adobe Commerce](https://img.shields.io/badge/Adobe%20Commerce-compatible-red.svg)

**Open-source AEO (AI Engine Optimization) modules that make Magento stores visible in ChatGPT, Gemini, and Perplexity.**

Most Magento stores are invisible to AI by default. If ChatGPT or Perplexity recommend products in your category, they're likely sending users to your competitors — not because of SEO, but because your store isn't readable by AI systems.

A suite of open-source modules that fix the technical signals AI systems rely on. Default Magento 2 scores ~25% on AEO signals, based on audits across dozens of Magento stores using a 9-signal AEO framework. Most stores can reach a high AEO score in under 90 minutes.

---

## What is AEO?

AEO (AI Engine Optimization) is the technical layer that makes your store readable by AI systems.

If SEO is about ranking pages, AEO is about being included in answers.

Unlike SEO, which optimizes for rankings, AEO ensures your products can be discovered, understood, and recommended by ChatGPT, Gemini, and Perplexity.

Key signals: robots.txt AI bot access, llms.txt catalog map, Product JSON-LD schema with `offers.availability`, product feeds required for ChatGPT Shopping (ACP format).

AI-driven shopping is growing fast, and most stores haven't adapted yet. That window won't stay open.

---

## Use cases

- Losing high-intent buyers from ChatGPT / AI recommendations
- Magento stores not appearing in ChatGPT or Perplexity answers
- Preparing for ChatGPT Shopping / AI-driven product discovery
- Fixing incomplete product schema (availability, price, variants)
- Making product catalogs accessible to AI crawlers
- Registering an ACP product feed with OpenAI's merchant program

---

## Module suite

Start with the audit module — it tells you exactly which modules your store needs. Install only what you need — or use the full stack for maximum coverage.

**Core signals covered:**
- **Crawlability** — robots.txt AI bot access
- **Structure** — llms.txt catalog map + llms.jsonl
- **Product data** — JSON-LD schema with offers.availability
- **Distribution** — ACP product feeds for ChatGPT Shopping

| Module | Signal | What it does |
|---|---|---|
| [module-aeo-audit](https://github.com/angeo-dev/module-aeo-audit) | Diagnostic | Checks all 9 AEO signals, Score Trend dashboard, CI support |
| [module-robots-txt-aeo](https://github.com/angeo-dev/module-robots-txt-aeo) | #1 robots.txt | Injects AI crawler rules (ChatGPT, Gemini, Perplexity, Claude) |
| [module-llms-txt](https://github.com/angeo-dev/module-llms-txt) | #2 llms.txt | Generates llms.txt and llms.jsonl per llmstxt.org spec |
| [module-rich-data](https://github.com/angeo-dev/module-rich-data) | #3 #5 schema | Product JSON-LD with offers.availability + FAQPage schema |
| [module-openai-product-feed](https://github.com/angeo-dev/module-openai-product-feed) | #4 ACP feed | Product feed for ChatGPT Shopping registration (ACP format) |
| [module-openai-product-feed-api](https://github.com/angeo-dev/module-openai-product-feed-api) | #4 API | REST API endpoints for ACP feed submission |

All modules: MIT licensed · PHP 8.2+ · Magento 2.4+ · Adobe Commerce Cloud compatible · Hyvä theme compatible

---

## Quick start

⭐ Star this repo to track updates

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

| Score | Status | Typical situation |
|---|---|---|
| 0–25% | Needs Improvement | Default Magento install. AI crawlers blocked. |
| 26–50% | Needs Improvement | Some fixes applied. Schema or feed missing. |
| 51–75% | Moderate | Core signals in place. Feed not registered. |
| 76–90% | Good | Strong foundation. Minor gaps. |
| 91–100% | Excellent | Full AEO compliance. ChatGPT Shopping active. |

---

## Links

- [angeo.dev](https://angeo.dev) — documentation and guides
- [Free AEO self-assessment](https://angeo.dev/ai-magento-audit/) — web-based audit, no CLI required
- [Magento 2 AEO Guide 2026](https://angeo.dev/magento-2-aeo-guide/) — complete signal reference
- [Packagist](https://packagist.org/packages/angeo/) — all packages
