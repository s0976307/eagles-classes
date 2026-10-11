# Study Guide — User Stories

Source: `Study Guide - User Stories.pdf` · **Rev. 13-Aug-2023** · 3 pages
**Directly governs Assignment #3** (user story + two acceptance criteria).

> **Provenance: SOURCE, verbatim.** Supplied by the Commander 2026-10-05 as readable text —
> no extraction loss. Quotes below are the guide's own words.

Textbook reference: Spurrier & Topi (2021), **pp. 97–101**. Note this is the **1st edition**;
the course requires the 2nd (2025), so page numbers may have shifted. Same edition mismatch as
the Activity Diagram guide.

## What a user story is

> Informal descriptions of **desired system features from the perspective of a system user**.
> They are **key to agile modeling but are compatible with the traditional SDLC model.**

> **The analyst converts the user story into system requirements** useful for the design and
> construction of the system.

So the story is an *input* to requirements, not the requirement itself. This matches Ch. 4
slide 6: *"usually not sufficient by itself for a business requirement."*

## The index card — and who does what

> User stories can be written down on **3x5 or 4x6 index cards** and typically consist of a
> **single sentence**. The analyst writes **more formal requirements on the back of the card**
> and uses the story card to **verify his or her understanding** of the desired feature.

> The **customer / client / product owner will assign a priority** to the story and the
> **analyst / developer will assign an estimate** of how long it would take to implement.

**Priority = business side. Estimate = technical side.** That division is a clean
matching-question target, and it is the reason MoSCoW (Ch. 4) is the *customer's* tool while
INVEST's "Estimable" is the *developer's* concern.

## What a user story covers — and what it doesn't

> The analyst is an **investigator** trying to discover the **"Who, what, where, when, how, and
> why"** of a system.
>
> User stories help illustrate the **who, what, why, and perhaps the when and where** of a
> specific feature.

Read that carefully: of the six investigative questions, the user story carries **who, what,
why**, sometimes when/where — and **not how**. The *how* is design. This is the WHAT/HOW line
again, stated through a different lens.

> User stories form the **starting point of a collaborative discussion** between user and analyst.

## The template

```
AS A <role>, I WANT <desire> SO THAT <benefit>.
```

> "As a student, I want to be able to view my completed courses online so that I can plan the
> remainder of my course work."

**This is the same example the Ch. 2 deck gives on slide 13** — two independent sources, the
professor's own worked case. If you want to know the register he grades against, it is this
sentence.

## Acceptance criteria

> To keep the user story **concise**, acceptance criteria can be **appended separately** to
> indicate **constraints or additional user requirements that must be met if the solution is to
> be acceptable to the user.**

Simple form:

> "Completed courses must be displayed in **chronological order**."

### Given-When-Then

> An agile-oriented acceptance criteria format is Given-When-Then, **usually used to develop
> test cases**.

```
GIVEN <some context>, WHEN <some action is taken>, THEN <a particular set of responses should result>.
```

> "**Given** that I have completed at least one course, **When** I request a list of my
> completed courses, **Then** the completed course data displayed must include Course ID,
> Course Description, Semester Taken, Date Completed, Letter Grade, and Grade Points Assigned."

> **Study this example — it is the calibration for "specific and testable."** It names a
> precondition, a single user action, and **six enumerated data fields**. A grader can check it
> without asking you a follow-up question. That is the bar.

Ch. 4 adds the tooling: **Cucumber** is the tool, **Gherkin** the language, **BDD** the style.

## The "Shall" alternative

> "Shall" is **more often used with traditional systems development versus agile** for
> requirements or specifications, but can also be used to **supplement** user stories in an
> agile context.

> "The system **SHALL** display completed courses in chronological order."

Ch. 4 slide 7 gives the role-form variant: `A <role> shall be able to <goal>.` Know both
directions — a question may ask you to convert a story into a shall-statement.

---

## Applying this to Assignment #3

The prompt asks for four parts and says plainly that **"user friendly" is too vague**. The
guide tells you what the professor accepts instead.

| Part | What the guide says to do |
|---|---|
| 1. Narrative of the process | Plain description of a real service you've used. Current state. |
| 2. Future-state need | A desire, not a design. If it names a screen or a technology, it's drifted into *how*. |
| 3. The user story | Exactly `As a <role>, I want <goal>, so that <benefit>` — one sentence, who/what/why only. |
| 4. Two acceptance criteria | Constraints that must be met for the solution to be acceptable. **Specific and testable.** |

**Two reliable ways to make a criterion testable:**

1. **Constraint form** — "must be displayed in chronological order." Testable because there is
   exactly one way to check it.
2. **Given-When-Then** — precondition, action, enumerated result. The guide's own example lists
   six required fields; enumeration is what makes it checkable.

**The two failure modes:**

- **Too vague** — "easy to use," "fast," "convenient." The prompt rejects this by name.
- **Drifted into design** — "a blue button on the dashboard." That's a UI model (Ch. 4), not a
  criterion. A criterion says what must be *true*, not what must be *built*.

Then run **INVEST** (Ch. 4 slide 16): Independent · Negotiable · Valuable · Estimable · Small ·
**Testable** — and note the last one is just the acceptance criteria doing their job.

## Further reading listed in the guide

Champagne (2020), *Seven Steps to Mastering Business Analysis*, 2nd ed. · Mark Shead, *Agile
User Stories* (2016) — https://youtu.be/apOvF9NVguA · Spurrier & Topi (2021) · Wikipedia,
*User story*.

---

## Study guide status

| Guide | Covers | State |
|---|---|---|
| **User Stories** | **A#3** | ✅ **captured — this file** |
| Activity Diagram | A#1, A#5 | ⚠️ was captured 2026-09-28, **lost in the rollback**; PDF still in `Systems Course Material\` |
| Entity Relationship Diagrams | A#2, A#6 | ❌ not extracted |
| Use Case Diagrams | A#7 | ❌ not extracted |
| Structured Programming | A#9 | ❌ not extracted |
| BA Tools | general | ❌ not extracted |
| **ANSI Flowchart** | referenced twice | ❌ **not present in the course materials at all** |

The four unextracted PDFs need poppler (`winget install --id oschwartz10612.Poppler`) — or you
can paste them in as text the way you did this one, which worked perfectly and lost nothing.
