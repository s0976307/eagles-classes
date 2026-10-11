# Assignment #1 — Introduction to the Activity Diagram
Due: Sat 12 Sep 2026, 23:59 (per COURSE-INFO.md deadline board)

> **STATUS — LATE. Corrected 2026-10-05 19:30.**
> **Real due date is Sat 19 Sep 2026** per the Canvas **Grades** page — not Sep 12 as this
> folder's name says. The folder name is stale; renaming would break every link, so it stays.
> **16 days late.** Canvas records it 🔴 **MISSING**, not zeroed.
> At −10%/day the penalty exceeds 100%: without an extension this scores zero regardless of
> quality. The syllabus grants extensions **upon request** — that request is the only thing
> between this work and a 0, and the **Midterm Grade posts Sun 11 Oct.**
> Draft email: [A3/email-draft-inomoto.md](../A3%20User%20Story%20(Oct%2003)/email-draft-inomoto.md).
> Priority order: [RECOVERY-PLAN.md](../RECOVERY-PLAN.md) — **A#3 outranks this.**
>
> Study on record: Mon 2026-09-28, 18:22 — Ch. 1–4 review covering swimlanes, parallel
> activity, decision vs. merge. Directly relevant to Q2, Q8, Q9.

## Canvas prompt (verbatim, from Assignment_1.pdf)

> Submit your answers to the following exercises as a Word document. Name your document
> "Assignment-1-LastnameFirstinitial," for example "Assignment-1-SmithJ." Include your name
> in the document.
>
> Use textbook activity diagrams Figure 2-12 Current State (p.51) and Figure 2-13 Future State
> (p.53) to answer these questions.
>
> 1. What is the overall name of the process diagrammed in the two figures?
> 2. Name the actors in Fig. 2-12 Current State.
> 3. Compare the current and future states of this process. Which current state actor is missing
>    from the future state and why?
> 4. Explain the meaning of the two Fig. 2-13 dashed line ovals that cross all swim lanes.
> 5. Explain the meaning of the round symbol with an "X" in the Fig. 2-12 CUSTOMER swim lane.
> 6. Explain the meaning of the rectangular dashed line boundary that encloses the Fig 2-12
>    actions "Scan item" and "Add item to sale."
> 7. Explain the meaning of the [=0] and [>=1] specifications in the Fig. 2-13 CUSTOMER swim lane.
> 8. Explain the meaning of the unlabeled diamond symbol located just before "Exit Store" in
>    the Fig. 2-12 CUSTOMER swim lane.
> 9. Explain the purpose of each of the vertical bars located in the Fig. 2-13 CUSTOMER swim lane.
> 10. Identify one of the Fig. 2-13 actions that would likely require further clarification using
>     either additional action symbols or with supplementary documentation. Briefly explain why.

## Rubric (verbatim)

**None published in the prompt.** 10 points total (COURSE-INFO.md: assignments are 10 pts
each, not individually weighted). Working assumption: ~1 pt per question. If Canvas shows a
rubric, paste it here and delete this line.

## Deliverables

- [ ] One Word `.docx` — **no diagram to draw for this assignment**
- [ ] Filename exactly `Assignment-1-<Lastname><Firstinitial>.docx`
- [ ] Your name inside the document
- [ ] Ten numbered answers, matching the prompt's numbering
- [ ] Copy dropped into `06 Submitted/`

> Note the deviation from the standing workflow: A1 asks you to **read** two textbook
> activity diagrams, not build one in draw.io. Nothing goes in `04 Diagrams/` for this one.

## Ambiguities to resolve

| Question | Ambiguity | Resolution path |
|---|---|---|
| Whole assignment | Is this past due, or extended? | **Ask the professor.** Blocking. |
| All | Answer length — one sentence or one paragraph? | Not specified. Assume 2–4 sentences per item; Q10 explicitly says "briefly." |
| 2 | Does "actor" mean only human roles, or does the POS System swimlane count? | The figure gives four swimlanes. Say which you're counting and why — that reasoning is the point, and it is defensible either way. State your definition of "actor" once, up front. |
| 4, 6 | Are the dashed ovals and the dashed rectangle standard UML notation, or the textbook's own convention? | **Read the prose around pp. 51–53.** Do not answer these two from generic UML knowledge alone — the book's caption/text is the authority. See `answer-scaffold.md`. |
| 10 | "Further clarification" — clarification for whom? | Reasonable reading: a developer or analyst who has to implement or fully specify the step. Say which reading you're using. |

## Analysis — the eight questions

Applied to the *grocery checkout system shown in the figures*, not to the assignment.
Fill this in from the figures before writing prose. It is what makes Q3 and Q10 answerable.

- **Who:** (list the swimlanes — Fig. 2-12 has four, Fig. 2-13 has three)
- **Why:**
- **What:**
- **Data:** (what does "Add item to sale" actually write? this feeds Q10)
- **Process:** (trace the flow start → end in each figure, once, out loud)
- **Rules:** (every bracketed guard you can find)
- **Interface:** (what changed between figures — this feeds Q3 and Q4)
- **How:**

## Model

Trace both figures node by node before writing a single answer. Fill this table yourself
from pp. 51 and 53 — the assignment PDF reproduction is small, the textbook is legible.

| | Fig. 2-12 Current State | Fig. 2-13 Future State |
|---|---|---|
| Swimlanes | | |
| Start node | | |
| Actions, in order | | |
| Decisions + guards | | |
| Forks / joins | | |
| Regions | | |
| End node(s) | | |

The single diff that falls out of this table is the whole of Q3, and most of Q4.

## Diagram blueprint

N/A — no diagram deliverable.

## Self-check before submitting

- [ ] All ten questions answered, numbered to match the prompt
- [ ] Q3 and Q10 give a **reason**, not just an identification — both ask "why"
- [ ] Every notation claim (Q4–Q9) traced to the textbook or to UML, and I can say which
- [ ] I can explain every answer out loud without notes
- [ ] Name in the document; filename matches the required pattern exactly
- [ ] Copy saved to `06 Submitted/`
