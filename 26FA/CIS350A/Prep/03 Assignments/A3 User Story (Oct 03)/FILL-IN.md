# A3 — FILL-IN SHEET

```
Due      Sat 2026-10-10, 23:59   (Canvas Grades)
Now      Thu 2026-10-08
Status   NOT LATE. Two days of runway. Full 10 / 10 available.
```

> **Date corrected 2026-10-08.** This header previously read *"Due Sat 2026-10-03 / Now Mon
> 2026-10-05 / Late 2 days / ceiling 8.0 out of 10"* and told you to ship at 8.0 rather than
> polish. **That was wrong and it was costing you points.** `01 Syllabus and Course
> Info/COURSE-INFO.md` is the date authority and gives A#3 as **Sat Oct 10** from Canvas
> Grades. No penalty is running.
>
> **The folder name `A3 User Story (Oct 03)` is also wrong**, and so are the other
> assignment folder names: each encodes the week the work was assigned, not its Canvas due
> date, and every one of them reads about a week early. Trust `COURSE-INFO.md`, never a
> folder name.
>
> **What this changes:** the advice below is sized for a 50 minute panic sitting against a
> running clock. There is no clock. Use the time. Run the three tests in
> `CATCH-UP-PLAN.md` properly and bring parts 2, 3 and 4 back for critique before you
> submit, which the old header told you to skip.

Everything below is still sound as a working sheet. Only the urgency framing was wrong.

**Do this first, before the worksheet:** [email-draft-inomoto.md](email-draft-inomoto.md).
On Mon 2026-09-28 at 19:20 the professor told you in class that you owe him a couple of
assignments, and you told him you'd send an email. The syllabus grants extensions on request.
That email is worth more points than anything on this sheet.

**Provenance.** **[PROMPT]** = assignment text · **[DECK]** = Ch. 4 slides via
`02 Readings and Notes/CH04-NOTES.md` · **[LECTURE]** = Prof. Inomoto's own words, class of
Mon 2026-09-28, from your wearable recording · **[CHECK BOOK]** = Ch. 4.2.1.1, which I have
not read. Fill the fields yourself — I don't have your experience, and part 1 requires it.

---

## STEP 0 — Pick the service · 2 min

Jog your memory. The prompt's own menu **[PROMPT]**: online purchase · travel reservation ·
paying a bill · library resource lookup · class registration. It also says the process
**does not have to be online or even computer-based** — a counter, a phone tree, or a paper
form all qualify.

Services you plausibly touched this semester, as prompts only — pick one **you actually used**:
pharmacy or medical refill · VA appointment scheduling · campus parking pass · Canvas itself ·
bookstore order · rugby club registration or dues · equipment or kit order · gym or facility
booking · VFW membership renewal · food delivery · bank or bill pay · DMV · phone carrier.

```
S1  Service I used:            ________________________________________________
S2  Roughly when I used it:    ________________________________________________
S3  The moment I thought
    "why doesn't it just…":    ________________________________________________
```

**GATE.** If **S3** is blank, go back and change the service. S3 *becomes* part 2. A service
with no remembered friction will fight you for the next 45 minutes.

---

## STEP 1 — Eight questions, one line each · 8 min

Don't write prose yet. One line per field. Part 1 assembles itself out of these.

```
Who      (roles that touch it, including mine): _______________________________
Why      (what it exists to do for me):         _______________________________
What     (the capability I came for):           _______________________________
Data     (what I supply / what comes back):     _______________________________
Process  (trigger → steps → outcome):           _______________________________
Rules    (deadlines, limits, eligibility, fees):_______________________________
Interface(app / web / phone / counter / paper): _______________________________
How      (automated vs. done by a human):       _______________________________
```

---

## STEP 2 — Part 1, the narrative · 10 min

Five slots. Fill the slots, then write them into 3–6 sentences, **present tense, first person.**

```
N1  What starts it (the trigger):       ______________________________________
N2  What I do first:                    ______________________________________
N3  What I hand over (info/payment):    ______________________________________
N4  What happens next / what I wait on: ______________________________________
N5  How it ends:                        ______________________________________
```

