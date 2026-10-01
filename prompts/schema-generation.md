# Prompt: Schema (JSON-LD) Generation

Generates valid, guideline-compliant JSON-LD from a page's actual content, ready for validation and deployment.

## When to use it

- Adding structured data to templates (product, service, article, location pages)
- Building `Organization` / `LocalBusiness` entity markup for the homepage or contact page
- Creating `FAQPage` or `BreadcrumbList` markup in bulk for many pages
- Converting existing Microdata to JSON-LD

## Inputs to prepare

- The page URL and its visible content: copy, prices, address, opening hours, FAQs
- The schema type(s) you want, or ask the model to recommend them
- Site-wide entity details: organisation name, logo URL, `sameAs` profiles
- Language and region of the page (for `inLanguage`, `areaServed`, currency)

## The prompt

```text
You are a technical SEO specialist who writes Schema.org JSON-LD.

Generate JSON-LD for the page below.

Rules:
- Output ONE <script type="application/ld+json"> block using an @graph array if there is more than one entity.
- Use ONLY values that appear in the page content or site details I provide. Never invent ratings,
  reviews, prices, dates, addresses or phone numbers. If a recommended property has no value,
  leave it out and list it under "Missing data" after the code.
- Every marked-up value must be visible to users on the page.
- Use absolute URLs. Give entities stable @id values (e.g. https://example.com/#organization)
  and reference them instead of repeating them.
- Use ISO 8601 for dates and ISO 4217 for currency (AED, SAR, USD).
- Set inLanguage to the page language (e.g. "en-AE", "ar-SA").

Page URL: {{URL}}
Page type: {{PAGE_TYPE}}
Requested schema types: {{SCHEMA_TYPES}}   (or "recommend")
Site-wide entity details: {{ORG_DETAILS}}
Page content:
"""
{{PAGE_CONTENT}}
"""

After the code, add:
1. Missing data: recommended properties you could not fill, and where to get them.
2. Rich result eligibility: which Google rich results this markup could qualify for, if any.
```

## Example (filled placeholders)

```text
URL: https://example.com/ar-ae/services/ac-maintenance/
Page type: service page (Arabic, UAE)
Requested schema types: Service, BreadcrumbList, FAQPage
Site-wide entity details: name "Example Co", logo https://example.com/logo.png,
  sameAs https://www.linkedin.com/company/example
```

## Reviewing the output

- [ ] **Validate it.** Run it through the Schema.org validator and Google's Rich Results Test, or use `validate_schema.py` from [schema-testing](https://github.com/haninbigleap-max/schema-testing).
- [ ] **Look for invented values.** Check `aggregateRating`, `review`, `priceRange`, `telephone`, `geo` and dates against the page. AI models often add plausible-looking values.
- [ ] **Visible content rule.** Every FAQ question and answer must appear on the page word for word, or close to it.
- [ ] **Consistent `@id`s.** The organisation `@id` should be identical on every page of the site.
- [ ] **Language and currency.** `inLanguage` and `priceCurrency` should match the locale (an `ar-sa` page should use SAR, not AED).
- [ ] **Not over-marked.** Don't add types the page doesn't really represent, such as `Product` on a blog post.
- [ ] **Check after deployment.** Inspect the live URL in Search Console to confirm Google sees the rendered markup.
