# A1 — working notes: reasoning behind each answer

**What this file is:** the reasoning for all ten questions — why each answer is what it is.
It is **working notes, not submission prose.** Nothing here is formatted to paste into the
Word document. Compose your own sentences from this; that is what makes the answers
defensible if the professor asks a follow-up.

**Standing caveat on sourcing.** These notes were worked out from the reduced figure
reproductions embedded in `Assignment_1.pdf`, **not** from textbook pp. 51/53. Action and
swimlane labels are legible in that reproduction; **arrow counts and directions often are
not.** Confidence is marked per question. Where a note says **VERIFY**, open the textbook
before you commit the answer to the document.

Companion files: [prompt-and-plan.md](prompt-and-plan.md) (intake, deadline status,
ambiguities) · [answer-scaffold.md](answer-scaffold.md) (document skeleton, notation table).

---

## Notation reference — the discrimination this whole assignment is built on

| Symbol | Name | What it asserts about flow |
|---|---|---|
| Solid filled circle | Initial node | Where the activity begins |
| Filled circle in a ring (bullseye) | Activity final node | The **whole activity** stops |
| Circle with an X | Flow final node | **This one path** stops; other paths keep running |
| Rounded rectangle | Action | One step of work |
| Diamond, 1 in / n out, `[guards]` | Decision node | Chooses **one** path; guards are mutually exclusive |
| Diamond, n in / 1 out, unlabeled | Merge node | Alternate paths rejoin; **no waiting** |
| Thick bar, 1 in / n out | Fork | Flow splits into genuinely **concurrent** paths |
| Thick bar, n in / 1 out | Join | Flow **waits** for every incoming path |
| Swimlane (partition) | Partition | Who is responsible for the actions inside |
| `[text]` on an arrow | Guard condition | Path taken only if the condition holds |

**Diamond = choice. Bar = concurrency.** Decision/merge is about picking one of several
paths. Fork/join is about several paths running at once. Confusing the two is the most
common activity-diagram error, and Q8 vs. Q9 exists to test exactly that line.

---

## Q1 — Process name · HIGH CONFIDENCE

The rotated label on the outer frame spanning all swimlanes, in both figures:
**Purchase Groceries**.

The distinction being tested: the swimlane frame carries the **process** name; the caption
underneath ("Current State Activity Diagram") is the **figure's** name. Two different things.
The process is identical in both figures — that is the entire reason they are shown as a pair.

## Q2 — Actors in Fig. 2-12 · HIGH CONFIDENCE

Four swimlanes: **Customer · Cashier · POS System · Bagger**.

The ambiguity is worth one sentence in the answer. Three are human roles; **POS System** is
software. In UML a swimlane is a *partition* — it answers "who is responsible for the actions
inside," and a system can hold that responsibility. Textbooks split on whether to call that an
"actor."

**Move:** state your definition once, list all four, note which is non-human. Cheap sentence,
protects the point either way.

## Q3 — The missing actor · HIGH CONFIDENCE on the *who*; strong inference on the *why*

**Bagger.** Fig. 2-13 has three lanes: Customer, Cashier, POS System.

The mechanism is what the question actually wants. Compare item handling across the figures:

| | Fig. 2-12 Current | Fig. 2-13 Future |
|---|---|---|
| Item handling | `Scan item` (Cashier) → `Add item to sale` (POS) → `Bag items` (Bagger) | `Collect, scan, and bag item` (Customer) → `Add item to sale` (POS) |
| Roles involved | three | one |
| When it happens | at checkout, **after** shopping | **during** shopping |

The work did not disappear — it **migrated to the Customer**, enabled by `Start mobile app` /
`Start sale`, which have no counterpart in the current state. The customer scans and bags each
item on pickup. No separate bagging step remains to staff.

Second-order change worth mentioning: the Cashier does not vanish, the **role changes** —
`Receive payment` becomes `Verify items`. Labor shifted from handling goods to auditing a
self-service process. Noting this shows you compared the diagrams rather than diffing two lists.

