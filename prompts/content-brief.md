# Prompt: SEO Content Brief

Turns a target keyword, your SERP research and business context into a structured content brief that a writer can follow and an SEO can approve.

## When to use it

- Planning a new page or blog post for a keyword you have already researched
- Refreshing an underperforming page (paste in the current content too)
- Briefing freelance writers in a consistent format
- Producing parallel briefs for different markets, such as `en-ae` vs `en-sa`

**Not** a replacement for keyword research. Decide the keyword and intent first, then use this prompt to speed up the write-up.

## Inputs to prepare

- Primary keyword and 5–15 secondary keywords (from your keyword tool or GSC)
- Notes on the top 5–10 ranking pages: page type, headings, angle, gaps
- "People Also Ask" questions and any AI Overview summary you see
- Business context: what you sell, USPs, location, audience
- Target market and language

## The prompt

```text
You are a senior SEO content strategist. Create a content brief for the page described below.

Use ONLY the information I provide for facts about the business. Where you need information
you don't have, write [NEEDS INPUT: ...] instead of inventing it.

## Inputs
Primary keyword: {{PRIMARY_KEYWORD}}
Secondary keywords: {{SECONDARY_KEYWORDS}}
Target market and language: {{MARKET}}   (e.g. en-ae, ar-sa, en-gb)
Page type: {{PAGE_TYPE}}   (e.g. service page, category page, blog guide)
Business context: {{BUSINESS_CONTEXT}}
Audience: {{AUDIENCE}}
SERP notes (top results, their angle, headings, gaps): {{SERP_NOTES}}
People Also Ask / AI Overview notes: {{PAA_NOTES}}

## Output (Markdown, in this order)
1. Search intent: primary intent, secondary intent, and what the searcher needs in order to be satisfied.
2. Recommended title tag (max ~60 characters) and meta description (max ~155 characters). Give 2 options each.
3. H1.
4. Full outline: H2s and H3s, with 1–2 bullet points per heading on what to cover.
5. Questions to answer directly: 5–8 questions, each with a suggested 40–60 word direct answer
   placed right under the matching heading (for featured snippets and AI answers).
6. Entities and topics to mention, to signal topical completeness.
7. Information gain: 3 ideas that would make this page better than the current top results
   (original data, local specifics, expert quotes, tools, comparison tables).
8. Internal links: types of pages on our site this page should link to and receive links from.
9. Schema types that suit this page.
10. Word count range, with your reasoning based on the SERP notes.

Write for the specified market. Use local spelling, currency and place names.
```

## Example (filled placeholders)

```text
Primary keyword: commercial cleaning services dubai
Secondary keywords: office cleaning dubai, deep cleaning company dubai, cleaning contract price
Target market and language: en-ae
Page type: service landing page
Business context: Example Co provides contract cleaning for offices and retail in Dubai and Sharjah...
```

## Reviewing the output

- [ ] **Intent check.** Does the outline match what actually ranks? If the SERP is all listicles and the brief proposes a service page, question it.
- [ ] **No invented facts.** Search for `[NEEDS INPUT` and fill every gap with real information. Remove any prices, certifications or statistics the model made up.
- [ ] **Title and meta length.** Check pixel width in a SERP preview tool, not just character counts. Arabic titles behave differently.
- [ ] **Direct answers are actually direct.** The first sentence should answer the question by itself.
- [ ] **Information gain is real.** If every idea is generic ("add images"), push the model for something specific to your business.
- [ ] **Cannibalisation.** Make sure no other page on the site already targets this keyword.
- [ ] **Local accuracy.** Area names, regulations and currency must be right for the market (AED vs SAR; Dubai vs Riyadh).
