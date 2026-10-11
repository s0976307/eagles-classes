# Ch. 1 — Introduction to Systems Analysis

Week 1 · covered 2026-08-31 / 09-02 · **Exam #1 (Ch. 1–4), Sat 2026-09-26**

> **Provenance.** Derived from Chapter 1 material the Commander supplied on 2026-09-02,
> as summarized by a prior session — not read directly from Spurrier & Topi or from the
> professor's slides. Everything here is *reported* framing. **Verify against the actual
> chapter and lecture notes before the exam.** Where this file and the professor
> disagree, the professor wins.

## 1.1 — Business Analyst vs. Systems Analyst

| | Primary concern | Emphasis |
|---|---|---|
| **BA** | Business / organizational needs | Business requirements |
| **SA** | Information technology | The information-system solution |

The BA identifies problems and opportunities · elicits stakeholder needs and constraints
· develops business requirements · develops a business solution · manages change.

**The catch — don't over-memorize the split.** The professor states that a good systems
analyst is *also* a business analyst, and that Spurrier & Topi merge the roles to a
degree.

- ❌ Wrong: "BA and SA are completely separate jobs."
- ✅ Right: "They overlap; BA emphasizes organizational/business requirements, SA
  emphasizes the IT solution."

## 1.2 — Business analysis

Two definitions given:

- **BABOK** — enabling organizational change by defining needs and recommending
  solutions that deliver stakeholder value.
- **Spurrier & Topi** — understanding how the business currently operates and
  determining how it should change to support organizational goals through a software
  project.

```
CURRENT STATE → understand the problem → identify needs
   → define requirements → DESIRED FUTURE STATE → recommend solution
```

**Technology bias warning.** The BA must not assume "we need software." A business
solution does not necessarily need a technology component. Don't solve the wrong problem
beautifully.

## 1.3 — Discover → Structure → Transform → Communicate

1. **Discover** — what is happening now? Understand the current state.
2. **Structure** — organize what you discovered. Modeling lives here.
3. **Transform** — what should the future state look like? Identify required
   capabilities and features.
4. **Communicate** — explain current and future states to the appropriate audience.

**Intelligent modeling** *(the professor's term)* — create artifacts when they add value,
and only to the level of detail required for their purpose. Note this is the same term
the syllabus uses under the Hybrid approach (BDUF / BRUF).

## 1.4 — Requirements

> **A requirement is a usable representation of a need.**

Need vs. want is the distinction that matters. A requirement may be represented as a
sentence, a formula, or a diagram.

| Category | Describes | Test question |
|---|---|---|
| **Business** | Business mission, activities, rules, information, external interactions needed to accomplish the mission | What does the *organization* need? |
| **Functional** | Observable system behavior | What must the *system do*? |
| **Non-functional** | Characteristics, quality attributes, constraints | How well, under what constraints, with what qualities? |

**Non-functional examples from the chapter:** accessibility · usability · auditability ·
efficiency · legal/licensing constraints · maintainability · performance · safety ·
security.

### Classification drill

Cover the answers.

| | Statement |
|---|---|
| A | The inspection department needs to reduce the time required to produce infrastructure reports. |
| B | The system shall allow inspectors to generate a PDF inspection report. |
| C | Inspection reports must be generated within 5 seconds. |
| D | Only authorized inspectors may access inspection records. |
| E | The organization needs better visibility into unresolved infrastructure defects. |

<details><summary>Answers</summary>

**A** Business — an organizational objective.
**B** Functional — observable system behavior.
**C** Non-functional — performance constraint.
**D** Non-functional — security / access constraint.
**E** Business — an organizational need.

Pattern: "the organization/department needs…" → business. "The system shall…" →
functional. A number, a limit, or a quality word → non-functional.
</details>

## 1.5 — Elicit vs. Gather

The professor's specific framing:

- **BAs elicit** requirements — assumes users have only a *general* idea of what they need.
- **SAs gather** requirements — assumes users already have a *clear and detailed* idea.

> ⚠️ **Exam risk.** This is the professor's distinction. Much of the industry and BABOK
> literature uses "elicit" as the preferred general term and treats "gather" as
> discouraged — because it implies requirements are lying around waiting to be collected.
> On this exam, answer with the professor's framing. Flagged because a textbook or
> outside source may contradict it.

**Discovery techniques:** interviews · workshops · focus groups · brainstorming ·
observation · surveys/questionnaires.

Why it matters — "we need a better inspection system" is not a requirement, it's a
starting point:

```
"We need something better."
  → Why? → What's wrong now? → Who experiences the problem?
  → What outcome is needed? → What capabilities are required?
  → What constraints exist?
```

That chain is analysis.

## 1.6 — Perfect technology

Essential analysis separates the business need (**WHAT**) from current technology
(**HOW**). Start by imagining a perfect-technology environment:

- infinite storage · error-free processing · infinite speed · infinite funds

*Then* apply real-world constraints to find the best feasible solution.

🚨 Analysis error: "We can't do that because our database can't…" — said before the need
is established. Determine what the business needs first; determine feasibility second.

## 1.7 — Optimal vs. feasible

**Optimal** — theoretically maximizes/minimizes all objectives while satisfying all
constraints. Often impractical.
**Feasible** — the acceptable solution meeting as many objectives and constraints as
possible.

```
PERFECT SOLUTION → probably impossible → TRADE-OFFS → FEASIBLE SOLUTION
```

Cost, schedule, technical limits, politics, risk, and organizational priorities are what
force the trade.

## Core card

| Concept | Remember |
|---|---|
| BA | Business / organizational focus |
| SA | Information technology / system focus |
| Business analysis | Understand needs → recommend value-producing change |
| Requirement | Usable representation of a need |
| Business requirement | Organizational need / goal |
| Functional requirement | What the system does |
| Non-functional requirement | Quality, constraint, or characteristic |
| Elicit | Discover needs (general idea) — BA |
| Gather | Collect detailed requirements (clear idea) — SA |
| Analysis | Determine the **WHAT** |
| Design | Determine the **HOW** |
| Current state | Where we are |
| Future state | Where we want to be |
| Optimal | Theoretical best |
| Feasible | Practical, acceptable |

Analysis = WHAT, Design = HOW is corroborated by the syllabus outline and
[MODELING-REFERENCE.md](MODELING-REFERENCE.md). It is the distinction most likely to
appear repeatedly.

## Open exercise — not yet answered

Scenario: *"Students wait too long to get answers about their financial-aid paperwork."*

Identify: the business problem · one business requirement · one functional requirement ·
one non-functional requirement · one stakeholder · and whether each is WHAT or HOW.

**Status: awaiting the Commander's own reasoning.** Record the attempt here, then the
critique.
