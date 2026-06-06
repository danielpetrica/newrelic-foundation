# Design Spec: New Relic Consultancy Sales Page

> Single-page HTML at `danielpetrica.com/newrelic`. Plain HTML, system fonts, inline CSS. No frameworks, no JS beyond Stripe embed + pre-qual toggle. No animations, no scroll effects.

---

## 1. Overall Aesthetic Direction

The page should feel like a well-structured internal memo from a senior engineer who has been asked to explain why monitoring matters and what it will cost. Not a sales page — a document that happens to sell.

**Mood:** Confident, restrained, substantive. The design communicates expertise through what it *doesn't* do — no gradients, no cards with shadows, no hero illustrations, no `border-radius` over 4px anywhere. The reader should feel like they stumbled onto something written by someone who ships production code, not marketing copy.

**References (spirit, not style):**
- The typographic restraint of old 37signals product pages (pre-Basecamp rebrand)
- The information density and clarity of the Tailscale blog
- The "this is just text and it works" confidence of Berkshire Hathaway's site — but with actual typesetting
- The editorial feel of Craig Mod's long-form pages

**What makes it memorable:** It looks like nothing else in SaaS consulting. No one else in the observability/DevOps consulting space builds pages this stripped-back. The absence of typical "consultant website" signifiers (stock photos of servers, glowing network diagrams, gradient CTA buttons) is itself the differentiation.

**Photography:** None. Zero images. The only non-text visual element is the Stripe checkout button (rendered by Stripe) and possibly the 5-star review pull quotes (stars as unicode characters ★, not images).

---

## 2. Color Palette

Four colors. No more.

| Role | Hex | Usage |
|------|-----|-------|
| Background | `#fafaf8` | Page background. A warm off-white — not `#ffffff`, not cream, just slightly softened. Reads as white without being sterile. |
| Text | `#1a1a1a` | All body copy, headlines, navigation. Near-black but not `#000`. Slightly warmer than `#111`. |
| Accent | `#284b63` | Used *only* for: the CTA button background, the pre-qual question active state indicator, and the monospace inline code tint. A muted teal-blue — references New Relic's brand color without copying it. Dark enough to contrast well on white. |
| Subtle | `#e6e4e0` | Horizontal rule divider between sections, the pre-qual checklist border-left when inactive, any structural lines. Barely visible, just enough to define space. |

**What not to use:** No secondary accent. No hover color changes (links underline on hover; the CTA button should not change color). No gradients. No tints or shades beyond these four hex values.

---

## 3. Typography

### Font Choice

**System font stack, no web fonts.** The page loads zero external CSS or font files.

```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
```

**Monospace inline stack** (for code/metric names/technical inline terms):

```css
font-family: 'SF Mono', 'Cascadia Code', 'Fira Code', Menlo, Consolas, monospace;
```

### Hierarchy

| Element | Size | Weight | Line-height | Notes |
|---------|------|--------|-------------|-------|
| Hero headline | `2.25rem` (36px) | 600 | 1.15 | The only element on the page at this size. Sets the entire tone. |
| Section headlines | `1.25rem` (20px) | 600 | 1.3 | Equal weight to body. The hierarchy comes from position (standalone line), not size inflation. No `h2` should feel like a "heading." |
| Body copy | `1rem` (16px) | 400 | 1.6 | Generous leading. The page is meant to be read, not scanned. |
| Small / meta | `0.8125rem` (13px) | 400 | 1.5 | Used for: star ratings, review attribution, the payment-plan note, the section-number labels, the lead-magnet form label. |
| Inline code | `0.875rem` (14px) | 400 | inherit | Monospace stack. Background `#f0eeeb`. Padding 1px 4px. Used for: "APM", "PHP", "Node.js", "NRQL", "SSH", metric names. |
| Price | `3rem` (48px) | 600 | 1 | The only number on the page set this large. The € symbol sits at `2rem`, optically aligned. |
| Pre-qual question labels | `1rem` (16px) | 500 | 1.5 | Slightly heavier than body to distinguish interactive text from passive text. |

### Color assignments within text:

- Body text: `#1a1a1a`
- Links: `#1a1a1a` with `text-decoration: underline` and `text-underline-offset: 3px`. On hover, underline color shifts to accent `#284b63`. No color change on the text itself.
- Review quote attribution: `#6b6b6b` (a gray derived from the text color at ~40% opacity — can use `color-mix` or just `#6b6b6b`)
- Horizontal rules: `#e6e4e0`, 1px height, full bleed (edge to edge in the content column)

---

## 4. Layout Structure

### Global constraints

