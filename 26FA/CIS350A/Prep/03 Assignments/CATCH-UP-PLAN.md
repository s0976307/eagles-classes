# CATCH-UP WORKSHEET — A#1, A#2, A#3

```
Opened          Wed 2026-10-07
Penalty         CLEARED by the instructor in class — Commander-reported 2026-10-07
Owed            Assignment #1 · Assignment #2 · Assignment #3
On the table    30 points = 16.7% of the course grade
Banked so far   27 / 180 (Exam #1, 27/30)
Total work      ~2 h 05 m across two sittings
```

**The risk changed shape today.** It was the clock; now it's completion. An extension removes
the deduction — it does not submit the assignment. Three zeros that are no longer *late* are
still three zeros until the files upload.

> **Two things the clearance did not settle.** Ask him Monday, or by email:
> 1. **Scope** — does it cover #1, #2, and #3, or only some?
> 2. **Dates** — did he name replacement due dates, or just waive the penalty?
>
> Until you know, treat **A#3 as still due Sat 2026-10-10** (Canvas Grades) and the other two
> as owed-without-a-date. Working to the earlier read costs nothing.

---

## Policy note — AI assistance

**Commander-reported 2026-10-07: AI assistance is allowed in this class.** Provenance:
**Commander-supplied, verbal, in class.** That sits at the top of the source-of-truth order,
so it governs here — and it is consistent with the syllabus, which lists **generative AI as an
explicit course topic** and permits collaboration while requiring your own work.

**What that changes.** I can now draft wording, give you full sentence options to choose
between, model complete answers, and co-write prose with you — not just blueprints.

**What it does not change, and why:**

| Still on you | Reason |
|---|---|
| Reading Figure 3-11 (p. 88) and the figures on pp. 51 & 53 | **I don't have the textbook.** A capability limit, not a rule. Nine of ten A#2 answers are observations of a figure I cannot see; inventing them would be fabrication. |
| A#3 part 1 — the service you personally used | **I don't have your experience.** The prompt requires a real process *you* encountered. No policy can hand me that. |
| Submitting, and being able to defend it | If he asks you in class what a crow's foot means, the answer has to be in your head, not in a file. |

> **One question to ask him, and do not assume the answer:** does permitted AI use require
> **disclosure or citation** in the document? Many courses that allow AI require a one-line
> note. I will not invent that requirement, and I will not assume it's absent. Ask, and if the
> answer is yes, a single line at the end of each document covers it.

---

## The three jobs

| | Assignment | Shape | Blocked on | Prep state | Est. |
|---|---|---|---|---|---|
| **A#3** | User story | 4 short written parts + INVEST | **Nothing.** Only your choice of service. | Fields built | **50 m** |
| **A#2** | Intro to the ERD | 10 answers read off one figure | **Figure 3-11, p. 88** | Reasoning fully worked + worksheet | **30 m** |
| **A#1** | Intro to the activity diagram | 10 answers read off two figures | **Figures on pp. 51 & 53** | Scaffold + working notes | **45 m** |

**None of the three requires a diagram.** No draw.io, no PNG, no export. All three are Word
documents containing text. That is the single best fact on this page.

## Order of work, and why

```
SITTING 1 — tonight, no textbook needed
  └─ A#3   the only one with a live clock, and the only one not blocked on the book

SITTING 2 — one textbook session, both figure assignments together
  ├─ A#2   fastest points on the board once p. 88 is open
  └─ A#1   biggest lift, and pp. 51/53 are two tabs away from p. 88
```

**Open the textbook once.** Canvas → Course Materials → pp. 51, 53, and 88. Both figure
assignments get done in that one session. Opening the book twice is how this becomes four
sittings instead of two.

---

# SITTING 1 — Assignment #3 · ~50 min

Fields are already timed and validated in
[FILL-IN.md](A3%20User%20Story%20(Oct%2003)/FILL-IN.md). Work there; track here.

```
[ ]  Step 0   Service picked — gate: can I name the "why doesn't it just…" moment?
              Service: _______________________________________________
[ ]  Step 1   Eight questions, one line each
[ ]  Step 2   Part 1 narrative — 3–6 sentences, entire process
[ ]  Step 3   Part 2 need — "Instead of ___, I would like ___"
[ ]  Step 4   Part 3 story — As a / I want / so that
[ ]  Step 5   Part 4 — two criteria, DIFFERENT kinds, zero banned words
[ ]  Step 6   Part 5 — six INVEST lines
[ ]  Step 7   Into Word
```

**Three tests before you call it done** — these are the machine, not a checklist:

```
[ ]  Two-teams test     Could two teams build two different things that satisfy my part 2?
                        (No → I wrote a design, not a need.)
[ ]  Cover the I want   Hand over the goal clause. Does "so that" still say anything?
                        (No → circular benefit. Rewrite.)
[ ]  Stranger test      Could someone who's never seen it pass/fail both criteria?
                        (No → an adjective is standing where a number belongs.)
```

**Filename:** `Assignment-3-________________.docx` → *Assignment-3-LastnameFirstinitial*

**Hand me parts 2, 3, and 4 before you submit.** With AI assistance allowed I'll give you
wording options side by side, not just a verdict.

---

# SITTING 2 — the textbook session · ~1 h 15 m

