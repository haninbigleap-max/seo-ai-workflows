# Prompt: AI Visibility Audit

A repeatable method, plus prompts, for checking whether and how your brand appears in AI-generated answers (ChatGPT, Gemini, Copilot, Perplexity, Claude, Google AI Overviews), and for tracking that over time.

## When to use it

- Setting a baseline before starting GEO / AEO work
- Monthly or quarterly tracking of AI share of voice against competitors
- After a big change such as a rebrand, new content hub, digital PR campaign or new market launch
- Investigating why a competitor keeps getting recommended instead of you

## Method

AI answers vary between runs, users, locations and model versions, so treat this like rank tracking with noise:

1. **Build a fixed prompt set** of 20–50 questions real customers ask, mixed across:
   - *Category*: "best {{SERVICE}} companies in {{CITY}}"
   - *Problem*: "how do I {{PROBLEM}}"
   - *Comparison*: "{{BRAND}} vs {{COMPETITOR}}"
   - *Brand*: "what is {{BRAND}}", "is {{BRAND}} reliable"
   - *Local / language*: run the same questions in English and Arabic, for UAE and KSA where relevant
2. **Run each prompt** on each platform in a clean session (logged out, or with memory and personalisation off), with location set to the target market. Run each one 2–3 times.
3. **Record the results** in a sheet: platform, prompt, date, brand mentioned (Y/N), position in the answer, sentiment, competitors mentioned, sources cited.
4. **Analyse the gaps** with the analysis prompt below.
5. **Repeat** on the same schedule with the same prompt set.

## Prompt A: run on each AI platform

Use the customer question exactly as written. Don't mention your brand unless it's a brand query. Optionally add:

```text
{{CUSTOMER_QUESTION}}

Please list the specific companies, products or websites you would recommend, and cite your sources.
```

## Prompt B: analyse the collected answers

```text
You are an SEO analyst specialising in AI search visibility (GEO).

Below are answers from several AI assistants to a fixed set of customer questions,
collected on {{DATE}} for the market {{MARKET}} (e.g. UAE, English and Arabic).

Our brand: {{BRAND}} (website: {{DOMAIN}})
Main competitors: {{COMPETITORS}}

For the data below:
1. Build a table: Prompt | Platform | Brand mentioned (Y/N) | Position (1st, 2nd, ... / not listed)
   | Sentiment (positive/neutral/negative) | Competitors mentioned | Cited sources (domains).
2. Calculate AI share of voice: the % of answers mentioning each brand, overall and per platform.
3. List the most frequently cited third-party domains. These are the sources AI systems trust in this niche.
4. Note any factual errors or outdated information about our brand.
5. Give 5 prioritised, specific actions to improve our visibility. Tie each one to the evidence
   above (e.g. "competitor X is cited from review site Y, where we have no profile").

Use only the data provided. Do not guess at answers that are not in the data.

DATA:
"""
{{PASTED_ANSWERS_OR_CSV}}
"""
```

## Example tracking sheet columns

| Date | Platform | Market | Language | Prompt | Brand mentioned | Position | Sentiment | Competitors | Sources cited |
|---|---|---|---|---|---|---|---|---|---|
| 2026-10-01 | Perplexity | UAE | en | best commercial cleaning companies in dubai | N | – | – | Brand A, Brand B | example-directory.com, example-reviews.com |
| 2026-10-01 | ChatGPT | KSA | ar | أفضل شركات تنظيف في الرياض | Y | 3 | neutral | Brand C | example-news.sa |

## Reviewing the output

- [ ] **Sample size.** Don't draw conclusions from a single run. Look for patterns across repeats and platforms.
- [ ] **Check the citations.** Open the cited sources. Are they current? Is your brand listed there at all?
- [ ] **Fix factual errors at the source.** Wrong information usually comes from your own site, an old directory listing or an outdated article. Correct it there.
- [ ] **Actionable, not generic.** "Create quality content" isn't an action. "Get listed on the directory cited in 8 of 20 answers" is.
- [ ] **Keep the method fixed.** Changing prompts or settings between months breaks the trend line.
- [ ] **Connect to SEO data.** Compare with GSC queries and referral traffic from AI platforms in GA4 (chatgpt.com, perplexity.ai, copilot.microsoft.com, gemini.google.com).
