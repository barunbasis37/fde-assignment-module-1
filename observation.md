# AI Model Comparison: Observations

This report compares how three AI models handled the same task: building a landing page for a Forward Deployed Engineering (FDE) services company.

## 1. AI Models Used

All three models were used through the same tool, **Claude Code** (in the VS Code extension). Only the model was changed between runs, so the comparison is fair.

**Model 1:** Claude Haiku 4.5 (Claude Code): the fast, lightweight model
**Model 2:** Claude Sonnet (Claude Code): the balanced, mid-tier model
**Model 3:** Claude Opus 5.5 (Claude Code): the most capable model

| Model | Output file | Brand name it invented |
|---|---|---|
| Claude Haiku 4.5 | [index-Haiku.html](index-Haiku.html) | Embed |
| Claude Sonnet | [index-sonnet.html](index-sonnet.html) | Pathfinder FDE |
| Claude Opus 5.5 | [index-opus.html](index-opus.html) | Fieldline |

---

## 2. Prompt Used

The **same prompt** was given to all three models:

> "Create a responsive landing page for a Forward Deployed Engineer (FDE) service company using only HTML and CSS (no JavaScript) in a single `index.html` file. Include a header with navigation, a hero section, services, how the engagement works, pricing, an FAQ and a contact/call-to-action section, plus a footer. The page must work on mobile and desktop, support dark mode, and follow accessibility best practices."

All three pages share these features, which confirms they received the same requirements:
- A single HTML file with embedded CSS and no JavaScript
- A mobile menu built with a CSS checkbox, and an FAQ built with `<details>/<summary>`
- Responsive layouts using media queries
- Dark mode (`prefers-color-scheme`) and reduced-motion support
- A skip link and ARIA labels for accessibility

---

## 3. Code Quality Observation