**Trap:** do not write "because of automation." Name the app, name the step, name who absorbed
the work.

## Q4 — The two dashed ovals · REASONING SOLID · **VERIFY against p. 53 prose**

Structural giveaway first: **the ovals cross swimlane boundaries.** No UML flow element does
that. An action, a decision, a fork — each lives in exactly one partition, because the
partition assigns responsibility. Something crossing all three lanes is not participating in
the flow at all.

They are **annotation** — the authors drawing on top of the finished diagram to highlight
regions for the reader. What they highlight is the two clusters where the future state differs
from the current state:

- **Left oval:** `Start mobile app` / `Start sale` / `Collect, scan, and bag item` /
  `Add item to sale` — the new self-service scanning; the change that eliminated the Bagger.
- **Right oval:** `Make payment` / `Verify items` / `Process payment` — the reworked checkout,
  where the Cashier's job became verification.

So: not notation, a callout; and the callouts mark the deltas from Fig. 2-12. This is why Q3
and Q4 sit adjacent in the assignment — Q4 is the author pointing at Q3's answer.

**VERIFY:** confirm the caption and surrounding prose say this. Strong read, but it is a read,
not the book's words.

## Q5 — Circle with an X · HIGH CONFIDENCE · standard UML

**Flow final node.** Trace what enters it: the `[No]` branch off `Access to payment?` — a
customer with no means of payment.

The contrast that earns the point:

| Symbol | Ends | Effect |
|---|---|---|
| ⊗ flow final | this **one path** | the rest of the activity keeps running |
| ◉ activity final | the **entire activity** | every path everywhere stops |

Why the authors chose the weaker one: a customer turned away at the door is not the end of
"Purchase Groceries" as a business process — the store keeps operating, other flows continue.
Only the completed-purchase path at `Exit store` legitimately ends the activity. Using ◉ on the
`[No]` branch would assert that one customer's lack of a credit card shuts down the store.

Business meaning: that customer leaves without entering the shopping process.

## Q6 — The dashed rectangle · BEHAVIOR CONFIDENT · **VERIFY the name in the book**

Three observations, in order:

1. It encloses `Scan item` (Cashier) and `Add item to sale` (POS System) — it spans two lanes,
   so it groups by **behavior**, not by responsibility.
2. There is a loop-back arrow inside it.
3. There are small segmented boxes on the boundary edge.

That combination is UML's **expansion region**: a region whose contents execute **once per
element of an input collection**. The collection is the items in the cart; the region runs
scan-then-add for item 1, item 2, item 3… and exits when the collection is exhausted. The
segmented boxes on the border are the expansion nodes — collection in, collection out.

Why it matters conceptually: without it you would have to draw one scan/add pair per item,
impossible for an unknown item count. The region is how an activity diagram says "repeat per
item" without a loop counter.

**VERIFY:** UML has several dashed-boundary constructs (expansion region, interruptible
activity region, structured activity node) and textbooks sometimes simplify. Use whatever
p. 51's prose calls it. **If the book uses a different name, the book wins** — and correct
this file.

## Q7 — `[=0]` and `[>=1]` · HIGH CONFIDENCE · standard UML

**Guard conditions** — boolean expressions on the outgoing edges of a decision node,
controlling which single path the flow takes.

Read against the decision they hang off, `# of items to purchase`:

- `[>=1]` — at least one item → continue into checkout (`Make payment`).
- `[=0]` — nothing to buy → that arrow runs along the top, past the entire payment sequence,
  to the merge before `Exit store`.

The real content of the answer is **why this is a well-formed decision**: the guards are
**mutually exclusive** (a count cannot be both) and **exhaustive** (a count cannot be anything
else — it is ≥0 by definition). Guards that overlap make the decision ambiguous; guards that
leave a gap deadlock the flow. These do neither.

Business case being modeled: somebody who walks in, browses, and buys nothing. The diagram has
to route them out without forcing them through payment.

## Q8 — The unlabeled diamond · HIGH CONFIDENCE · standard UML

