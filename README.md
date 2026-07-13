<div align="center">

# Awesome Generative Engine Optimization [![Awesome](https://awesome.re/badge-flat2.svg)](https://awesome.re)

> A curated list of tools, research, standards, and resources for **Generative Engine Optimization (GEO)** and **Answer Engine Optimization (AEO)** — getting your content found and *cited* by AI search engines like ChatGPT, Perplexity, Gemini, and Google AI Overviews.

</div>

Classic SEO optimizes for a ranked list of blue links. **GEO/AEO optimizes for being the source an AI engine quotes.** Different mechanics — entity resolution, citation confidence, structured data, retrievability — and a fast-moving, poorly-documented space. This list is an attempt to map it.

Maintained by [Nadia Mohamed](https://nadiamohamed.me), SEO Engineer (Technical SEO + GEO for SaaS & tech). Contributions welcome — see [Contributing](#contributing).

## Contents

- [What is GEO / AEO?](#what-is-geo--aeo)
- [Foundational reading](#foundational-reading)
- [Research & papers](#research--papers)
- [Standards & specifications](#standards--specifications)
- [Open-source tools](#open-source-tools)
- [Structured data & schema](#structured-data--schema)
- [Measurement & analytics](#measurement--analytics)
- [The AI engines](#the-ai-engines)
- [Bots & crawlers reference](#bots--crawlers-reference)
- [Guides & tutorials](#guides--tutorials)
- [Contributing](#contributing)

## What is GEO / AEO?

- **GEO (Generative Engine Optimization)** — optimizing content so it is retrieved, synthesized, and *cited* by generative engines (ChatGPT, Perplexity, Gemini, Copilot).
- **AEO (Answer Engine Optimization)** — the overlapping practice of optimizing to be the direct answer in answer engines and AI Overviews. Often used interchangeably with GEO; AEO leans toward the "featured answer" framing, GEO toward the "cited source" framing.
- **Why it's distinct from SEO** — you're not competing for position #1, you're competing to be one of a handful of sources an LLM trusts enough to attribute. That rewards clear entities, structured data, extractable claims, and demonstrable authority over keyword density and backlinks alone.

## Foundational reading

- [What is Generative Engine Optimization?](https://nadiamohamed.me/insights/structured-data-for-ai-search/) — structured data for AI search, a complete GEO guide.
- [How to Get Cited by Perplexity](https://nadiamohamed.me/insights/how-to-get-cited-by-perplexity/) — seven strategies for AI-search citation.
- [Google Search Central: AI features and your website](https://developers.google.com/search/docs/appearance/ai-features) — Google's own guidance on how content surfaces in AI Overviews.

## Research & papers

- [**GEO: Generative Engine Optimization**](https://arxiv.org/abs/2311.09735) — Aggarwal et al. (KDD 2024). The paper that named the field; introduces the GEO-bench benchmark and measures which content optimizations increase visibility in generative engine responses.
- [Search Engines in the Age of LLMs](https://arxiv.org/abs/2402.19472) — survey of retrieval-augmented generation as it applies to search.
- Track new work via [arXiv cs.IR](https://arxiv.org/list/cs.IR/recent) (Information Retrieval) and [cs.CL](https://arxiv.org/list/cs.CL/recent) (Computation & Language).

## Standards & specifications

- [**llms.txt**](https://llmstxt.org) — a proposed standard for a root-level Markdown file that gives LLMs a curated index of your site. → generate one with [llms-txt-generator](https://github.com/NadiaM22/llms-txt-generator).
- [Schema.org](https://schema.org) — the structured-data vocabulary AI engines parse for entities and relationships.
- [robots.txt & the emerging AI-crawler directives](https://developers.google.com/search/docs/crawling-indexing/robots/intro) — controlling which AI bots may crawl you.

## Open-source tools

> ⭐ = maintained by this list's author.

- ⭐ [**geo-audit-cli**](https://github.com/NadiaM22/geo-audit-cli) — score any URL on AI-search readiness (JSON-LD validity, entity coverage, citability, crawlability) from the command line or CI.
- ⭐ [**llms-txt-generator**](https://github.com/NadiaM22/llms-txt-generator) — build a spec-compliant `llms.txt` from your sitemap.
- ⭐ [**ai-referral-tracker**](https://github.com/NadiaM22/ai-referral-tracker) — isolate AI-search referral traffic from GA4 exports and server logs.
- ⭐ [**json-ld-schema-templates-seo**](https://github.com/NadiaM22/json-ld-schema-templates-seo) — production-ready JSON-LD templates optimized for AI citation.
- [Schema Markup Validator](https://validator.schema.org/) — official Schema.org validator.
- [Rich Results Test](https://search.google.com/test/rich-results) — Google's structured-data eligibility checker.

## Structured data & schema

- [Google: Structured data general guidelines](https://developers.google.com/search/docs/appearance/structured-data/sd-policies)
- [Schema.org full type hierarchy](https://schema.org/docs/full.html) — the complete vocabulary.
- High-signal types for AI citation: `Article`, `Person`, `Organization`, `FAQPage`, `HowTo`, `BreadcrumbList`, `WebSite`, `SoftwareApplication`. → templates in [json-ld-schema-templates-seo](https://github.com/NadiaM22/json-ld-schema-templates-seo).

## Measurement & analytics

- [How to Track AI Referral Traffic in GA4](https://nadiamohamed.me/insights/track-ai-referral-traffic/) — building an AI-search channel in GA4.
- ⭐ [ai-referral-tracker](https://github.com/NadiaM22/ai-referral-tracker) — do it from an export or log instead of hand-built segments.
- Server-log analysis matters here: many AI crawlers don't execute JavaScript, so they're invisible to client-side analytics but visible in raw logs.

## The AI engines

| Engine | Vendor | Notes |
| --- | --- | --- |
| [ChatGPT Search](https://openai.com/index/introducing-chatgpt-search/) | OpenAI | Cites sources inline; crawled by `OAI-SearchBot` / `ChatGPT-User`. |
| [Perplexity](https://www.perplexity.ai/) | Perplexity | Citation-first answer engine; `PerplexityBot`. |
| [Gemini](https://gemini.google.com/) | Google | Feeds and overlaps with Google AI Overviews. |
| [Google AI Overviews](https://developers.google.com/search/docs/appearance/ai-features) | Google | Synthesized answers atop the SERP. |
| [Copilot](https://copilot.microsoft.com/) | Microsoft | Built on Bing's index. |
| [Claude](https://claude.ai/) | Anthropic | Web search with citations. |

## Bots & crawlers reference

Know which bots to allow for AI-search visibility (distinct from training crawlers you may wish to block):

- **OpenAI** — `OAI-SearchBot` (search index), `ChatGPT-User` (live user fetches), `GPTBot` (training).
- **Perplexity** — `PerplexityBot`.
- **Google** — `Googlebot` (also powers AI Overviews), `Google-Extended` (training opt-out control).
- **Anthropic** — `ClaudeBot`, `Claude-User`.
- **Microsoft** — `bingbot`.

> Reference: each vendor publishes its user-agent list and IP ranges — verify against those before allow/deny-listing.

## Guides & tutorials

- [Structured Data for AI Search: Complete GEO Guide](https://nadiamohamed.me/insights/structured-data-for-ai-search/)
- [How to Get Cited by Perplexity: 7 Proven Strategies](https://nadiamohamed.me/insights/how-to-get-cited-by-perplexity/)
- [Free AEO Article Analyzer](https://nadiamohamed.me/ai-tools/) — score any article against 10 AI-readiness signals.

## Contributing

Found a tool, paper, or resource that belongs here? Contributions are very welcome.

1. Read the [contribution guidelines](CONTRIBUTING.md).
2. Add your link in the right section, alphabetically where it makes sense, with a one-line description of *why it matters for GEO/AEO* (not just what it is).
3. Open a pull request.

Keep it **awesome**: no link farms, no thin listicles, no paywalled-with-no-value content. Real tools, primary sources, and genuinely useful writing only.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](LICENSE)

To the extent possible under law, the contributors have waived all copyright and related rights to this work ([CC0 1.0](LICENSE)).
