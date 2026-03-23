---
marp: true
theme: default
paginate: true
size: 16:9
header: ''
footer: ''
math: mathjax
---

<style>
:root {
  --bg-base: #0f172a;
  --bg-surface: #1e293b;
  --bg-elevated: #334155;
  --text-primary: #e2e8f0;
  --text-secondary: #94a3b8;
  --color-heading: #7dd3fc;
  --color-heading-h3: #a5b4fc;
  --color-accent: #f87171;
  --color-highlight: #fbbf24;
  --color-green: #4ade80;
  --border-subtle: #475569;
  /* High-contrast table + code (readable “paper” panels on dark slides) */
  --table-header-bg: #1e40af;
  --table-header-text: #ffffff;
  --table-cell-bg: #1e293b;
  --table-cell-bg-alt: #172033;
  --table-cell-text: #f8fafc;
  --table-border: #64748b;
  --code-block-bg: #f1f5f9;
  --code-block-text: #0f172a;
  --code-block-border: #cbd5e1;
  --code-inline-bg: #e2e8f0;
  --code-inline-text: #0f172a;
}

/* ── Base slide ── */
section {
  background-color: var(--bg-base);
  color: var(--text-primary);
  font-family: 'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
  font-size: 28px;
}

/* ── Page number ── */
section::after {
  color: var(--text-secondary);
}

/* ── Headings ── */
h1 {
  color: var(--color-heading);
}

h2 {
  color: var(--color-heading);
  border-bottom: 3px solid var(--color-accent);
  padding-bottom: 0.2em;
}

h3 {
  color: var(--color-heading-h3);
}

/* ── Bold / strong ── */
strong {
  color: var(--color-highlight);
}

/* ── Links ── */
a {
  color: var(--color-heading);
  text-decoration: underline;
  text-decoration-color: var(--border-subtle);
}

a:hover {
  color: #bae6fd;
}

/* ── Blockquotes ── */
blockquote {
  background-color: var(--bg-surface);
  border-left: 5px solid var(--color-accent);
  border-radius: 0 6px 6px 0;
  padding: 0.5em 1em;
  font-style: italic;
  color: var(--text-secondary);
}

blockquote strong {
  color: var(--color-highlight);
}

/* ── Lists ── */
li {
  color: var(--text-primary);
}

li::marker {
  color: var(--color-accent);
}

/* ── Tables (high contrast: borders + light text on solid rows) ── */
table {
  font-size: 0.88em;
  width: 100%;
  border-collapse: collapse;
  border: 2px solid var(--table-border);
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.35);
}

th {
  background-color: var(--table-header-bg) !important;
  color: var(--table-header-text) !important;
  font-weight: 700;
  text-align: left;
  padding: 0.55em 0.75em;
  border: 1px solid #3b82f6;
}

td {
  padding: 0.5em 0.75em;
  border: 1px solid var(--table-border);
  color: var(--table-cell-text) !important;
  background-color: var(--table-cell-bg);
  vertical-align: top;
}

tr:nth-child(even) td {
  background-color: var(--table-cell-bg-alt);
}

/* Table body emphasis: readable on dark cells */
td strong {
  color: #fde047 !important;
}

th strong {
  color: #ffffff !important;
}

/* ── Code: light “paper” blocks so text + syntax tokens stay readable ── */
code {
  font-size: 0.9em;
  font-family: ui-monospace, 'Cascadia Code', 'Source Code Pro', Menlo, Consolas, monospace;
  background-color: var(--code-inline-bg);
  color: var(--code-inline-text);
  border-radius: 4px;
  padding: 0.12em 0.4em;
  border: 1px solid #cbd5e1;
}

pre {
  font-size: 0.82em;
  line-height: 1.45;
  background-color: var(--code-block-bg) !important;
  color: var(--code-block-text) !important;
  border: 1px solid var(--code-block-border) !important;
  border-radius: 8px;
  padding: 0.85em 1em !important;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.6), 0 2px 10px rgba(0, 0, 0, 0.25);
}

pre code {
  background-color: transparent !important;
  color: var(--code-block-text) !important;
  border: none !important;
  padding: 0 !important;
}

