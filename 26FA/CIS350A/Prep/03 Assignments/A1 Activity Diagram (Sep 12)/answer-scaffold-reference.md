> **Recovered 2026-10-11 from `H:\My Drive\03 Coursework\2026 Fall\Intro Systm Analysis
> 26FA-CIS350A\Prep\`,** where session my-drive-a4 had consolidated it. It is **not** a
> duplicate of `answer-scaffold.md` in this folder, despite sharing that filename at the
> source. The two are different documents:
>
> - **`answer-scaffold.md`** (this folder, regenerated 2026-10-05) is the **fillable
>   worksheet**: blank fields to complete, plus a now-superseded extension-request block.
> - **This file** is the **reference** the worksheet replaced: the Word document skeleton,
>   the provenance markers, and the notation table.
>
> The notation table is the part worth having. Questions 4 through 9 of A#1 turn on telling
> a decision from a merge and a fork from a join, which is the single discrimination the
> assignment is built to test. That table was lost from this tree when the worksheet
> overwrote it. Nothing here was edited; only this header was added.
>
> Still true and unchanged by the recovery: **the answers are not in here.** They come off
> the textbook figures on pp. 51 and 53, and the reproductions inside `Assignment_1.pdf`
> are too small to read reliably.

---

# A1 — answer scaffold

**What this file is:** the skeleton of your Word document plus, per question, the concept
being tested and what a complete answer must contain. **It contains no answers.** You write
those from the textbook figures on pp. 51 and 53, and you should be able to defend every one
out loud.

**Provenance — read this before you trust anything below.**

- Items marked **[UML]** are standard UML activity-diagram notation. Reliable.
- Items marked **[CHECK BOOK]** are things the Spurrier & Topi figures may notate their own
  way. The prose around pp. 51–53 is the authority, not generic UML and not me.
- The figure reproductions inside `Assignment_1.pdf` are too small to read reliably. Work
  from the textbook in Canvas → Course Materials.

---

## Document skeleton

```
Assignment-1-<Lastname><Firstinitial>.docx

<Your Name>
CIS 350A — Systems Analysis & Design — Fall 2026
Assignment #1: Introduction to the Activity Diagram
<date submitted>

[Optional, one line: your working definition of "actor," since Q2 turns on it.]

