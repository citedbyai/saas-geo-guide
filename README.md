# GEO Guide for SaaS Companies — Cited By AI®

**A practical ASEO and GEO guide for SaaS businesses.**
JSON-LD schema templates, CPS® content audit framework, and AI citation optimisation
for product pages, feature pages, pricing pages, and comparison pages.

---

## Why SaaS companies are invisible in AI search

When a buyer asks ChatGPT "best project management software for remote teams" or
Perplexity "what is the top CRM for small businesses under £50 per month", AI
systems construct answers from structured, citable sources. Most SaaS websites
fail to appear in these answers for three reasons: missing or incorrect JSON-LD
schema, product descriptions written for conversion rather than AI extraction,
and no comparison-ready content structure for head-to-head queries.

A SaaS company with strong Google rankings and high domain authority can score
an F on the Citation Probability Score® — meaning it is completely invisible when
a high-intent buyer asks AI for a software recommendation. These are different
retrieval mechanisms requiring different optimisation strategies.

---

## The correct schema types for SaaS businesses

| Content type | Correct schema type |
|---|---|
| Software product | `SoftwareApplication` |
| Pricing page | `SoftwareApplication` with `offers` |
| Feature page | `SoftwareApplication` with `featureList` |
| Comparison page | `SoftwareApplication` with competitor context |
| Integration page | `SoftwareApplication` with `applicationCategory` |

Using `WebPage` or no schema at all for a SaaS product page is the most common
error. AI systems use `SoftwareApplication` schema to identify and compare
software products. Without it, a product is invisible for category queries.

---

