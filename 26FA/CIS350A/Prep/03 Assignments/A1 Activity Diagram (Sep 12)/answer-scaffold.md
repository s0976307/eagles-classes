# A1 — fillable worksheet (late turn-in)

**Regenerated 2026-10-05 for late submission.** Fill every `____` field. When all fields are
filled and the self-check passes, transfer to Word and submit.

Reasoning behind every answer: [working-notes.md](working-notes.md) · Intake and deadline
status: [prompt-and-plan.md](prompt-and-plan.md)

> **This worksheet is structure, not answers.** The fields are yours to write. Prompts under
> each field say what a complete answer must contain — not what to say.

---

## FIELD 0 — Extension request (do this first)

> **Superseded 2026-10-05 → [RECOVERY-PLAN.md](../RECOVERY-PLAN.md) FIELD A.**
> A1, A2 and A3 are all outstanding. Ask for all three in **one** conversation, not three
> emails. The combined draft is in the recovery plan. A1 is **not** the first thing to work
> on — see FIELD B there for the order.

23 days late. Nominal penalty exceeds 100%. Syllabus: *"Extensions granted upon request."*
No extension means this work scores zero regardless of quality.

```
To: inomoto@niagara.edu
Subject: CIS 350A — Assignment #1 late submission

Professor Inomoto,

Reason for delay: ______________________________________________

Work completed since: __________________________________________
  (you studied Mon 2026-09-28, 18:22 — Ch. 1–4 review incl. swimlanes,
   parallel activity, decision vs. merge)

Requested submission date: _____________________________________

<your name>
```

- [ ] Email sent — date: `________`
- [ ] Response received — outcome: `________________________`

**Do not skip to the questions.** Reply SLA is one business day.

---

## FIELD 1 — Document header

```
Filename:  Assignment-1-________________.docx
           (Lastname + first initial, e.g. Assignment-1-SmithJ)

Name:      ____________________________
Course:    CIS 350A — Systems Analysis & Design — Fall 2026
Assignment: #1 — Introduction to the Activity Diagram
Date:      ____________
```

**Working definition of "actor"** (one line — Q2 turns on it, declare it up front):

> ______________________________________________________________

---

## FIELD 2 — Source verification

Three answers cannot be finalized from the reduced figures in `Assignment_1.pdf`. Open the
textbook (Canvas → Course Materials, pp. 51 and 53) and clear these:

| # | What to check | Found | Confirmed? |
|---|---|---|---|
| Q4 | What the p. 53 prose/caption says the dashed ovals are | `____________` | ☐ |
| Q6 | The textbook's **name** for the dashed rectangle on p. 51 | `____________` | ☐ |
| Q9 | Arrow count + direction on **each** vertical bar, Fig. 2-13 Customer lane | `____________` | ☐ |

If the book contradicts [working-notes.md](working-notes.md), **the book wins.**

---

## FIELD 3 — Model table

Fill from both figures before writing prose. Q3, Q9 and Q10 are nearly free once this exists.

| | Fig. 2-12 Current State | Fig. 2-13 Future State |
|---|---|---|
| Swimlanes | `____________` | `____________` |
| Start node | `____________` | `____________` |
| Actions, in order | `____________` | `____________` |
| Decisions + guards | `____________` | `____________` |
| Forks / joins | `____________` | `____________` |
| Regions | `____________` | `____________` |
| End node(s) | `____________` | `____________` |

**The single diff that falls out of this table is all of Q3 and most of Q4.**

---

# The ten answers

### Q1 — Overall name of the process

> ______________________________________________________________

☐ Named the **process** (outer frame label), not the figure caption
☐ Noted it is the same process in both figures

---

### Q2 — Actors in Fig. 2-12

> ______________________________________________________________
> ______________________________________________________________

☐ All four swimlanes listed
☐ Identified which one is **not** human
☐ Applied the definition from FIELD 1 — said whether it counts and why

*Your Ch. 1–4 notes: "swimlane = responsibility boundary… organize activities by responsible
participant and show handoffs." That phrasing is defensible here.*

