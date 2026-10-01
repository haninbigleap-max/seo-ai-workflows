# llms.txt: Explanation and How to Use the Template

## What is llms.txt?

`llms.txt` is a proposed standard ([llmstxt.org](https://llmstxt.org/)): a Markdown file at the root of your site (`https://example.com/llms.txt`) that gives large language models a short, curated summary of your site and links to the most useful pages.

Think of it as a cross between a sitemap and an "about us" written for machines. A sitemap lists *every* URL. `llms.txt` lists the *important* ones, with context.

## Does it help rankings or AI visibility?

Be realistic with clients:

- It is **not** a Google ranking factor. Google representatives have publicly said Search does not use it.
- Support from major AI platforms is limited and still changing. Some AI tools and agents read it, and many don't yet.
- It is cheap to create and maintain, carries no SEO risk, and forces a useful exercise: deciding which pages and facts best represent the brand.

Treat it as a low-effort, low-risk addition, not a GEO strategy on its own. Crawlable content, clear entities, structured data and third-party mentions matter far more.

## Structure (as used in the template)

The format is plain Markdown, in this order:

1. **H1 with the site or brand name** (required): `# Example Co`
2. **Blockquote summary**: one or two sentences describing what the business is, where it operates and who it serves.
3. **Optional free text**: key facts that AI answers often get wrong, such as service areas, languages, pricing notes and what you *don't* offer.
4. **H2 sections with link lists**, in the format `- [Page name](URL): short description`.
5. **`## Optional` section**: lower-priority links that can be skipped when context is limited.

## How to adapt the template

1. Replace "Example Co" and the summary with your brand. Keep the summary factual, not salesy.
2. Under **Key facts**, list what AI assistants should know to answer correctly: markets, languages, currencies, opening hours and policies.
3. Choose 10–30 of your most important pages. Use canonical, indexable, `200` URLs only.
4. For multi-region sites (for example `en-ae`, `ar-ae`, `en-sa`, `ar-sa`), make the market clear in the link text, and include a section for the Arabic versions.
5. Upload it to the site root as `llms.txt`, served as `text/plain` or `text/markdown`.
6. Update it whenever key services, markets or URLs change, and check the links during your regular technical audits.

## Optional: llms-full.txt

Some sites also publish `llms-full.txt`, which contains the full text of key pages in one Markdown file. It's useful for documentation sites. For most business sites, `llms.txt` is enough.