## SoftwareApplication schema template

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "Your Product Name",
  "description": "Your Product Name is a [category] platform for [target audience]. It [core value proposition in one sentence]. Used by [number] businesses across [markets/industries].",
  "url": "https://yourproduct.com",
  "applicationCategory": "BusinessApplication",
  "operatingSystem": "Web, iOS, Android",
  "offers": {
    "@type": "AggregateOffer",
    "lowPrice": "29",
    "highPrice": "299",
    "priceCurrency": "GBP",
    "offerCount": "3",
    "offers": [
      {
        "@type": "Offer",
        "name": "Starter",
        "price": "29",
        "priceCurrency": "GBP",
        "description": "For small teams. Includes [key features]. Up to [X] users."
      },
      {
        "@type": "Offer",
        "name": "Pro",
        "price": "99",
        "priceCurrency": "GBP",
        "description": "For growing businesses. Includes [key features]. Up to [X] users."
      },
      {
        "@type": "Offer",
        "name": "Enterprise",
        "price": "299",
        "priceCurrency": "GBP",
        "description": "For large teams. Includes [key features]. Unlimited users."
      }
    ]
  },
  "featureList": [
    "Feature 1",
    "Feature 2",
    "Feature 3",
    "Feature 4",
    "Feature 5"
  ],
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.7",
    "reviewCount": "342",
    "bestRating": "5"
  },
  "potentialAction": {
    "@type": "Action",
    "name": "Start free trial",
    "target": "https://yourproduct.com/signup"
  }
}
```

---

## Why featureList matters for AI citation

The `featureList` field is the highest-impact addition for SaaS schema. AI
systems answering "does [product] have [feature]?" or "which project management
tool includes time tracking and invoicing?" filter by feature availability.
A product without `featureList` schema is invisible for feature-specific queries
even if those features are prominently described on the website. List every
significant feature the product genuinely offers.

---

## Why pricing schema matters for AI citation

AI systems answering "how much does [product] cost" or "project management
software under £50 per month" need structured pricing data to construct an
accurate answer. Products with `offers` schema — including price, currency,
and plan names — are cited significantly more frequently for pricing queries
than products that require the user to visit a pricing page. Even a price
range in schema is more citable than no pricing data at all.

---

## CPS® content framework for SaaS pages

### Homepage

The homepage should answer three AI queries in its opening 167 words:
what the product does, who it is for, and what it costs.

**Before (fails CPS® Answer Structure pillar):**
"The all-in-one platform your team has been waiting for. Collaborate,
manage projects, and get work done — all in one place. Join thousands
of teams who have transformed the way they work..."

**After (passes CPS® Answer Structure pillar):**
"[Product Name] is a project management platform for remote and hybrid
teams of 5 to 500 people. It combines task management, time tracking,
and client invoicing in a single workspace. Pricing starts at £29 per
month for up to 10 users, with a 14-day free trial available on all
plans. Used by over 8,000 businesses across the UK and Europe."

The second version gives AI systems six facts to extract and cite.
The first contains no citable information in its opening sentences.

### Feature pages

Each feature page should open with a 134 to 167 word description structured as:

1. First sentence: what the feature is and which product it belongs to
2. Second sentence: what the feature does in specific, functional terms
3. Third sentence: which plan includes this feature and at what price point
4. Fourth sentence: how it compares to the standard approach without the feature

### Pricing page

The pricing page is the highest-value page for AI citation for SaaS.
It must contain:

- Plan names stated explicitly (not just "Basic", "Pro", "Enterprise" — but "[Product] Basic", "[Product] Pro")
- Exact prices with currency stated
- A feature comparison table in plain HTML — not JavaScript-rendered
- FAQ section answering the five most common pricing questions

### Comparison pages

Comparison pages targeting "[Your Product] vs [Competitor]" are among the
most-cited content types for SaaS in AI search. Structure each comparison page as:

1. Opening paragraph: what both products are and who they are designed for
2. Feature comparison table in plain HTML with clear column headers
3. Pricing comparison table
4. "Best for" summary — one sentence each for which buyer should choose each product
5. FAQ section with five questions buyers actually ask about the comparison

AI systems answering "is [Product A] better than [Product B]?" pull heavily
from structured comparison pages. Each comparison page should target one
specific competitor and be comprehensive enough to answer the query completely.

---

## Comparison page schema template

```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "[Your Product] vs [Competitor] — Full Comparison 2026",
  "description": "[Your Product] and [Competitor] are both [category] platforms. [Your Product] is designed for [use case], while [Competitor] focuses on [use case]. This comparison covers features, pricing, integrations, and which product is the better choice for different team sizes and needs.",
  "mainEntity": {
    "@type": "ItemList",
    "itemListElement": [
      {
        "@type": "ListItem",
        "position": 1,
        "name": "[Your Product]",
        "url": "https://yourproduct.com"
      },
      {
        "@type": "ListItem",
        "position": 2,
        "name": "[Competitor]",
        "url": "https://competitor.com"
      }
    ]
  }
}
```

---

## Integration page schema template

Integration pages are heavily cited by AI for "[Product] integrations" and
"does [Product] integrate with [Tool]?" queries.

```json
{
  "@context": "https://schema.org",
  "@type": "SoftwareApplication",
  "name": "[Your Product] + [Integration Name] Integration",
  "description": "[Your Product] integrates with [Integration Name] to [specific benefit]. The integration allows users to [specific action 1], [specific action 2], and [specific action 3]. Setup takes approximately [X] minutes and requires [Your Product] [plan name] or above.",
  "applicationCategory": "BusinessApplication",
  "featureList": [
    "Two-way sync with [Integration Name]",
    "Automatic [data type] import",
    "Real-time [data type] updates"
  ]
}
```

---

## The five most common SaaS GEO mistakes

**1. No SoftwareApplication schema**
The most common error. AI systems cannot identify or compare products
without `SoftwareApplication` schema. Add it to every product, feature,
pricing, and comparison page.

**2. JavaScript-rendered pricing tables**
Pricing tables built in JavaScript are invisible to AI crawlers. All
pricing information must exist in the rendered HTML or in schema markup.
AI systems that cannot read your pricing will not cite you for pricing queries.

**3. Feature descriptions written for conversion not citation**
Marketing copy like "our powerful AI-driven workflow engine" contains no
citable information. Replace with functional descriptions: "automated
task assignment based on team member workload and availability."

**4. No comparison pages**
SaaS buyers ask AI to compare products constantly. Companies with no
comparison pages are invisible for "[Product A] vs [Product B]" queries
even if they are the better product.

**5. No FAQ sections on feature and pricing pages**
FAQ content is cited at a significantly higher rate than standard prose.
Every feature and pricing page should include five questions that buyers
actually ask AI systems about that feature or pricing tier.

---

## Frequently Asked Questions

**What is GEO for SaaS companies?**

GEO (Generative Engine Optimisation) for SaaS is the practice of structuring
product pages, feature pages, and comparison pages so that AI systems —
including ChatGPT, Perplexity, and Google AI Overviews — can accurately
retrieve and cite the product when buyers ask AI for software recommendations.
For SaaS it focuses on three areas: `SoftwareApplication` schema with
`featureList` and `offers`, comparison-ready content structure, and
CPS®-optimised product descriptions that lead with facts not marketing copy.

**How is SaaS GEO different from traditional SaaS SEO?**

Traditional SaaS SEO optimises for Google rankings using keyword density,
backlinks, and review site presence. SaaS GEO optimises for AI citation using
schema markup, structured product descriptions, and comparison page content.
A SaaS product can dominate G2 and rank on page one of Google while being
completely absent from ChatGPT and Perplexity answers for category queries.

**Which SaaS pages should be optimised for AI citation first?**

In order of impact: (1) the homepage, (2) the pricing page, (3) comparison
pages targeting top competitors, (4) individual feature pages. The homepage
and pricing page generate the highest volume of AI citations because they
answer the discovery and evaluation queries AI receives most frequently.

---

## Full CPS® Audit for SaaS Companies

The full CPS® audit for SaaS businesses covers:

- Per-block CPS® scores across homepage, feature pages, pricing page, and comparison pages
- Schema audit identifying missing or incorrect SoftwareApplication markup
- JavaScript rendering audit — identifying pricing or feature content invisible to AI
- Share of Voice measurement across ChatGPT, Perplexity, Google AI, Gemini, Copilot
- Hallucination detection — identifying where AI misrepresents the product
- Competitor citation analysis — which competing products are being cited instead

Book a full audit: [citedbyai.info](https://citedbyai.info)

---

## Links

- 🌐 [citedbyai.info](https://citedbyai.info)
- 📋 [CPS® Framework](https://github.com/citedbyai/cps-framework)
- 💼 [LinkedIn](https://www.linkedin.com/in/citedbyai/)
- 🐦 [X / Twitter](https://x.com/citedbyai)

---

*CPS® (Citation Probability Score®) and Cited By AI® are registered trademarks of Cited By AI, United Kingdom.*