/* highlight.js */
pre .hljs-keyword,
pre .hljs-selector-tag,
pre .hljs-title,
pre .hljs-section {
  color: #6d28d9 !important;
}

pre .hljs-string,
pre .hljs-attr {
  color: #047857 !important;
}

pre .hljs-number,
pre .hljs-literal {
  color: #b45309 !important;
}

pre .hljs-comment {
  color: #64748b !important;
  font-style: italic;
}

pre .hljs-function,
pre .hljs-title.function_ {
  color: #0369a1 !important;
}

pre .hljs-built_in,
pre .hljs-class {
  color: #0e7490 !important;
}

/* Prism (alternate highlighter) */
pre .token.keyword,
pre .token.selector,
pre .token.tag {
  color: #6d28d9 !important;
}

pre .token.string,
pre .token.attr-value {
  color: #047857 !important;
}

pre .token.number,
pre .token.boolean {
  color: #b45309 !important;
}

pre .token.comment {
  color: #64748b !important;
  font-style: italic;
}

pre .token.function {
  color: #0369a1 !important;
}

pre .token.class-name {
  color: #0e7490 !important;
}

/* ── Horizontal rule (shouldn't show in slides, but just in case) ── */
hr {
  border-color: var(--border-subtle);
}

/* ── Lead (centered) slides ── */
section.lead {
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

section.lead h1,
section.lead h2,
section.lead h3 {
  text-align: center;
}

/* ── Invert (accent dark) slides — title, closing ── */
section.invert {
  background: linear-gradient(160deg, #0c0f1a 0%, #162040 50%, #1a1040 100%);
  color: #ffffff;
}

section.invert h1 {
  color: #ffffff;
  text-shadow: 0 0 40px rgba(125, 211, 252, 0.3);
}

section.invert h2 {
  color: var(--color-heading);
  border-bottom-color: rgba(248, 113, 113, 0.5);
}

section.invert h3 {
  color: var(--color-heading-h3);
}

section.invert blockquote {
  background-color: rgba(30, 41, 59, 0.6);
  border-left-color: var(--color-accent);
  color: #cbd5e1;
}

section.invert a {
  color: var(--color-heading);
}

/* ── Section header slides ── */
section.section-header {
  background: linear-gradient(135deg, #1e3a5f 0%, #0f172a 100%);
  color: #ffffff;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
}

section.section-header h2 {
  color: #ffffff;
  font-size: 2.2em;
  border-bottom: 3px solid rgba(248, 113, 113, 0.5);
  text-shadow: 0 0 30px rgba(125, 211, 252, 0.2);
}

/* ── Quote slides ── */
section.quote-slide {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

section.quote-slide blockquote {
  font-size: 1.3em;
  border-left: 6px solid var(--color-accent);
  padding: 0.5em 1em;
  margin: 0.5em auto;
  max-width: 80%;
}

/* ── Font-size variant slides ── */
section.small-text {
  font-size: 22px;
}

section.smaller-text {
  font-size: 20px;
}
</style>

<!-- _class: lead invert -->
<!-- _paginate: false -->
<!-- _header: '' -->
<!-- _footer: '' -->

# Software Engineering in the AI Era

## Vibe Coding Done Right

---

<!-- _class: lead -->

## About the speaker

### Setia Budi

**Machine Learning Engineer** at **tiket.com**

<br>

**Social — @boedybios**

- [Instagram](https://www.instagram.com/boedybios/)
- [LinkedIn](https://www.linkedin.com/in/boedybios/)
- [GitHub](https://github.com/boedybios)

<br>

**YouTube — Indonesia Belajar**

[Indonesia Belajar](https://www.youtube.com/@belajarIDN) · `youtube.com/@belajarIDN`

---

## Agenda

1. Software Engineering Workflow — Before AI-Assisted Coding
2. Software Engineering — With AI-Assisted Coding
3. The Rise of Vibe Coding
4. The Pros and Cons of AI-Assisted Coding
5. TDD/BDD — The Responsible Way to Vibe Code

---

<!-- _class: section-header -->

## 1. Software Engineering Workflow Before AI-Assisted Coding

---

### The Traditional Development Lifecycle

```text
Requirements  →  Design  →  Implement  →  Test  →  Deploy  →  Maintain
```

<br>

Each phase relied **entirely** on human expertise, institutional knowledge, and manual effort.

Software engineering has always been about managing **complexity** — the tools changed over decades, but the discipline stayed the same.

---

### How Engineers Spent Their Time

| Activity                    | Typical Share |
|-----------------------------|---------------|
| Reading docs & source code  | ~30%          |
| Writing new code            | ~20%          |
| Debugging & troubleshooting | ~25%          |
| Code review & collaboration | ~15%          |
| Tooling & environment setup | ~10%          |

<br>

> "Indeed, the ratio of time spent reading versus writing is well over 10 to 1.
> We are *constantly* reading old code as part of the effort to write new code."
> — Robert C. Martin, *Clean Code*

---

### The Toolbox of the Pre-AI Engineer

- **IDEs** — IntelliJ, VS Code, NeoVim *(autocomplete, syntax highlighting, refactoring)*
- **Version Control** — Git *(collaboration & history)*
- **CI/CD Pipelines** — Jenkins, GitHub Actions *(automated builds & deploys)*
- **Stack Overflow & Documentation** — The primary "knowledge retrieval" system
- **Linters & Static Analysis** — PyLint, PyRight, Ruff *(code quality gates)*
- **Testing Frameworks** — JUnit, PyTest, Locust *(manual test authoring)*

<br>

Every tool augmented the engineer but **never replaced the thinking**.

---

### Pain Points of the Traditional Workflow

- **Boilerplate fatigue** — Repetitive scaffolding, CRUD logic, and glue code
- **Context switching** — Jumping between browser, docs, IDE, and terminal
- **Knowledge silos** — Tribal knowledge locked in senior engineers' heads
- **Slow onboarding** — New team members need weeks to become productive
- **Inconsistent quality** — Code review catches vary by reviewer fatigue
- **Testing feels like a chore** — Tests written *after* the code, often skipped under pressure

<br>

These pain points created an environment **hungry for disruption**.

---

<!-- _class: section-header -->

## 2. Software Engineering With AI-Assisted Coding

---

### The New Landscape

AI coding assistants have reshaped the inner loop of software development:

```text
Think  →  Prompt  →  Review  →  Refine  →  Commit
```

<br>

The engineer's role shifts from **typist** to **director** — articulating intent, evaluating output, and curating quality.

Code is no longer *written from scratch* — it is **generated, reviewed, and refined**.

---

<!-- _class: small-text -->

### Where AI Assistants Plug In

| Workflow Phase     | AI Capability                                       |
|--------------------|-----------------------------------------------------|
| **Design**         | Generate architecture diagrams, API contracts        |
| **Implementation** | Code generation, autocomplete, boilerplate removal   |
| **Testing**        | Generate unit tests, suggest edge cases              |
| **Code Review**    | Spot bugs, suggest improvements, explain code        |
| **Documentation**  | Auto-generate docstrings, READMEs, changelogs        |
| **Debugging**      | Explain errors, suggest fixes, trace root causes     |
| **Learning**       | Explain unfamiliar code, teach patterns on-the-fly   |

<br>

AI doesn't just help in one phase — it **permeates every phase**.

---

### Popular AI-Assisted Coding Tools (2025–2026)

| Tool                  | Key Strength                              |
|-----------------------|-------------------------------------------|
| GitHub Copilot        | Deep IDE integration, inline suggestions  |
| Cursor                | AI-native IDE, agentic multi-file editing |
| Claude Code / ChatGPT | Conversational problem-solving            |

<br>

The tooling landscape is evolving fast — but the **engineering principles** underneath should not.

---

### The Human + AI Collaboration Model

```text
┌──────────────────────────────────────────┐
│           SOFTWARE ENGINEER              │
│                                          │
│  Intent  ──►  Prompt / Specification     │
│                      │                   │
│                      ▼                   │
│            ┌──────────────────┐          │
│            │   AI ASSISTANT   │          │
│            │   (Generation)   │          │
│            └────────┬─────────┘          │
│                     │                    │
│                     ▼                    │
│  Review  ◄──  Generated Code             │
│    │                                     │
│    ▼                                     │
│  Accept / Refine / Reject                │
│    │                                     │
│    ▼                                     │
│  Commit & Ship                           │
└──────────────────────────────────────────┘
```

---

<!-- _class: quote-slide -->

### The engineer remains the accountable decision-maker at every stage.

> But what happens when that **accountability** starts to slip?

---

<!-- _class: section-header -->

## 3. The Rise of Vibe Coding

---

### What Is Vibe Coding?

In February 2025, **Andrej Karpathy** coined the term:

> "There's a new kind of coding I call **'vibe coding'**, where you fully give in to the vibes, embrace exponentials, and forget that the code even exists."
>
> — Andrej Karpathy (@karpathy), Feb 2025

<br>

The idea: describe what you want in natural language, let AI generate the code, accept the results if they "seem to work," and move on.

**You don't read the code. You don't fully understand the code. You just *vibe*.**

---

### Why Vibe Coding Took Off

- **Speed is intoxicating** — Prototype an entire app in an afternoon
- **Low barrier** — Non-engineers and beginners can build working software
- **Instant gratification** — See results immediately, iterate by prompting
- **AI keeps getting better** — Each model generation makes it more tempting

<br>

Vibe coding unlocked **creativity and experimentation** at a scale never seen before.

And that's genuinely exciting.

---

### The Uncomfortable Truth About Vibe Coding

But there's a cost:

<br>

- **"It works"** is not the same as **"it's correct"**
- **"It runs"** is not the same as **"it's secure"**
- **"It looks right"** is not the same as **"it handles edge cases"**

<br>

Without verification, vibe coding produces **demo-quality software that feels like production-quality software**.

It's the software equivalent of a **movie set** — the facade looks real, but there's nothing behind the walls.

---

<!-- _class: smaller-text -->

### The Vibe Coding Spectrum

```text
RECKLESS                                                 RESPONSIBLE
VIBE CODING                                              VIBE CODING
   │                                                          │
   ▼                                                          ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌───────────────┐
│ "Just ship   │ │ "I skimmed   │ │ "I reviewed  │ │ "Tests pass,  │
│  it, YOLO"   │ │  the code,   │ │  the code    │ │  code reviewed│
│              │ │  looks fine" │ │  carefully"  │ │  & verified"  │
│  No tests    │ │  No tests    │ │  Maybe some  │ │  TDD/BDD      │
│  No review   │ │  Light       │ │  tests after │ │  Tests first  │
│ No           │ │  review      │ │  the fact    │ │  AI generates │
│ understanding│ │              │ │              │ │  to spec      │
└──────────────┘ └──────────────┘ └──────────────┘ └───────────────┘
       ▲                                                    ▲
  Most vibe coding                                   Where we should
  today                                              aim to be
```

The goal isn't to **stop** vibe coding. It's to do it **responsibly**.

---

<!-- _class: quote-slide -->

### The Real Question

> How do we keep the **speed and joy** of vibe coding while adding the **rigor and reliability** of real engineering?

<br>

This is not a new question.

Software engineering has answered it before — **decades ago**.

---

<!-- _class: section-header -->

## 4. The Pros and Cons of AI-Assisted Coding

---

### The Pros (1/2)

**Velocity & Productivity**
- 30–50% faster task completion on routine work *(GitHub Research, 2023)*
- Dramatically reduced boilerplate and scaffolding time
- Entire prototypes built in hours instead of days

**Lower Barrier to Entry**
- Junior developers get "senior-level" suggestions
- Faster onboarding to unfamiliar codebases and languages
- Domain experts can build tools without deep programming skills

**Cognitive Offloading**
- Focus on *what* to build rather than *how* to type it
- Less time on Stack Overflow, more time on the actual problem

---

### The Pros (2/2)

**Consistency & Coverage**
- AI can suggest test cases humans overlook
- Enforces patterns when prompted with conventions
- Generates consistent boilerplate across a codebase

**Learning Accelerator**
- Explains unfamiliar code in natural language
- Exposes engineers to idiomatic patterns they might not know
- Always-available mentor

---

### The Cons (1/3)

**Hallucination & Subtle Bugs**
- AI generates plausible but incorrect code — the "looks right" trap
- Dangerous in security-sensitive or mission-critical contexts
- Bug patterns are novel — not the kind engineers are trained to spot

**Over-Reliance & Skill Atrophy**
- Engineers may lose deep problem-solving skills
- "Copy-paste from AI" without understanding is the new "copy-paste from Stack Overflow"
- Juniors may never develop foundational debugging instincts

---

### The Cons (2/3)

**Context Window Limitations**
- AI lacks full project context — may contradict existing architecture
- Large codebases exceed what the model can reason about at once
- Cross-module implications are often missed

**Security & IP Concerns**
- Code sent to cloud models raises data leakage risks
- Generated code may inadvertently replicate licensed code
- AI doesn't reason about threat models unless explicitly prompted

---

### The Cons (3/3)

**Technical Debt Amplification**
- It's faster to generate bad code too — AI can *accelerate* debt creation
- Without discipline, "just ship it" culture intensifies
- Codebases balloon with AI-generated code nobody fully understands

**Non-Deterministic Output**
- Same prompt, different results — makes reproducibility harder
- Team members get different suggestions, reducing consistency
- Refactoring becomes risky when you can't predict what AI will produce

---

### The Balanced View

```text
                  ┌───────────────────┐
                  │    AI-Assisted    │
                  │      Coding       │
                  └────────┬──────────┘
            ┌──────────────┼──────────────┐
            ▼              ▼              ▼
      ┌──────────┐  ┌──────────┐  ┌──────────────┐
      │ Amplifies│  │ Amplifies│  │  Requires    │
      │   Good   │  │   Bad    │  │  New Skills  │
      │ Practice │  │ Practice │  │  & Discipline│
      └──────────┘  └──────────┘  └──────────────┘
```

> AI-assisted coding is a **force multiplier**, not a replacement.
> Great practices + AI = **exceptional output**.
> No practices + AI = **exceptional mess**.

---

<!-- _class: lead -->

### The Central Dilemma

Every con of AI-assisted coding shares a root cause:

<br>

> **There is no automated way to verify that AI-generated code is correct.**

<br>

Or is there?

---

<!-- _class: section-header -->

## 5. TDD/BDD — The Responsible Way to Vibe Code

---

<!-- _class: quote-slide -->

### The Core Insight

We already have a practice that solves this exact problem:

> **Define correctness *before* writing code, then verify automatically.**

<br>

That's TDD. That's BDD. That's what they were *always* for.

AI didn't invent the need for specification-first development.
AI made it **non-negotiable**.

---

### Quick Refresher — TDD

**Test-Driven Development**

```text
 RED          →        GREEN        →        REFACTOR
 Write a               Make it               Clean it
 failing test          pass                  up
```

<br>

The discipline: **no production code exists without a test that demanded it**.

Every line of code has a *reason to exist*, expressed as a test.

---

### Quick Refresher — BDD

**Behavior-Driven Development**

```gherkin
Feature: User Login
  Scenario: Successful login with valid credentials
    Given a registered user with email "user@example.com"
    When they submit the login form with valid credentials
    Then they should be redirected to the dashboard
    And a session token should be issued
```

<br>

BDD extends TDD by expressing tests in **business-readable language**.
Stakeholders, QA, and engineers share the same specification.

Both share a principle: **specify behavior *before* implementation**.

---

### Why TDD/BDD Was Made for the AI Era (1/2)

What TDD/BDD gives you:

1. **A precise, executable specification** — not a vague English prompt
2. **An automated verification mechanism** — pass/fail, no ambiguity
3. **A feedback loop** — failing tests tell AI exactly what's wrong
4. **A regression safety net** — refactor fearlessly, re-run tests
5. **Living documentation** — the spec *is* the test suite

---

### Why TDD/BDD Was Made for the AI Era (2/2)

What vibe coding lacks:

1. A precise specification — **tests provide this**
2. Automated verification — **tests provide this**
3. A feedback loop — **tests provide this**
4. A safety net — **tests provide this**
5. Documentation of intent — **tests provide this**

---

<!-- _class: lead -->

### **TDD/BDD solves every weakness of vibe coding.**

---

### Tests as Prompts — The Key Reframe

What if we stop thinking of tests as "extra work after coding" and start thinking of them as **the specification language for AI**?

```text
Traditional Vibe Coding:
  Vague Prompt  →  AI Generates Code  →  "Looks right?"  →  Ship & pray

Responsible Vibe Coding (TDD + AI):
  Write Tests   →  AI Generates Impl  →  Run Tests       →  ✓ or Iterate
```

<br>

Tests become the **contract** that the AI must satisfy.

This gives us something we desperately need: **a deterministic verification layer on top of non-deterministic generation**.

---

<!-- _class: smaller-text -->

### Side-by-Side: Vibe Coding vs. Responsible Vibe Coding (1/2)

| Aspect                   | Vibe Coding (No Tests)        | Responsible Vibe Coding (TDD/BDD) |
|--------------------------|-------------------------------|-----------------------------------|
| **Specification**        | Vague natural language prompt | Precise, executable test cases    |
| **Verification**         | "Looks right to me"          | Automated pass/fail               |
| **Feedback to AI**       | "Try again, it's broken"     | "Test X failed: expected Y, got Z"|
| **Confidence in output** | Low — hope-driven            | High — evidence-driven            |
| **Refactoring safety**   | Terrifying                   | Fearless — tests catch regressions|

---

<!-- _class: smaller-text -->

### Side-by-Side: Vibe Coding vs. Responsible Vibe Coding (2/2)

| Aspect                    | Vibe Coding (No Tests)         | Responsible Vibe Coding (TDD/BDD)    |
|---------------------------|--------------------------------|--------------------------------------|
| **Debugging**             | "Something's wrong somewhere"  | "This specific behavior is broken"   |
| **Documentation**         | None — the prompt is gone      | Tests *are* the living documentation |
| **Technical debt**        | Accumulates invisibly          | Controlled — tests enforce contracts |
| **Reproducibility**       | Different AI output each time  | Same tests, same pass/fail criteria  |
| **Long-term maintenance** | Fragile                        | Sustainable                          |

---

<!-- _class: small-text -->

### The Proposed Workflow

```text
┌───────────────────────────────────────────────────────┐
│                                                       │
│  ENGINEER (Human)                                     │
│                                                       │
│  1. Define behavior specs (BDD scenarios/test cases)  │
│  2. Review & validate the specification               │
│                                                       │
│          ┌────────────────────────────────┐           │
│          │        AI ASSISTANT            │           │
│          │                                │           │
│          │  3. Generate implementation    │           │
│          │     that satisfies the tests   │           │
│          └─────────────┬──────────────────┘           │
│                        │                              │
│                        ▼                              │
│  4. Run test suite automatically                      │
│          │                                            │
│          ├── ALL PASS → Review quality → Commit       │
│          │                                            │
│          └── FAILURES → AI iterates (back to step 3)  │
│                                                       │
└───────────────────────────────────────────────────────┘
```
---

<!-- _class: lead -->

### The human writes the **what**. 
### The AI writes the **how**. 
### The tests verify **both**.

---

<!-- _class: small-text -->

### Concrete Example — TDD: Step 1

**Engineer writes the tests (the specification):**

```python
import pytest
from pricing import calculate_discount

class TestCalculateDiscount:
    def test_no_discount_below_threshold(self):
        assert calculate_discount(30.00) == 0.00
        assert calculate_discount(49.99) == 0.00

    def test_standard_discount_tier(self):
        assert calculate_discount(50.00) == 5.00
        assert calculate_discount(80.00) == 8.00
        assert calculate_discount(99.99) == 10.00

    def test_premium_discount_tier(self):
        assert calculate_discount(100.00) == 20.00
        assert calculate_discount(150.00) == 30.00

    def test_rejects_negative_amounts(self):
        with pytest.raises(ValueError, match="cannot be negative"):
            calculate_discount(-10.00)

    def test_zero_amount_returns_zero_discount(self):
        assert calculate_discount(0.00) == 0.00
```

The engineer expressed **business rules, edge cases, and error handling** — all as executable specs.

---

### Concrete Example — TDD: Step 2 & 3

**AI generates the implementation to satisfy the tests:**

```python
def calculate_discount(amount: float) -> float:
    if not isinstance(amount, (int, float)):
        raise TypeError(f"Expected numeric amount, got {type(amount).__name__}")
    if amount < 0:
        raise ValueError("Order amount cannot be negative")
    if amount < 50:
        return 0.00
    if amount < 100:
        return round(amount * 0.10, 2)
    return round(amount * 0.20, 2)
```

**Run the tests:**

```text
$ pytest test_pricing.py -v
test_no_discount_below_threshold    PASSED
test_standard_discount_tier         PASSED
test_premium_discount_tier          PASSED
test_rejects_negative_amounts       PASSED
test_zero_amount_returns_zero       PASSED
======================== 5 passed in 0.02s ========================
```

**The AI vibed. The tests verified. The engineer is confident.**

---

<!-- _class: small-text -->

### Concrete Example — BDD Flavor

**Engineer writes behavior specs in Gherkin:**

```gherkin
Feature: Shopping Cart Discount
  As an e-commerce platform
  I want to apply tiered discounts to orders
  So that customers are rewarded for larger purchases

  Scenario Outline: Apply tiered discounts based on order amount
    Given an order total of <amount> dollars
    When the discount is calculated
    Then the discount should be <discount> dollars

    Examples:
      | amount | discount |
      | 0.00   | 0.00     |
      | 30.00  | 0.00     |
      | 50.00  | 5.00     |
      | 80.00  | 8.00     |
      | 100.00 | 20.00    |
      | 150.00 | 30.00    |

  Scenario: Reject negative order amounts
    Given an order total of -10.00 dollars
    When the discount is calculated
    Then a ValueError should be raised with message "cannot be negative"
```
---

<!-- _class: lead -->

### AI generates both **step definitions** and **implementation**. 
### BDD adds: **stakeholders can read and validate the spec** before a single line of code is written.

---

### What the Engineer *Actually* Does

| Activity                                        | Who Does It  |
|-------------------------------------------------|--------------|
| Understands the business requirement             | Human        |
| Translates requirements into test cases / specs  | Human        |
| Reviews the spec for completeness & edge cases   | Human        |
| Generates the implementation                     | AI           |
| Runs the test suite                              | Automated    |
| Iterates on failures                             | AI + Human   |
| Reviews the generated code for quality           | Human        |
| Approves and commits                             | Human        |

---

<!-- _class: lead -->

### The engineer's job shifts from **writing code** to **defining correctness**.
### That's not less engineering — it's **more** engineering.

---

### Why This Solves the Vibe Coding Problem (1/2)

**Problem: AI hallucinates code that "looks right."**
TDD/BDD fix: Tests don't care how the code *looks*. They verify how it **behaves**.

<br>

**Problem: Engineers skip reviewing AI output.**
TDD/BDD fix: You don't need to read every line. The **test suite** is your reviewer.

<br>

**Problem: No way to verify correctness automatically.**
TDD/BDD fix: That's **literally what tests do**.

---

### Why This Solves the Vibe Coding Problem (2/2)

**Problem: Refactoring AI code is terrifying.**
TDD/BDD fix: Change anything. Re-run tests. If they pass, **you're good**.

<br>

**Problem: AI generates technical debt.**
TDD/BDD fix: Tests enforce contracts. Debt can't hide behind "it works on my machine."

<br>

**Problem: Knowledge is lost when the prompt is gone.**
TDD/BDD fix: The test suite *is* the **permanent, executable documentation**.

---

### The Flywheel Effect

```text
     Write better tests (human skill)
            │
            ▼
     AI generates better code ──────► Higher confidence
            │                                │
            ▼                                ▼
     More refactoring courage          Ship faster
            │                                │
            ▼                                ▼
     Cleaner codebase              Happier stakeholders
            │                                │
            └────────────────────────────────┘
                   Continuous improvement
```
---

Over time:
- Your **test suite becomes your most valuable asset** — more than the implementation
- Implementation becomes **disposable and regenerable**
- Engineers focus on **domain logic, edge cases, and correctness** — not syntax

---

<!-- _class: small-text -->

### TDD/BDD + AI: A Maturity Model

```text
Level 0: RECKLESS VIBE CODING
  "Prompt → Ship → Pray"
  No tests. No review. Maximum speed, maximum risk.

Level 1: CAUTIOUS VIBE CODING
  "Prompt → Review → Ship"
  Manual review of AI output. Better, but doesn't scale.

Level 2: TEST-AFTER VIBE CODING
  "Prompt → Ship → Write tests later"
  Tests confirm what AI wrote, not what you needed.

Level 3: RESPONSIBLE VIBE CODING (TDD/BDD)              ◄── TARGET
  "Write tests → Prompt → Verify → Ship"
  Tests define correctness BEFORE code exists.
  AI writes to a specification. Verification is automated.

Level 4: FULLY AUTONOMOUS LOOP
  "Write tests → AI generates + runs + iterates → Human reviews → Ship"
  The AI agent runs tests itself, iterates on failures,
  and only surfaces the final result for human review.
```

---

### What Changes in Engineering Culture

| Traditional Mindset                       | AI-Era / TDD Mindset                           |
|-------------------------------------------|-------------------------------------------------|
| "I need to write the implementation"      | "I need to define what correct means"           |
| "Tests are extra work"                    | "Tests are the primary work product"            |
| "My code is my craft"                     | "My specifications are my craft"                |
| "Good engineers write elegant code"       | "Good engineers define precise behavior"        |
| "Don't touch it, it works"               | "Regenerate it — the tests will catch problems" |
| "I don't have time for tests"            | "I don't have time to NOT write tests"          |

---

### For Skeptics: "Isn't Writing Tests Just As Much Work?"

**Yes, but the payoff equation has changed.**

**Before AI:**
- Writing tests = effort
- Writing implementation = effort
- Total effort = tests + implementation *(many engineers skipped tests)*

**With AI:**
- Writing tests = effort **(your primary job)**
- Writing implementation = **near-zero effort** *(AI generates it)*
- Total effort ≈ tests — but now they *also* serve as your **prompt**, your **verification**, your **documentation**, and your **safety net**

<br>

> **Tests went from "nice to have" to "the only thing you need to write."**
> The ROI of TDD/BDD has never been higher than it is right now.

---

<!-- _class: section-header -->

## Key Takeaways

---

### Five Things to Remember

<br>

1. **AI is a force multiplier** — it amplifies your existing practices, good or bad

2. **Vibe coding is real and it's not going away** — the question is whether you do it recklessly or responsibly

3. **TDD/BDD is the natural guardrail** — it gives AI a precise spec and gives you automated verification

4. **The engineer's role is evolving** — from "person who types code" to "person who defines correctness"

5. **Tests are now the most valuable artifact** — implementation is disposable; specifications are not

---

### The Future Software Engineer

```text
┌──────────────────────────────────────────────────┐
│                                                  │
│       THE AI-ERA SOFTWARE ENGINEER               │
│                                                  │
│    ✦  Defines WHAT, not HOW                      │
│    ✦  Writes specifications, not boilerplate     │
│    ✦  Reviews & curates, not types               │
│    ✦  Owns quality, not keystrokes               │
│    ✦  Thinks in behaviors & edge cases           │
│    ✦  Uses AI boldly, verifies rigorously        │
│                                                  │
│    Tools change. Engineering rigor doesn't.      │
│                                                  │
└──────────────────────────────────────────────────┘
```

---

<!-- _class: lead invert -->

## Closing Thought

> *"Vibe coding isn't the problem.*
> *Vibe coding **without verification** is the problem.*
>
> *TDD and BDD have always been about defining correctness before writing a single line of implementation.*
>
> *In the AI era, that discipline isn't just a best practice — it's the **only practice** that lets you move fast and stay responsible at the same time."*

---

<!-- _class: lead invert -->
<!-- _paginate: false -->

# Thank You

### Questions & Discussion