1. <answer>
2. <answer>
...
10. <answer>
```

Plain numbered list. No cover page, no headers beyond the above — nothing in the prompt asks
for them, and nothing in the prompt asks for a diagram.

---

## Notation you need before answering Q4–Q9

Activity diagrams answer **"what happens, in what order"** (MODELING-REFERENCE.md). Every
symbol below is a claim about *flow*: where it starts, splits, waits, chooses, repeats, stops.

| Symbol | Name | What it asserts about flow |
|---|---|---|
| Solid filled circle | Initial node **[UML]** | Where the activity begins |
| Filled circle in a ring (bullseye) | Activity final node **[UML]** | The **whole activity** stops |
| Circle with an X | Flow final node **[UML]** | **This one path** stops; other concurrent paths keep running |
| Rounded rectangle | Action **[UML]** | One step of work |
| Diamond, one arrow in, several out with `[guards]` | Decision node **[UML]** | A choice; guards are mutually exclusive conditions |
| Diamond, several arrows in, one out, no label | Merge node **[UML]** | Alternate paths rejoin; **no waiting** happens here |
| Thick bar, one in → several out | Fork **[UML]** | Flow splits into genuinely concurrent paths |
| Thick bar, several in → one out | Join **[UML]** | Flow **waits** until every incoming path arrives |
| Swimlane (partition) | **[UML]** | Who is responsible for the actions inside it |
| `[text]` on an arrow | Guard condition **[UML]** | That path is taken only if the condition holds |
| Dashed rounded rectangle around actions | Activity region **[CHECK BOOK]** | UML has several kinds; see Q6 |

**The distinction the exam will come back to:** a *decision/merge* is about **choosing one
of several paths**. A *fork/join* is about **several paths running at once**. Diamond =
choice. Bar = concurrency. Mixing these up is the most common activity-diagram error.

---

## Per question

### Q1 — Name of the process
**Tests:** that you can find the scope boundary of a diagram.
**Look at:** the label on the outer frame enclosing all swimlanes in both figures — not the
figure caption ("Current State Activity Diagram" is the *caption*, not the *process name*).
**Complete answer:** the process name, stated once. One sentence is enough.

### Q2 — Actors in Fig. 2-12
**Tests:** swimlane = responsibility.
**Look at:** the vertical labels down the left edge of Fig. 2-12. There are four.
**Complete answer:** list them. Then handle the ambiguity: one of the four is not a person.
Say whether you're counting it as an actor and give your one-line reason. Either position
earns the point if the reasoning is stated; an unexamined list may not.

### Q3 — Which actor disappears, and why
**Tests:** reading a current-state → future-state delta, which is the entire point of Ch. 2.
**Method:** set the two swimlane lists side by side. One label in Fig. 2-12 has no
counterpart in Fig. 2-13. Then find where that actor's work went — does the action vanish
from the future state entirely, or does it reappear inside a different swimlane, merged into
another step?
**Complete answer:** name the missing actor **and** explain the mechanism that eliminated
the role. "Why" is doing real work in this question. Tie it to the specific change visible
in Fig. 2-13's early actions — the future state introduces something the customer operates
that the current state does not have.
**Trap:** do not answer "because of automation." Name *what* automates *which* step.

### Q4 — The two dashed ovals crossing all swimlanes **[CHECK BOOK]**
**Tests:** whether you can tell notation from annotation.
**Key insight:** these ovals cross swimlane boundaries. UML flow elements do not do that —
an action belongs to exactly one partition. That is strong evidence these are not UML
constructs at all but the authors' **callouts**, drawn on top of the diagram to highlight
regions for the reader.
**What to do:** confirm against the prose on p. 53 and the figure caption, then say what
the two highlighted regions have in common. Look at *which* actions each oval encloses and
ask what is true of those actions that is not true of the rest of the diagram.
**Complete answer:** what the ovals are (annotation, not flow notation) **and** what the
author is drawing your eye to.

### Q5 — The circle with an X, Customer swimlane, Fig. 2-12
**Tests:** flow final vs. activity final. **[UML]**
**Look at:** what leads into it — trace the guard on that incoming arrow back to its decision
node. That guard tells you which real-world situation ends here.
**Complete answer:** name the symbol, state what it terminates, and contrast it with the
bullseye at the far right of the same swimlane. The contrast is the answer — state it
explicitly. Then say, in business terms, what has happened to that customer.

### Q6 — The dashed rectangle around "Scan item" / "Add item to sale" **[CHECK BOOK]**
**Tests:** how repetition is expressed in an activity diagram.
**Key observation:** those two actions sit in *different* swimlanes, and there is an arrow
looping back. Whatever the boundary is called, it groups a set of actions that execute
**once per item**, repeating until the collection is exhausted — that is the behavior the
diagram is expressing.
**What to check in the book:** UML offers more than one dashed-boundary construct
(expansion region, interruptible activity region, structured activity node). Look for a small
marker on the boundary's edge and for how the book names it in the p. 51 discussion. Use the
textbook's name, not a name you found elsewhere.
**Complete answer:** the name the textbook uses, plus the behavior — repeats per item —
plus what ends the repetition.

### Q7 — `[=0]` and `[>=1]` in the Fig. 2-13 Customer swimlane
**Tests:** guard conditions. **[UML]**
**Look at:** what these two guards hang off. Find the decision node immediately before them
and read its label — the guards are only meaningful as answers to that label's question.
**Complete answer:** say what a guard condition is generally, state what `=0` and `>=1` are
counting, and trace where each path goes. Then note the property that makes them a valid
decision node: they are mutually exclusive and together cover every case.

### Q8 — The unlabeled diamond just before "Exit store," Fig. 2-12
**Tests:** merge vs. decision — the discrimination from the notation table. **[UML]**
**Look at:** count the arrows. How many in, how many out? Are there guards on any of them?
An unlabeled diamond with multiple inputs and one output is doing the opposite job from the
labeled one earlier in the same swimlane.
**Complete answer:** name it, say what it does, and — this is the part that earns the point —
explain why it is **not** a synchronization: it does not wait for all incoming paths, it
simply passes along whichever path arrives. Contrast it with the diamond in Q7's answer and
with the bars in Q9's.

### Q9 — "Each of the vertical bars" in the Fig. 2-13 Customer swimlane
**Tests:** fork vs. join. **[UML]** Note the wording: **each**. There is more than one bar,
and they do different jobs. An answer that describes "the bar" generically will lose the point.
**Method:** for each bar, count arrows in and out.
- One in, several out → fork: flow **splits**; the outgoing paths run concurrently.
- Several in, one out → join: flow **waits** for every incoming path before continuing.

**Complete answer:** treat the bars separately. For each: which type, what it splits or
synchronizes, and — in business terms — what is happening simultaneously, or what is being
waited on before checkout can proceed.

### Q10 — One action needing further clarification
**Tests:** judgment about level of abstraction — SLO 2. There is no single correct answer;
there are well-defended and poorly-defended ones.
**How to choose:** scan Fig. 2-13's actions and find one where a developer would immediately
ask "but *how*?" Good candidates are actions that (a) bundle several distinct operations into
one rounded rectangle, (b) hide branching the diagram never shows, or (c) name a step whose
business rules are invisible — what gets written, validated, or rejected.
**Complete answer, three parts:**
1. Name the action exactly as the figure labels it.
2. Say what is ambiguous or compressed about it — be specific about the hidden complexity.
3. Say which fix you'd use and why: decompose it into additional action symbols, or leave the
   action alone and attach supplementary documentation. The prompt offers both; pick one and
   justify the pick.

**Strong move:** connect it to the Ch. 1 framing already in your notes — activity diagrams
model **process**; rules and data belong to other lenses (`MODELING-REFERENCE.md`, the seven
artifacts). An action that is really hiding a *rule* is a legitimate reason to say
"supplementary documentation" rather than "more boxes."

---

## Order of work

1. Resolve the due-date question with the professor. — `prompt-and-plan.md`
2. Open the textbook to pp. 51 and 53.
3. Fill the **Model** table in `prompt-and-plan.md` from both figures. Do not skip this;
   Q3, Q9, and Q10 are nearly free once the table exists.
4. Read the prose around both figures for the **[CHECK BOOK]** items (Q4, Q6).
5. Draft all ten answers in your own words.
6. Run the self-check in `prompt-and-plan.md`.
7. Save to `06 Submitted/` after uploading.

Bring the draft back here for critique before you submit.