| Criteria | Haiku | Sonnet | Opus |
|---|---|---|---|
| Size | 585 lines / 29 KB | 1155 lines / 49 KB | 790 lines / 46 KB |
| Page sections | 8 (hero, brands, services, timeline, CTA, pricing, FAQ, contact) | 11 (adds stats, testimonials, a full contact form) | 11 (adds problem/solution, a comparison table, testimonials) |
| CSS variables (design tokens) | Yes, but some colours are typed directly into the code (header background, timeline text) | Yes, the most complete and best commented | Yes, used consistently |
| Icons | Emojis (🔗 📊 🔐 🚀), which look different on each operating system | Inline SVG | Inline SVG |
| Semantic HTML | Basic | Good (`article`, a `form` with labels) | Best (`dl` for stats, `ol` for steps, `figure`/`blockquote`, a `table` with `caption` and `scope`) |
| Accessibility | The mobile menu checkbox uses `display:none`, so keyboard users can't open the menu | The checkbox can get focus, but nothing shows on screen when it does | The checkbox can get focus and shows a visible focus ring |
| Dark mode | Supported | Supported | Supported |
| Bugs found | The FAQ shows two arrows (the browser's default marker plus a custom ▼). The featured price card's `scale(1.05)` can overflow on mobile. | The FAQ has no open/close indicator. The `.chevron` style exists, but no chevron element was ever added to the HTML. | Minor only: a duplicated `.nav .btn` rule and one unused class (`.btn-line-light`) |
| Maintainability | Fair | Good | Good |

**Summary:**
- **Haiku** wrote the shortest, simplest code, but it has real bugs in the user interface and accessibility.
- **Sonnet** wrote the most code with the best comments, but left one feature (the FAQ indicator) half-built.
- **Opus** wrote the cleanest, most semantic code with the fewest defects.

---

## 4. AI Hallucination Observation

### Haiku

**Observation 1: The timeline contradicts itself.**
The heading says *"Simple. Four-week engagement."*, but the steps run Week 1 → Week 2 → Weeks 3–4 → Week 5, which is five weeks. The pricing card says "4–5 weeks". The AI did not check its own content.

**Observation 2: A real company is listed as a customer.**
"Protocol Labs" is a real company (the makers of IPFS/Filecoin). The page claims it as a client under *"Trusted by engineering teams at"*. This is the most serious hallucination found, because publishing it could mislead visitors and create legal risk.

**Observation 3: The contact address hasn't been checked.**
`hello@embed.dev` uses a domain that may belong to someone else. A human must verify it.

**Observation 4: The numbers are made up.**
"2.8 wks average deployment time", "200+ live deployments" and "96% renewal rate" have no source.

### Sonnet

**Observation 1: The numbers contradict each other.**
It claims *"48 hrs avg. time to first working deploy"*, but also *"Live within 5 business days"* and *"5 days average time to embed"*. An engineer can't deploy before they have joined the team.

**Observation 2: A feature that doesn't exist.**
The header has a "Sign in" button, but there is no account system behind it. The button just links to the contact section.

**Observation 3: Placeholder company names.**
The customer logos are ACME, Northwind, Globex, Initech, Umbrella Labs and Soylent. These are well-known fictional names, but **Soylent is also a real company**.

**Observation 4: The testimonials are made up.**
Quotes are attributed to named people (Dana Whitfield, Rafael Kim, Priya Sen) who don't exist.

**What it did well:** it used a reserved placeholder email domain (`hello@pathfinderfde.example`) and a fake `555` phone number, and it gave no prices (*"pricing depends on scope"*). This is the most responsible use of placeholders among the three.

### Opus

**Observation 1: The data source doesn't exist.**
The comparison table's caption reads *"Typical figures from Fieldline engagements, 2024–2026."* There is no such data. The AI presented invented numbers as if they came from real measurements.

**Observation 2: The testimonials and statistics are made up.**
*"Our pilot-to-paid conversion went from 40% to 85% in two quarters"* is attributed to a named person (Sofia Reyes, Head of Sales, Verity) who doesn't exist.

**Observation 3: A made-up claim that depends on timing.**
The hero says *"3 engineers available for Q4 starts"*. This goes out of date quickly and has no basis.

**What it did well:** its numbers agree with each other. "3 wks median time to production" matches the "day 19" rollout in the terminal graphic and the four-phase, roughly four-week process.

### Common to all three models

- Every model **invented statistics, customer logos, testimonials and/or prices**. All of this needs human verification or replacement before the page is published.
- None of the forms or contact buttons actually work (`action="#"` or a bare `mailto:`). They look complete but have no backend.

| Hallucination type | Haiku | Sonnet | Opus |
|---|---|---|---|
| Content that contradicts itself | Yes (timeline) | Yes (stats) | No |
| Real company named as a customer | Yes (Protocol Labs) | Partly (Soylent) | No |
| Fake testimonials | No | Yes | Yes |
| Made-up statistics | Yes | Yes | Yes |
| Claims a data source that doesn't exist | No | No | Yes |
| Feature that doesn't exist | No | Yes ("Sign in") | No |
| Contact details that could belong to someone else | Yes | No (safe `.example` domain) | No |

---

## 5. Final Decision

**Which AI model produced better results, and why?**

**Opus produced the best result.**

| Criteria | Winner | Reason |
|---|---|---|
| Code quality | Opus | The most semantic and accessible HTML, consistent design tokens, almost no bugs |
| Accuracy | Opus | Its content agrees with itself. Haiku and Sonnet both contradict their own numbers. |
| Maintainability | Opus / Sonnet | Both have a clear structure and reusable components. Sonnet has better comments. |
| Understanding of requirements | Opus | It added sections that fit a real B2B sales page (problem vs. solution, a comparison table, a qualifying contact form). |

**Ranking:**

1. **Opus:** the most accurate and polished. Its hallucinations are the "marketing filler" kind (testimonials, a made-up data source), not contradictions or real-world names.
2. **Sonnet:** a close second. It handled placeholders most responsibly (`.example` domain, `555` number, no invented prices) and has the best-commented CSS, but it has a broken FAQ indicator, a fake "Sign in" button and a contradiction in its stats.
3. **Haiku:** the weakest. It names a real company as a customer, its timeline contradicts itself, its mobile menu can't be used with a keyboard, and it uses emoji icons. It is the fastest and lightest option, which suits a quick first draft.

**Key lesson:** all three models produced believable but unverified content. AI output, especially numbers, names, testimonials and contact details, must always be reviewed by a human before it is published.

> Note: this comparison was carried out with the help of Claude Opus, which is one of the models being evaluated.