**Merge node.** Same shape as a decision, opposite job; the notation tells you which:

| | arrows | guards | behavior |
|---|---|---|---|
| Decision | 1 in, n out | yes | picks **one** outgoing path |
| Merge | n in, 1 out | none | passes along **whichever** path arrived |

Multiple inputs, one output, no labels → merge. It rejoins the two alternate routes created
back at `# of items to purchase`: the `[=0]` bypass and the path that went through payment.
Both end at `Exit store`, so they must converge somewhere.

**The sentence that earns the point:** a merge does **not** wait. It is not synchronization.
Exactly one of those two paths was ever taken — they are alternatives, not concurrency — so
there is nothing to wait for. That is what distinguishes it from the bars in Q9, and it is the
discrimination this assignment is built around.

## Q9 — The vertical bars · CONCEPT CONFIDENT · **VERIFY arrow directions yourself**

Note the wording: "the purpose of **each**." Plural, and they are expected to differ. A generic
"these are forks" answer loses the point.

Method, works on any activity diagram:

- **1 in → n out = fork.** Flow splits; outgoing paths run **concurrently**. Nothing is decided.
- **n in → 1 out = join.** Flow **waits** until every incoming path arrives, then continues as one.

My read of Fig. 2-13's Customer lane — **this is where the reduced figure defeats me, check p. 53:**

- **Bar before `Collect, scan, and bag item`** — almost certainly a **join**. `Start mobile app`
  (Customer) and `Start sale` (POS System) happen in parallel, and scanning cannot begin until
  **both** are done: the app must be running and the sale record must be open. That is a
  synchronization requirement, and a join is how you state it.
- **Bar before `Make payment`** — a **join** on the other side of the item loop: every item must
  be scanned and added before a total exists to pay.

Whatever you find, for each bar state (a) fork or join, (b) what splits or what is being waited
on, (c) the business reason. **The business reason is the part most students skip.**

## Q10 — Action needing clarification · JUDGMENT · no single right answer

Two defensible picks. They lead to **different** fixes, which is why the prompt offers both.

**`Collect, scan, and bag item`** → argues for **additional action symbols.**
Three verbs in one rounded rectangle, each a distinct operation with its own failure modes: an
item that will not scan, produce needing weighing, an age-restricted item requiring staff
approval, a customer putting something back after scanning it. The action also silently
contains its own iteration and its own exception branches, none of which appear. Decomposing it
into separate actions makes the exceptions drawable.

**`Verify items`** → argues for **supplementary documentation.**
A single box with no outgoing branch for failure. Unanswered: what triggers verification —
every customer or a sample? What percentage of items? What happens when the physical cart does
not match the sale record? Who resolves it?

Those are **business rules** — and here is the leverage: per
[MODELING-REFERENCE.md](../../02%20Readings%20and%20Notes/MODELING-REFERENCE.md), an activity
diagram models **process**; rules belong to structured logic, data to the ERD. Adding more boxes
will not fix an action that is hiding a **rule**, which is precisely why documentation is the
right instrument here.

That move — naming **which lens** the missing information belongs to, and deriving the fix from
that — is what the question is fishing for. Pick one, name it exactly as the figure labels it,
say what is compressed, justify the fix.

---

## Confidence summary

| Questions | Status |
|---|---|
| Q1, Q2, Q3, Q5, Q7, Q8 | Solid — standard UML plus legible labels |
| Q4, Q6 | Reasoning sound; **confirm names/intent against pp. 51–53 prose** |
| Q9 | Concept certain; **per-bar reading unverified — count the arrows** |
| Q10 | Judgment call; both candidates defensible |

## Before you write

1. Resolve the due-date question with Prof. Inomoto — see the status block in
   [prompt-and-plan.md](prompt-and-plan.md). Still blocking.
2. Open pp. 51 and 53. Clear the three **VERIFY** items above.
3. Draft in your own words, then run the self-check in `prompt-and-plan.md`.
4. Bring the draft back for critique before submitting.
