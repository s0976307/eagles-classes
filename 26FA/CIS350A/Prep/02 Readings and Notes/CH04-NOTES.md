# Ch. 4 — User Stories and User Interface Modeling

Weeks 4–5 · **47 slides** · deck revision `26FA-1` (current) · Exam #1 (Ch. 1–4)
**Directly relevant to Assignment #3 — user story, due Sat 2026-10-03.**

> **Provenance: SOURCE.** Extracted directly from
> `Systems Course Material\CIS350 Chapter 4 - User Stories and UI Models.pptx` on
> 2026-09-28. Slide numbers cited. Figure slides (2, 10, 23–29, 33) are images — open the
> deck for Figures 4-3 through 4-8, the MoSCoW graphic, and the stakeholder map.

## 4.1 — Features vs. designs *(slide 3)*

| | Question | Expressed as |
|---|---|---|
| **Features** | **What** new IS capabilities does the organization need to achieve its goals? | A **user story**, often with acceptance criteria |
| **Designs** | **How** should the system be designed and implemented to provide those capabilities? | design specs |

The system **"whats"** vs. the system **"hows."** Same WHAT/HOW axis as Ch. 1 analysis vs.
design — it keeps returning because it is the spine of the course.

## 4.2 — Intelligent modeling *(slide 4)*

> Creating requirements artifacts **only when they add value** in a given project context
> at a particular stage — **"just-in-time" modeling.**

Create artifacts only at the level of sophistication the project needs as a whole. *If a
handwritten draft is sufficient and there is no archival need, don't spend extra time
creating a production-quality document.*

Same term appears in Ch. 1 and in the syllabus under Hybrid (BDUF/BRUF). Three sources —
expect it on the exam.

## 4.3 — User story *(slides 5–7)*

> A brief narrative description of a system feature (capability) that includes a **user
> role**, a **need** important to that role, and a **justification** for the need.

**Components:** Who — actor, role, or persona · What — goal, need, or desire · Why —
justification.

**Format:** `As a <role>, I want <goal>, so that <benefit>.`

Deck example:

> As a retail store customer, I want to be able to easily find a product that meets my
> needs, so that I can complete picking up my purchases accurately, efficiently, and
> without delays.

**Properties (slide 6):** expresses ideas for business requirements · **usually not
sufficient by itself** for a business requirement · basis for discussion between BA and user.

### The "shall" alternative *(slide 7)*

A business need can also be documented as a single-sentence **"Shall" statement**:

`A <role> shall be able to <goal>.`

> A retail store customer shall be able to easily find a product that meets his or her needs.

**Know both forms.** A question may ask you to convert between them.

## 4.4 — Acceptance criteria *(slides 8, 11–12)*

> Criteria that must be met for the solution to be **acceptable by the requesting user**.
> Constraints that limit acceptable solutions. **Foundation for user acceptance tests.**

Two kinds:

| | Covers |
|---|---|
| **Functional** | **Variations** — complexities or specific details · **Exceptions** — error conditions |
| **Nonfunctional** | Operational characteristics that don't directly affect functional behavior |

Deck example criteria (slide 12) — note that the last one is an explicit **OR**, which is
what makes it a constraint on acceptable solutions rather than a design:

1. Available on at least the two most popular mobile computing platforms.
2. User can identify the product by entering (part of) its name or its UPC code.
3. If unavailable, indicate whether the store typically carries it and when it is expected back.
4. Communicate location as an aisle/bay combination **OR** on a map showing directions
   from the customer's current location.

## 4.5 — Prioritization: MoSCoW *(slides 9–10)*

Needed to create and manage the **product backlog** so the most valuable stories are built
first.

**Rank ordering** (1 = most valuable, then 2, 3, 4…) is common in **Agile Scrum with
flexible scope**, but breaks down at scale — *how much more important is story 73 than 74?*

**MoSCoW** (Clegg & Barker, **1994**) supports **semi-flexible scope**:

| | |
|---|---|
| **M**ust have (MH) | |
| **S**hould have (SH) | flexible portion of scope |
| **C**ould have (CH) | flexible portion of scope |
| **W**on't have (WH) | |

- **MVP = all MH stories and their predecessors.**
- **Each acceptance criterion can carry its own MoSCoW priority** — not just each story.

## 4.6 — INVEST *(slide 16)*

Criteria for evaluating a user story:

| | |
|---|---|
| **I**ndependent | of other user stories — cf. module cohesion and coupling |
| **N**egotiable | for discovery changes |
| **V**aluable | to the user — cf. MoSCoW |
| **E**stimable | sized, so it can be prioritized |
| **S**mall | completable within an iteration |
| **T**estable | according to acceptance criteria |