- Single centered column, max-width `640px`, centered with `margin: 0 auto`.
- Horizontal padding `1.25rem` on mobile (20px), `2rem` on desktop.
- Spacing between sections: `4rem` (64px) of whitespace. Between subsection groups within a section: `2rem`.
- No sticky headers, no fixed nav, no footer columns.

### Section order and spatial treatment

Each section is a block with no visual container — just text in the column. Sections are separated by 4rem of vertical space and, optionally, a 1px horizontal rule in `#e6e4e0` for the major structural transitions (after Hero, before Pricing, before CTA).

**1. Hero** (no `<hr>` below)
- Headline on one line: the pain-focused headline
- Subhead: one sentence, same size as body but weight 400, 2rem below headline
- Below subhead: three trust signifiers horizontally arranged on desktop, stacked on mobile:
  - "5.0 ★ on Upwork" (linked)
  - "ISO 27001 experience" (no link)
  - "7 calendar day delivery" (no link)
- These are `0.8125rem`, muted gray text, separated by `·` (middle dot, `&middot;`) on desktop, each on its own line on mobile.
- Generous top padding: `6rem` from page top to headline. No nav bar. No logo. The page starts with the headline.

**2. The Problem**
- Section headline: "Nobody owns monitoring."
- Body copy: 2-3 short paragraphs describing the pain state.
- No visual flourishes. Just text.

**3. The Cost of Nothing**
- Section headline: "Downtime costs more than €850."
- Body copy: 1-2 paragraphs. Includes the key ROI line: "Cheaper than one hour of downtime."
- This section is shorter than Problem. Its job is to frame the price before the reader sees it.

**4. The Solution**
- Section headline: "Full monitoring. 7 calendar days. One price."
- Body copy: The core value proposition paragraph.
- After the paragraph: the four phases of The Foundation Process, displayed as an inline list, not a diagram. Each phase on one line:
  ```
  1. Instrument  →  Agents deployed across your stack
  2. Baseline    →  72 hours of traffic before we tune anything
  3. Alert       →  Thresholds set to your patterns, not generic defaults
  4. Handoff     →  The Foundation Kit: dashboard suite, alert playbook, runbook
  ```
- Phase numbers in `0.8125rem` monospace, muted gray. Phase names in `1rem` weight 600. Descriptions in body weight. Arrows (`→`) in accent color. Each phase separated by `0.75rem`. No connecting lines, no timeline visual. Pure typography.

**5. What's Included**
- Section headline: "Everything in the package."
- An expanded feature list. Each feature on its own line:
  - Feature name in weight 600 (e.g., "APM agent configuration")
  - Mini-explanation in body weight on the same line after an en-dash (`–`)
- Grouped implicitly by blank lines (not sub-headlines):
  - Monitoring scope: APM, host, browser, Docker, synthetics
  - Alerting: policies, conditions, delivery channels
  - Infrastructure visibility: Apache/Nginx/Traefik, MySQL
  - Logs: system logs included; app logs included for standard frameworks
- The last item in the list: "The Foundation Kit — a documented runbook of everything configured. You're never locked in."

**6. What Happens After**
- Section headline: "After delivery."
- Two short paragraphs:
  - The 14-day tuning window (included, not extra)
  - The optional paths: €200 tuning pass, €250/mo retainer
- Each option presented as "Option: description" on its own line, with the price in weight 600.
- A one-line reassurance: "Zero commitment beyond the initial setup."

**7. Pricing**
- Section headline: "€850"
- No body text before the price. The price *is* the headline.
- Below the price, on one line: "Everything included. Docker, synthetics, alerting, the Foundation Kit."
- Below that, smaller text: "Payment plan: €425 now, €425 on delivery. Same scope, no catch."
- No pricing table. No comparison columns. No "most popular" badges.

**8. Who I Am**
- Section headline: "Who you're hiring."
- This section is intentionally brief. Not a CV dump.
- 3 short paragraphs:
  - Paragraph 1: "I've been configuring New Relic since 2023..." — establishes tenure and hands-on reality.
  - Paragraph 2: "I contributed to ISO 27001 certification at Warrant Hub..." — establishes compliance lens.
  - Paragraph 3: "I run this exact setup myself." — establishes skin in the game.
- Below the paragraphs: two pull quotes from Upwork reviews, formatted as:
  ```
  ★★★★★ 5.0
  "...highly skilled with New Relic and provided valuable suggestions..."
  — APM Tool Expert for SaaS Website, 75h engagement
  ```
  ```
  ★★★★★ 5.0
  "...exceptionally professional and possesses extensive knowledge... project completed to a very high standard..."
  — New Relic Implementation client, 61h engagement
  ```