---

### Q3 — Which current-state actor is missing from the future state, and why

> ______________________________________________________________
> ______________________________________________________________
> ______________________________________________________________

☐ Named the missing actor
☐ Named **what** absorbed the work and **who** now does it
☐ Traced it to a specific action label that exists in 2-13 but not 2-12
☐ **Did not write "because of automation"** — named the mechanism
☐ Bonus: noted the Cashier's role *changed* rather than vanished

---

### Q4 — The two dashed ovals crossing all swimlanes (Fig. 2-13)

> ______________________________________________________________
> ______________________________________________________________

☐ Used the structural argument: they **cross swimlanes**, so they are not flow notation
☐ Said what they are (annotation / callout)
☐ Said what each of the two highlights
☐ FIELD 2 Q4 confirmed against p. 53

---

### Q5 — The circle with an "X" (Fig. 2-12, Customer lane)

> ______________________________________________________________
> ______________________________________________________________

☐ Named the symbol
☐ Traced the incoming guard back to its decision
☐ **Contrasted it explicitly** with the bullseye in the same lane
☐ Said what it means in business terms

---

### Q6 — The dashed rectangle around "Scan item" / "Add item to sale"

> ______________________________________________________________
> ______________________________________________________________

☐ Used the **textbook's** name (FIELD 2 Q6)
☐ Stated the behavior: executes once per item
☐ Said what ends the repetition
☐ Noted it spans two lanes — grouping by behavior, not responsibility

---

### Q7 — The `[=0]` and `[>=1]` specifications

> ______________________________________________________________
> ______________________________________________________________

☐ Named them as guard conditions on a decision node
☐ Named the decision they hang off
☐ Traced where **each** path goes
☐ Said why they are well-formed: **mutually exclusive and exhaustive**

---

### Q8 — The unlabeled diamond before "Exit store"

> ______________________________________________________________
> ______________________________________________________________

☐ Counted arrows (n in / 1 out) and noted the absence of guards
☐ Named it
☐ Said **which two paths** it rejoins
☐ **Stated it does not wait** — not a synchronization

*Your Ch. 1–4 notes already carry this: "Decision — chooses between alternative paths /
Merge — brings alternative paths back together."*

---

### Q9 — The purpose of **each** vertical bar (Fig. 2-13, Customer lane)

Question says *each*. Answer them separately.

**Bar 1** — location: `________________________`
> ______________________________________________________________

**Bar 2** — location: `________________________`
> ______________________________________________________________

☐ FIELD 2 Q9 confirmed — arrows counted on p. 53
☐ Each bar classified fork **or** join
☐ For each: what splits, or what is being waited on
☐ For each: the **business reason** ← most-skipped point

*Your notes: "Parallel activities allow multiple activities to proceed concurrently." True of a
fork. A join is the other half — it makes concurrent paths **wait and reconverge.**
Diamond = choice. Bar = concurrency.*

---

### Q10 — One Fig. 2-13 action needing further clarification

**Action chosen** (exact label from figure): `________________________`

**Fix chosen** (circle one): additional action symbols · supplementary documentation

> ______________________________________________________________
> ______________________________________________________________
> ______________________________________________________________

☐ Named the action exactly as labeled
☐ Said specifically what is compressed or hidden
☐ Justified **which** fix and why that one
☐ Strong move: named which modeling lens the missing information belongs to — activity
  diagrams model *process*; rules → structured logic, data → ERD

---

## Self-check before submitting

- [ ] FIELD 0 resolved — extension requested, outcome known
- [ ] All three FIELD 2 verifications cleared against the textbook
- [ ] All ten answered, numbered to match the prompt
- [ ] Q3 and Q10 give a **reason**, not just an identification
- [ ] Q9 treats the bars **separately**
- [ ] Every notation claim traceable to the textbook or to UML — and I can say which
- [ ] I can explain every answer out loud without notes
- [ ] Name in document; filename matches the required pattern exactly
- [ ] Copy saved to `06 Submitted/`