## 4.7 — Epics and themes *(slides 5, 14–15)*

**Epic** — a special user story summarizing a **broad range** of user needs (multiple
regular stories); collects/categorizes/groups related stories requiring **more than a
single delivery cycle (sprint)**.

- Used in agile **planning**.
- **Not directly used for construction or configuration.**
- Can implicitly define high-level activity **dependencies**.
- Can be part of a **theme** — high-level objectives tying development work to the
  organization's **strategic goals**.

## 4.8 — User acceptance tests: Gherkin *(slide 13)*

UAT can be formulated as an extension of user stories.

- **Cucumber** — tool that automates UAT in a **behavior-driven development (BDD)** style.
- **Gherkin** — the language Cucumber uses to define test cases.

```
Given: a precondition
When:  the actor does something
Then:  some outcome results

Given: User is on logon screen
When:  User enters correct logon ID
And:   User enters correct password
Then:  User is allowed access to the web page
```

Three tool/term pairs worth keeping straight: **Cucumber** = the tool, **Gherkin** = the
language, **BDD** = the style.

## 4.9 — Why UI models *(slide 17)*

> User stories were never intended to be full requirements specifications. They have been
> characterized as **"a promise of a conversation."**

The written form isn't rich enough to ensure stakeholders agree on direction.
**Solution: integrate simple UI models with user stories.**

## 4.10 — Wireframe vs. mock-up vs. prototype *(slide 20)*

**Assignment-critical.** Three separate deliverables appear across the semester —
#4 wireframe, #8 mockup.

| | Definition | Focus |
|---|---|---|
| **Wireframe** | Blueprint of component (UI element) layout | **functionality** |
| **Mock-up** | **Static** representation of the final product | **finished look** |
| **Prototype** | **Interactive** model with limited functionality | "demo" at the end of an agile iteration, for feedback or possible release |

Purpose of initial UI modeling (slide 21): capture a **simplified but sufficient** subset
of essential characteristics so the target can be evaluated and improved · elaborate the
ideas in the user story's words as a communication mechanism · explore **feasibility** of
UI/UX ideas.

Figures 4-3 → 4-8 (slides 23–28) are the worked mobile examples, including a **mock-up
with a navigation sequence** (4-6) and generic wireframe/mock-up comparisons.

## 4.11 — Project and system types *(slide 18)*

| | |
|---|---|
| **Greenfield** | UI designed from scratch to best meet user story goals — e.g. automating a completely manual system |
| **Brownfield** | UI should be **consistent with existing standards**; significant overhaul is unusual, but attributes can still be enhanced |

| | |
|---|---|
| **System of record** ("back office") | Authoritative data source — transaction database |
| **System of engagement** ("front office") | Facilitates user interaction and communication — UI/UX models |

## 4.12 — Usability design *(slide 19)*

**HCI design** concerns how effectively people can operate and control a machine, based on
**feedback loops** between machine and person. Seven criteria:

suitability for the task · self-descriptiveness · controllability · conformity with user
expectations · error tolerance · suitability for individual customization · suitability
for learning

| | Focus |
|---|---|
| **UI design** | product **layout** — position of buttons, icons, entry boxes. Microsoft **Fluent**, Google **Material** |
| **UX design** | overall **feel and functionality** |

## 4.13 — Design thinking *(slide 29)*

Iterative approach to complex problems, resembling **agile**. Understand → Envision →
Prototype, expanded as: **Empathize** (develop user profiles or **personas**) → **Ideate**
(brainstorm) → **Prototype** (storyboard, wireframes, mockups) → **Test**. Human- or
user-centered design of HCI.

## 4.14 — Feasibility dimensions *(slide 30)*

Initial evaluation during preliminary investigation; **re-evaluated throughout** the
project. Nine dimensions — Ch. 11 expands these:

economic · financial · technical · schedule · political · operational · legal/regulatory/
contractual · environmental sustainability · **ethical (*should* it be done?)**

## 4.15 — Stakeholder analysis *(slides 31–33)*

BABOK: a stakeholder is *"a group or individual with a relationship to the change, the
need, or the solution."* The **RACI matrix** and **stakeholder mapping** support the
**communication plan**.

**RACI** (pronounced "ray-see"):

| | |
|---|---|
| **R**esponsible | does the work |
| **A**ccountable | answers to higher authority for correct completion |
| **C**onsulted | provides knowledgeable opinions (SME) |
| **I**nformed | needs to be kept up to date on progress |

**Stakeholder mapping** — influence × interest grid: high/high → **manage closely** ·
high influence, low interest → **keep satisfied** · low influence, high interest →
**keep informed** · low/low → **monitor**.

Roles list (slide 31) includes project sponsor/product owner, agile coach/scrum master,
SMEs, QA/QC, DBA, testers and trainers, vendors and consultants, senior executives.