- Quotes in body size, italic. Attribution in `0.8125rem`, not italic, muted gray. Stars in accent color. Quotes separated by 1.5rem. Each pull quote indented with a left border-left of `2px solid #e6e4e0` and `1rem` left padding.

**9. FAQ**
- Section headline: "If you're wondering..."
- Each FAQ as a `<details>` element (no JS needed — native HTML):
  - The `<summary>` is the question, weight 500, same size as body, cursor pointer.
  - The answer is body text inside, weight 400.
  - Default: all closed. The user opens what they care about.
  - Questions drawn from the objection-handling section of the brief. At minimum: price, capability, wrong-fit platforms, GDPR/data sovereignty, New Relic bill impact, existing monitoring tools, speed-vs-DIY, and lock-in risk.
- Each `<details>` separated by `1rem`. A subtle left border (`2px solid #e6e4e0`) appears on the open `<details>` via the `[open]` selector — the only CSS "animation" on the page, and it's a static state change.

**10. The Lead Magnet**
- A short section with a headline: "Not ready to buy? Take the free PDF."
- One sentence: "5 New Relic Alerts Every SaaS Should Have — a practical guide you can use today, whether or not you work with me."
- Below: an inline email capture form. Single input field (`type="email"`) + submit button, on one line. No labels — placeholder text "you@yourcompany.com". The button says "Send me the PDF".
- Both input and button share the same height (`2.75rem`), same border (`1px solid #e6e4e0`), same font. The button background is accent (`#284b63`) with white text. The input background is white with `#1a1a1a` text.
- Below the form, in `0.75rem` muted text: "No spam. One email with the PDF, then a follow-up series. Unsubscribe anytime."
- The form action posts to Mailcoach. No JS validation beyond `type="email"` and `required`.

**11. CTA — Pre-Qual + Stripe Checkout**
- Section headline: "Ready? Check your setup and check out."
- The pre-qual questions (see Section 6 below).
- Below the questions: the Stripe checkout embed.
- A final reassurance line below the Stripe embed: "If your environment doesn't match what you indicated, full refund minus time spent at €65/hr. The Foundation Kit means you're never dependent on me."

---

## 5. Key Visual Elements

### What's present:

1. **Horizontal rules between sections** — 1px, color `#e6e4e0`, full-width within the content column. Used sparingly: after Hero, before Pricing, before CTA. Not between every section — whitespace alone handles most transitions.

2. **Left-border pull quotes** — The review quotes in "Who I Am" get a `2px solid #e6e4e0` left border with `1rem` padding. This is the only "card-like" visual treatment on the page, and it's as minimal as possible.

3. **Inline monospace code** — Technical terms (APM, PHP, Node.js, NRQL, SSH) appear in `0.875rem` monospace with a background tint of `#f0eeeb`. This is both functional (distinguishes technical from natural language) and signals to the technical reader that the author thinks in code.

4. **The open `<details>` border** — When a FAQ answer is revealed, a `2px solid #284b63` left border appears. This is the only use of the accent color as a structural element anywhere on the page (besides buttons). It makes the FAQ interaction feel intentional.

5. **Unicode ★ stars** — Five-point stars in the accent color for review ratings. No icon fonts, no SVG.

### What's absent (intentionally):

- No icons (no checkmarks, no arrows beyond the → in the phase list)
- No cards, no shadows, no `border-radius` above 4px
- No images, no illustrations, no logos (not even Daniel Petrica's own logo — the page doesn't need one; the domain IS the brand)
- No decorative dividers or ornaments
- No background color changes between sections

---

## 6. The Pre-Qual + Stripe Flow

### Visual treatment before answers are given

The pre-qual section sits above the Stripe embed. It's three yes/no questions, presented as a compact inline form. The default state shows all three questions, each with a "Yes" and "No" button.

Layout:

```
Ready? Check your setup and check out.

  Linux host (Ubuntu/Debian/CentOS/Alpine)?        [Yes]  [No]
  PHP (Laravel) or Node.js backend?                  [Yes]  [No]
  Active New Relic account (or willing to create)?   [Yes]  [No]

  ───
  ⚠ Full monitoring generates billable data in New
  Relic. Make sure you understand your expected
  data ingest and pricing tier before purchasing.
  ───

  [Stripe checkout embed appears here when all three = Yes]
```

### Question styling

- Each question row: question text (weight 400) on the left, `[Yes]` `[No]` buttons on the right, flexbox-justified.
- The Yes/No buttons are not `<button>` elements in the traditional sense — they're `<label>` elements wrapping a hidden `<input type="radio">`, styled to look like text choices:
  - Default state: text color `#6b6b6b`, background transparent, border `1px solid #e6e4e0`, padding `4px 12px`, `border-radius: 4px`, cursor pointer.
  - Selected "Yes": background `#284b63`, text `#ffffff`, border `#284b63`.
  - Selected "No": background `#e6e4e0`, text `#6b6b6b`, border `#e6e4e0`.
