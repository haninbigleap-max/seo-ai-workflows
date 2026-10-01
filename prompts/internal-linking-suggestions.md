# Prompt: Internal Linking Suggestions

Finds contextual internal linking opportunities between a page and the rest of your site, with suggested anchor text and the exact sentence where each link fits.

## When to use it

- After publishing a new page that has few or no internal links pointing to it
- Strengthening priority pages (services, categories) with links from relevant blog content
- Building topic clusters: linking pillar pages and supporting articles both ways
- Cleaning up orphan pages found in a crawl

## Inputs to prepare

- **Target page**: URL, primary keyword and a one-line summary
- **Candidate source pages**: export from Screaming Frog or your CMS with URL, title, H1 and, ideally, body text (or the first 300 words)
- **Existing links**: the inlinks report for the target, so you don't suggest links that already exist
- Language and market, so you don't link `en-ae` pages to `ar-sa` pages by mistake

For large sites, pre-filter candidates by topic or keyword overlap first, then send 20–50 at a time.

## The prompt

```text
You are an SEO specialist planning internal links.

TARGET PAGE (the page that should RECEIVE links):
URL: {{TARGET_URL}}
Primary keyword: {{TARGET_KEYWORD}}
Summary: {{TARGET_SUMMARY}}
Language/market: {{MARKET}}

CANDIDATE SOURCE PAGES (may link TO the target):
{{CANDIDATES: URL | Title | Body text or excerpt}}

Pages that ALREADY link to the target (exclude these): {{EXISTING_INLINKS}}

Task:
1. Pick up to {{N}} source pages where a link to the target would genuinely help a reader.
   Skip pages where the link would be forced or off-topic.
2. For each one, quote the EXACT existing sentence from the source page where the link should go,
   and suggest the anchor text: 2-6 words, descriptive, natural. Prefer text that already
   exists in the sentence over rewriting it.
3. Vary the anchor text across suggestions. Don't use the exact-match keyword every time.
4. Only suggest links between pages in the same language/market.
5. Give a relevance score from 1 to 5 and a one-line reason.

Output as a table:
Source URL | Existing sentence | Anchor text | Relevance (1-5) | Reason

Then list up to 3 links the TARGET page should send OUT to strengthen the topic cluster.
```

## Example output

| Source URL | Existing sentence | Anchor text | Relevance | Reason |
|---|---|---|---|---|
| https://example.com/en-ae/blog/office-hygiene-checklist/ | "For larger offices, many businesses in Dubai outsource this to a commercial cleaning provider." | commercial cleaning provider | 5 | Directly describes the service on the target page |
| https://example.com/en-ae/blog/moving-office-tips/ | "Book a deep clean of the new space before your team moves in." | deep clean of the new space | 3 | Related, but end-of-tenancy intent is secondary |

## Reviewing the output

- [ ] **The sentence really exists.** Search the source page for the quoted sentence. Models sometimes paraphrase or invent it.
- [ ] **Read it as a user.** Would you click that link at that point in the text? If not, drop it.
- [ ] **Anchor variety.** Avoid 10 identical exact-match anchors pointing at one page.
- [ ] **Language and market match.** No links from Arabic pages to English pages, or from UAE pages to KSA pages, inside body copy.
- [ ] **Link to the canonical, indexable URL.** No redirects, no parameter URLs.
- [ ] **Don't overload pages.** Keep body links per page reasonable, and prioritise the highest-relevance suggestions.
- [ ] **Measure.** Recrawl after implementing, and watch the target page's impressions in GSC over the following weeks.