## 4.16 — Technique selection and triangulation *(slides 34–36)*

The BA should use **multiple tools** to view a problem from different perspectives.
**"Triangulation"** increases confidence that the understanding is valid.

| Lens | Techniques |
|---|---|
| **Process** | user story, activity diagram |
| **Data / Domain** | ER diagram, class diagram, **dataflow diagram** |
| **User Interface** | use case, wireframe, mock-up, prototype |
| **Logic** | Structured English, business rules, decision trees and tables |

> This is the same four-lens structure as
> [MODELING-REFERENCE.md](MODELING-REFERENCE.md) — and it maps directly onto the nine
> assignments. Confirmation the assignments are one system seen four ways.

**Audience (slide 35):** split the solution into **human-centric (manual)** and
**program-centric (automated)** parts. Business stakeholders get the high-level process
view (the "what") and business-rule validation; lower-level "how" becomes written
procedures and policy manuals. IT stakeholders get automation details detailed enough for
a developer to produce working software.

**Choosing (slide 36):** a technique good for *organizing the analyst's* understanding may
be poor for *validating with stakeholders* — you may use one for analysis and another for
presentation. Text is simplest but ambiguous; graphics are concise but need symbol
knowledge; **combination is most common** — annotated diagrams plus textual detail.

## 4.17 — Elicitation techniques *(slides 37–47)*

Eight methods (slide 37): review existing documentation · observation · interviews ·
surveys and questionnaires · facilitated sessions · focus groups · competitive analysis ·
**system (not user) interface analysis**.

**Review documents (38)** — company policy manuals, IT manuals/forms/screens/reports.
Minimal stakeholder interaction; learn the organization's terminology and culture; note
documentation gaps. *Don't waste stakeholder time on answers available in documents.*

**Observation (39)** — three named effects: **Hawthorne**, **observer**, **"novelty"**.
Watch for variation between the process **as documented** ("work-to-rule"), **as
described** by the worker, and **as observed** (unconscious workarounds and shortcuts).
Take notes, limit verbal questions, **job shadow** at all relevant levels, and consider
timing — seasonal fluctuations, month-end close.

**Apophenia (40–41)** — the tendency to construct meaningful patterns from random data.
**Pareidolia** is the visual/auditory subset: animal shapes in clouds, constellations, the
man in the moon, the Martian face, EVP. The *Giant Claw* (1957) example: without other
evidence, **any pattern can be made to fit a series of random dots.** An analyst's
discipline against over-reading data.

**Interviews (42)** — initiate (decide who via stakeholder analysis, familiarize yourself)
→ plan (agenda, specific objectives; structured/semistructured/unstructured; closed vs.
open questions) → execute (take notes; **record only with permission**) → close (thank,
summarize and confirm understanding, ask for further thoughts, follow up).

Question sequencing — three named patterns:

| Pattern | Shape |
|---|---|
| **Pyramid** | closed → open |
| **Funnel** | open → closed |
| **Diamond** | pyramid → funnel |

**Surveys (43)** — multiple locations or large participant counts; may be third-party;
wording and sequence matter.

**Facilitated sessions (44)** — **not ordinary group meetings**: structured, planned, with
roles **facilitator, recorder, timekeeper**, often off-site. Used for kick-off, detailed
elicitation (**IBM's Joint Application Design — JAD**), brainstorming. Use **BA pairing**
if no independent facilitator is available.

**Focus groups (45)** — randomly selected individuals representing a demographic or
viewpoint; typically **external customer product feedback**; led by trained
facilitators/moderators, **not usually conducted by the BA**, often third-party. **Not an
interview** — closer to brainstorming on a specific topic.

**Competitive analysis (46)** — who do stakeholders consider the competition; how do the
same customers view competitors' products and services.

**System interface analysis (47)** — identify interfaces affecting or affected by the
project. Refer to the **context diagram**, **use case diagram**, **context-level DFD**.
Helps identify additional stakeholders who could serve as SMEs.

---

## Open exercise — not yet answered

Write **one** user story in the course's exact structure for this scenario:

> A Niagara University student wants a system that shows which assignments need attention
> today, because assignments get buried across multiple courses.

```
As a __________,
I want __________,
so that __________.
```

No implementation details. WHO → WHAT → WHY only.

**Status: awaiting the Commander's own reasoning.** Then acceptance criteria → UI model →
wireframe vs. mock-up vs. prototype.

> Hint on the trap without giving it away: "shows which assignments need attention today"
> is very close to describing a screen. A user story names the **capability and the
> benefit**, not the display. Check your `I want` against §4.1 — if it reads like a
> design, it belongs in the UI model instead.