- On mobile, each question stacks: question text on top, Yes/No below, separated by `0.5rem`. No forced vertical alignment — natural reading flow.

### The logic (minimal JS)

- All three questions default to unselected.
- When all three have "Yes" selected: show the Stripe embed + the "not a fit" messages for any "No" selections disappear.
- If any question has "No" selected: the Stripe embed stays hidden. Below that question, a brief inline message appears in `0.8125rem`, color `#6b6b6b`:
  - Linux = No: "This package requires a Linux host. If you're on a different platform, I'm happy to refer you to someone who specializes in it."
  - Stack = No: "This package covers PHP (Laravel) and Node.js backends. For other stacks, a custom engagement may be possible — reach out directly."
  - New Relic = No: "You'll need an active New Relic account. You can create one at newrelic.com — the free tier is enough to start."
- The data ingest notice (the ⚠ block) is always visible, regardless of answers.

### Transition to Stripe

When all three answers = Yes, the Stripe embed appears below the pre-qual questions with no animation, no fade-in, no transition. It simply appears. (CSS: toggle `display: none` → `display: block`).

The Stripe embed renders at its natural width (from Stripe's JS). It should be contained within the same 640px column.

The JS for this is approximately 15 lines — an event listener on the radio inputs that checks all three states and toggles the embed container's `hidden` attribute.

---

## 7. Mobile Treatment

### At 640px and below (single breakpoint)

The page uses a single breakpoint: `max-width: 640px`. There is no intermediate tablet layout. The design is either desktop (content column at 640px) or mobile (full-width with padding).

**What changes:**

1. **Max-width goes away** — The content column becomes `width: 100%` with `padding: 0 1.25rem`. The text measure is naturally constrained by the viewport.

2. **Headline size drops** — Hero headline goes from `2.25rem` to `1.75rem` (28px). This keeps it from wrapping awkwardly on narrow screens.

3. **Price drops** — From `3rem` to `2.5rem` (40px). It's still the largest element, but it shouldn't dominate a phone screen.

4. **Trust signifiers stack** — The three items under the hero subhead stack vertically with `0.5rem` between them. The `·` separators are hidden.

5. **Pre-qual questions stack** — Each question becomes a two-line stack: question text on top, Yes/No buttons below with `0.5rem` gap. No side-by-side layout.

6. **Lead magnet form stacks** — The email input and submit button stack vertically, full width, with `0.5rem` between them. On desktop they're side by side.

7. **Section spacing reduces** — Inter-section whitespace goes from `4rem` to `3rem`. The page will already be long scrolled; overly generous spacing on mobile creates fatigue.

8. **Review quotes lose the indent** — The `1rem` left padding on pull quotes drops to `0.75rem` to preserve words-per-line.

**What doesn't change:**

- Font sizes for body, small text, monospace inline
- Color palette
- Horizontal rule treatment
- FAQ `<details>` behavior (native, works everywhere)
- The overall editorial feel — the page should look like it was *designed for mobile first*, not adapted reluctantly

---

## 8. Signature Detail

### The inline code treatment as a trust signal

Throughout the page, technical terms appear as inline monospace with a subtle background tint:

> I configure **`APM`** agents for **`PHP`** (Laravel) and **`Node.js`** stacks.

This is a small thing, but it does three things at once:

1. **Signals technical competence.** Engineers recognize this convention — it's how you format code in technical documentation. Seeing it on a sales page creates immediate subconscious trust: "This person writes docs, not just marketing copy."

2. **Makes the page scannable for technical buyers.** A CTO scanning the page can instantly spot every technology mentioned without reading a single sentence of body copy.

3. **Creates a distinctive visual rhythm.** The alternating pattern of body text → monospace snippet → body text gives the page a texture that feels editorial rather than promotional. It breaks up the gray wall of text without resorting to decorative elements.

**Implementation note:** This is purely CSS — `<code>` elements get the monospace stack, `0.875rem` size, `#f0eeeb` background, `1px 4px` padding, and `border-radius: 3px`. No additional markup burden.

### Secondary detail: the section numbering

The Foundation Process phases are numbered 1–4, set in `0.8125rem` monospace, muted gray. These tiny numbers do a lot of work: they signal structure without headlines, they make the process feel methodical, and they create a visual anchor point that the eye returns to. Combined with the `→` arrows in accent color, the phase list reads like a terminal command, not a marketing diagram. Small thing, but it's the kind of detail that makes the whole page feel like it was made by someone who cares.