**Part 1 — final text:**

```
________________________________________________________________________________
________________________________________________________________________________
________________________________________________________________________________
________________________________________________________________________________
```

**Validate before moving on:**

- [ ] Covers **the entire process** **[PROMPT]** — trigger through outcome, not just the bad part
- [ ] The friction appears as a **stated fact**, not a complaint (save that for part 2)
- [ ] A stranger could tell what the service is and how it ended
- [ ] 3–6 sentences. The professor's own part 1 is **one** sentence **[PROMPT]** — that's the floor

---

## STEP 3 — Part 2, the future-state need · 5 min

One stem. Fill both halves.

```
Instead of ________________________________________________ [current-state pain],

I would like _______________________________________________ [capability I want].
```

**Validate:**

- [ ] **Two-teams test** — could two teams build two *different* things that both satisfy this?
      Yes → it's a need. Only one thing fits → you wrote a **design**. Rewrite.
- [ ] No screen, button, app, or vendor named. Features are the system's **whats**; designs are
      the **hows** **[DECK §4.1]** — part 2 lives on the *what* side
- [ ] Exactly **one** desire. Two desires = two stories = fails **S** in INVEST
- [ ] Benefit is **mine**, not the organization's **[PROMPT]** — "from your perspective as the user"

---

## STEP 4 — Part 3, the user story · 7 min

Three slots **[DECK §4.3]**: **Who** → role/persona · **What** → goal/need/desire ·
**Why** → justification.

```
R   As a ______________________________________________________________________
    [your relationship to the service: customer / patient / member / student /
     account holder. NOT "a user" — the deck says "retail store customer," the
     professor's example says "online banking service customer"]

G   I want to be able to ________________________________________________________
    [a capability, verb phrase, implementation left open]

J   so that ______________________________________________________________________
    [the CONSEQUENCE of having it — in time, money, accuracy, risk, or trips]
```

**The one test that catches the common failure.** Cover slot **G** with your hand and read
**J** alone. Does it still say something? If it evaporates, J is restating G — rewrite it.

- ✗ "I want a notification, so that I am notified." — circular
- ✓ "I want to mail checks without physically writing them out, so that I can **save time and
  postage**." **[PROMPT]** — different currency than the goal

**[LECTURE 2026-09-28]** The professor spent real time on exactly this clause. His framing: it
isn't enough that a solution "may be perfectly fine" or "more convenient" —

> "you need to structure that … so that it's explicit, that's clear … this makes it more
> convenient, **therefore** you're gonna save some time and they'll be able to devote that
> extra time to other tasks."

"Convenient" is where a weak justification stops. **Therefore + what the saved time buys** is
where his goes. Write the *therefore*.

**Part 3 — assembled, one sentence:**

```
As a ____________________, I want ____________________, so that ____________________.
```

- [ ] Literally in the `As a / I want / so that` format **[PROMPT]** — don't paraphrase the format
- [ ] One sentence
- [ ] Converts cleanly to the "shall" form **[DECK §4.3]**: `A <role> shall be able to <goal>.`
      If it won't convert, the goal isn't a capability yet

---

## STEP 5 — Part 4, two acceptance criteria · 8 min

**Exactly two** **[PROMPT]**, labeled a. and b., matching the example's layout.

**[LECTURE 2026-09-28]**, the professor's own definition, almost verbatim:

> "standards and **metrics or measures** that supplement the user story, so that you can say —
> if your solution meets these criteria, then it will be acceptable to the requesting user …
> **constraints that limit acceptable solutions** … they provide a foundation for user
> acceptance tests."

He also said how detailed they need to be **varies** with how detailed the designer must be —
so for a 10-point assignment, two sharp criteria beat four hedged ones.

**Make them different kinds** **[DECK §4.4]**. Pick two rows:

| Kind | Covers | Shape to fill |
|---|---|---|
| Functional — **variation** | a complexity or specific detail | "The service should allow / support \<detail>, up to \<limit>." |
| Functional — **exception** | an error condition | "If \<thing fails>, the service should \<state what happens>." |
| **Nonfunctional** | an operational characteristic | "The service should \<do it> within \<number> / on \<platforms>." |