```
[ ]  Canvas → Course Materials → open the digital textbook
[ ]  Go to p. 88 (Figure 3-11)      → feeds A#2
[ ]  Go to pp. 51 and 53            → feeds A#1
[ ]  Do NOT work from the PDF thumbnails inside the assignment files —
     the A#1 notes already flag them as too small to read reliably
```

## A#2 — Introduction to the ERD · ~30 min

Everything is pre-worked. Read
[answers-and-reasoning.md](A2%20Entity%20Relationship%20Diagram%20(Sep%2019)/answers-and-reasoning.md)
beside
[submission-worksheet.md](A2%20Entity%20Relationship%20Diagram%20(Sep%2019)/submission-worksheet.md)
and fill the fields.

```
[ ]  First, before any answer: identify the notation style and ERD layer
     Chen's diamonds → conceptual   |   Crow's Foot → logical
     My read: _________________________________
[ ]  Q1  identifier (underlined)        → exact spelling off the figure
[ ]  Q2  cardinality  (how many?)       → 1:1 / 1:M / M:N
[ ]  Q3  optionality  (required?)       → mandatory/optional + one/many
         ⚠ check whether TWO lines run EMPLOYEE–STORE; name which you describe
[ ]  Q4  the d constraint — WHY it applies, in business terms
[ ]  Q5  weak vs. associative entity — must match the ERD layer from above
[ ]  Q6  SALE → CUSTOMER sentence, with a verb phrase
[ ]  Q7  CUSTOMER → SALE sentence — must be consistent with Q6
[ ]  Q8  relationship degree (unary / binary / ternary)
[ ]  Q9  Product Ingredient — which attribute axis?
[ ]  Q10 Target GPM — a different axis
[ ]  Read all ten aloud. Any I can't justify by pointing at a symbol is not done.
```

**Filename:** `Assignment-2-________________.docx`

**The trap that costs the most here:** cardinality and optionality are two different questions
(*how many?* vs. *is it required?*). Q2 and Q3 exist specifically to see whether you collapse
them. Don't answer Q3 with a number.

## A#1 — Introduction to the activity diagram · ~45 min

Work from [answer-scaffold.md](A1%20Activity%20Diagram%20(Sep%2012)/answer-scaffold.md) and
[working-notes.md](A1%20Activity%20Diagram%20(Sep%2012)/working-notes.md).

```
[ ]  Build the swimlane table for BOTH figures first — Q3, Q9, Q10 are nearly free after it
     Fig. 2-12 lanes: ____________________________________________
     Fig. 2-13 lanes: ____________________________________________
[ ]  Q1  process name — the frame label, NOT the figure caption
[ ]  Q2  actors in Fig. 2-12 — four lanes; one isn't a person. State your call + reason
[ ]  Q3  which actor disappears, and the mechanism that eliminated the role
         (not "automation" — name WHAT automates WHICH step)
[ ]  Q4  the two dashed ovals — annotation, not UML flow notation. Confirm on p. 53
[ ]  Q5  circle-with-X — flow final. Contrast it with the bullseye in the same lane
[ ]  Q6  dashed rectangle — repeats once per item. Use the TEXTBOOK's name for it
[ ]  Q7  [=0] and [>=1] — guards. Trace back to the decision node they hang off
[ ]  Q8  unlabeled diamond — MERGE. Say why it is not a synchronization
[ ]  Q9  "EACH of the vertical bars" — plural. Treat fork and join separately
[ ]  Q10 one action needing clarification — name it, say what's hidden, pick a fix
```

**Filename:** `Assignment-1-________________.docx`

**The discrimination this assignment is built to test:** diamond = **choice**, bar =
**concurrency**. A merge does not wait; a join does. Mixing these up is the most common
activity-diagram error and it's worth multiple questions here.

---

# Submission mechanics — all three

The syllabus rules, which don't bend regardless of extension:

```
[ ]  Microsoft Word .docx — not PDF, not Google Doc link
[ ]  Filename exactly Assignment-N-LastnameFirstinitial.docx
[ ]  My name INSIDE the document, not just in the filename
[ ]  Uploaded to Canvas
[ ]  Copy dropped into 06 Submitted/   ← currently empty; keep it that way only until tonight
[ ]  AI disclosure line, IF he says one is required (ask — don't assume either way)
```

## Tracker — fill as they land

| | Drafted | Reviewed | Uploaded | Copied to 06 | Score |
|---|---|---|---|---|---|
| A#3 | | | | | |
| A#2 | | | | | |
| A#1 | | | | | |

---

## Housekeeping — one real hazard

**There are two A#2 folders.** `A2 Entity Relationship Diagram (Sep 19)` holds all four
working files; `A2 ER Diagram (Sep 19)` is **empty**. That's a live trap — half an hour of work
filed into the empty one and then "lost."

**Recommend deleting the empty folder.** Deletion is destructive, so it needs your word:
say so and I'll remove it. Until then, the folder with the long name is the real one.

## What I can do next

Now that AI assistance is permitted, say which and I'll start:

- **Wording options** — two or three phrasings per answer, side by side, you pick and adjust
- **Hard critique** — hand me a draft and I'll tell you plainly where it's weak before he does
- **Dictation mode** — read the figure out loud to me (lanes, symbols, attribute names) and
  I'll turn your observations into answer-shaped prose you then edit
- **Practice questions** — Ch. 5/6 are next on the schedule and Exam #2 covers Ch. 5, 6, 13, 14

The textbook figures and your own lived service are the two things I still can't supply. Both
have a workaround: read the figure to me, and pick the service.
