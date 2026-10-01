# SEO AI Workflows

A practical prompt library and set of templates for using AI in day-to-day SEO work, and for improving how a brand shows up in AI-generated answers (GEO / AEO).

## What it does

This repo gives you tested, reusable building blocks:

- **Prompts** for common SEO tasks: content briefs, schema generation, AI visibility audits and internal linking. Each one comes with when to use it and how to review the output.
- **Templates**, starting with an `llms.txt` file you can adapt for your own site.

Everything is model-agnostic. The prompts work with ChatGPT, Claude, Gemini, Copilot, or an LLM API inside your own scripts.

## Why it matters

### How AI fits into SEO work

AI is useful in SEO when it speeds up work that a specialist then reviews. It's risky when it replaces that review. A good split:

| Let AI draft | Keep human-owned |
|---|---|
| First-pass content briefs and outlines | Search intent judgement and keyword prioritisation |
| JSON-LD from page content | Final schema validation and matching visible content |
| Internal link suggestions at scale | Deciding which pages matter commercially |
| Clustering keywords and summarising SERPs | Facts, prices, claims, legal and medical statements |
| Translating briefs between English and Arabic | Native review of Arabic copy and local nuance (UAE vs KSA) |

### AI search visibility (GEO / AEO)

Search is no longer just ten blue links. Google AI Overviews, ChatGPT search, Perplexity, Copilot and Gemini all answer questions directly and cite a handful of sources.

- **GEO (Generative Engine Optimization)** means making your brand and content easy for AI systems to find, understand, trust and cite.
- **AEO (Answer Engine Optimization)** means structuring content so it directly answers specific questions in a form that can be extracted.

Most of the groundwork is the same as good SEO: crawlable pages, clear entities, structured data, and authoritative, specific content. On top of that:

1. **Be extractable.** Put clear question-style headings first, then a direct answer, then the detail.
2. **Be an entity.** Use consistent name, address and descriptions across your site, Google Business Profile, Wikidata, LinkedIn and directories. Add `Organization` schema with `sameAs` links.
3. **Be cited.** Earn mentions on the third-party sites AI systems already trust in your niche: reviews, comparisons, industry media.
4. **Be accessible.** Don't accidentally block AI crawlers you want (GPTBot, ClaudeBot, PerplexityBot, Google-Extended) in robots.txt. Consider an `llms.txt`.
5. **Measure.** Track brand presence in AI answers for a fixed set of prompts over time. See [`prompts/ai-visibility-audit.md`](prompts/ai-visibility-audit.md).

## Folder structure

```
seo-ai-workflows/
├── README.md
├── LICENSE
├── prompts/
│   ├── content-brief.md                 # SEO content brief from a keyword + SERP notes
│   ├── schema-generation.md             # JSON-LD from page content
│   ├── ai-visibility-audit.md           # Check brand presence in AI answers
│   └── internal-linking-suggestions.md  # Contextual internal link ideas
└── templates/
    ├── llms.txt                         # Example llms.txt for a multi-region site
    └── llms-txt-guide.md                # What llms.txt is and how to fill in the template
```

## How to use it

1. Open the prompt file that matches your task.
2. Copy the prompt block and replace every `{{PLACEHOLDER}}` with your own inputs.
3. Paste it into your AI tool of choice. For long inputs such as full page content, use a model with a large context window.
4. Review the output with the checklist under **Reviewing the output** in each file. Don't skip this step.
5. Save prompts that work well for your niche, and version them here like code.

**Tips that apply to every prompt**

- Give the model real source material (SERP notes, page copy, product data) and tell it to use *only* that material for facts.
- Ask for a fixed output format (table, JSON, Markdown headings) so the result is easy to review and reuse.
- For GCC sites, say which market and language you mean: `en-ae`, `ar-ae`, `en-sa` or `ar-sa`. Currency (AED vs SAR), spelling and terminology differ.
- Never paste confidential client data into tools that aren't approved for it.

## Example output

A shortened example from `prompts/content-brief.md` for the keyword *"commercial cleaning services dubai"* (market `en-ae`):

```markdown
## Brief: Commercial Cleaning Services in Dubai

Primary keyword: commercial cleaning services dubai
Search intent: Commercial, with comparison and local service-provider intent
Target page type: Service landing page
Suggested title: Commercial Cleaning Services in Dubai | Example Co
Suggested H1: Commercial Cleaning Services in Dubai

### Outline
H2: Commercial cleaning services we offer in Dubai
H2: Industries we serve (offices, retail, warehouses, clinics)
H2: How our commercial cleaning contracts work
H2: Pricing: what affects the cost (AED)
H2: Areas covered (Business Bay, DIFC, JLT, Al Quoz)
H2: FAQs

### Questions to answer directly (AEO)
- How much does commercial cleaning cost in Dubai?
- Do you need a Dubai Municipality-approved cleaning company?
```

## License

MIT