```
4a  Kind (variation / exception / nonfunctional): ______________________
    Text: _____________________________________________________________
    ___________________________________________________________________

4b  Kind (must DIFFER from 4a):                  ______________________
    Text: _____________________________________________________________
    ___________________________________________________________________
```

**Banned-word sweep** — the prompt names "user friendly" as too vague **[PROMPT]**. Same
problem: *easy · quick · fast · intuitive · seamless · reliable · better · simple · modern.*
Each one hides the pass/fail line. Replace it with **a number, a list, or a condition.**

**Gherkin stress test** **[DECK §4.8]** — scratch work, not part of the deliverable. If a
criterion won't take this shape, it isn't testable yet:

```
4a   Given _________________  When _________________  Then _________________
4b   Given _________________  When _________________  Then _________________
```

- [ ] Each criterion adds a detail the one-sentence story **could not carry**
- [ ] Neither one restates part 3
- [ ] A tester who has never seen the system would know how to pass/fail both
- [ ] No screen, button, or layout described — that's Assignment #4
- [ ] *Optional, cheap, shows you read past the definition:* tag one `(Must have)` and one
      `(Should have)` — **each criterion can carry its own MoSCoW priority** **[DECK §4.5]**
- [ ] **[CHECK BOOK]** Skim Ch. 4.2.1.1's examples and match the book's register

---

## STEP 6 — Part 5, INVEST · 5 min

The prompt's closing paragraph says to evaluate against INVEST **[PROMPT]** but the worked
example stops at part 4. **Include it as a labeled part 5** — near-zero cost if unwanted, a
visibly unaddressed instruction if omitted.

One line each. **Be willing to fail one** — an honest failure with a named cause scores better
than six lines of "yes," and if the audit bites, **fix the story, not the audit.**

```
Independent — ___________________________________________________________________
Negotiable  — ___________________________________________________________________
Valuable    — ___________________________________________________________________
Estimable   — ___________________________________________________________________
Small       — ___________________________________________________________________
Testable    — ___________________________________________________________________
```

Prompts, if a line stalls **[DECK §4.6]**:

- **I** — buildable without first building something you haven't written? **[LECTURE 2026-09-14]**
  the professor was emphatic here: a backlog "should not consist of a user story that cannot be
  started until a separate user story is completed."
- **N** — is the *how* still open for discussion?
- **V** — does J name something a real person would trade time or money for?
- **E** — concrete enough to guess at the work? Name any dependency that would change the estimate.
- **S** — one capability, one iteration? Several = an **epic** **[DECK §4.7]**, which fails S.
- **T** — do 4a and 4b actually settle whether it's done?

---

## STEP 7 — Into Word · 5 min

Filename **exactly**: `Assignment-3-<Lastname><Firstinitial>.docx` **[PROMPT]**

```
<Your Name>
CIS 350A — Systems Analysis & Design — Fall 2026
Assignment #3: User Story
2026-10-05

1. <Part 1 text>

2. Instead of <…>, I would like <…>.

3. As a <role>, I want <goal>, so that <justification>.

4. a. <criterion>
   b. <criterion>

5. INVEST evaluation
   Independent — <line>
   Negotiable  — <line>
   Valuable    — <line>
   Estimable   — <line>
   Small       — <line>
   Testable    — <line>
```

No cover page. No diagram — nothing in this prompt asks for one. **Don't put an apology or a
note about lateness in the document.** That belongs in the email, where it can actually buy
something.

**Final sweep:**

- [ ] Filename matches the pattern exactly
- [ ] My name is **inside** the document, not just in the filename
- [ ] Part 3 is one sentence in the literal required format
- [ ] Covering `I want` leaves `so that` still saying something
- [ ] Zero banned words in part 4
- [ ] Uploaded to Canvas
- [ ] Copy dropped in `06 Submitted/`

Then bring parts 3 and 4 back here for critique — that is the part I can do on *your* answer.
If you want the critique before you submit, paste them in; if the clock is the bigger risk,
submit first and we critique after. At 2 days late, shipping beats polishing.
