# A3 — answer scaffold

**What this file is:** the skeleton of your Word document, what each part is testing, what a
complete answer contains, and one **fully worked specimen on a service that is not yours**.
The specimen exists to be taken apart, not copied — part 1 of this assignment requires a
service *you have personally used*, so the submitted answer cannot come from me.

**Provenance — read before trusting anything below.**

- **[DECK]** — from `02 Readings and Notes/CH04-NOTES.md`, extracted from the professor's own
  Chapter 4 slides on 2026-09-28. Highest authority in this workspace.
- **[PROMPT]** — the assignment text itself, including the professor's worked banking example.
- **[STD]** — standard agile practice. Generally reliable; Spurrier & Topi may phrase it
  their own way.
- **[CHECK BOOK]** — the prompt cites **Ch. 4.2.1.1** for acceptance-criteria examples. I have
  the slide deck, not that section. Open it. The book's examples outrank mine.
- **[SPECIMEN]** — my demonstration. Not course material, not yours to submit.

---

## Document skeleton

```
Assignment-3-<Lastname><Firstinitial>.docx

<Your Name>
CIS 350A — Systems Analysis & Design — Fall 2026
Assignment #3: User Story
<date submitted>

1. <narrative of the current-state process>

2. <the future-state need>

3. As a <role>, I want <goal>, so that <justification>.

4. a. <acceptance criterion>
   b. <acceptance criterion>

5. INVEST evaluation
   Independent — <one line>
   Negotiable  — <one line>
   Valuable    — <one line>
   Estimable   — <one line>
   Small       — <one line>
   Testable    — <one line>
```

Plain numbered list, matching the professor's example layout exactly. No cover page, no
diagram — nothing in the prompt asks for either. Part 5 is the judgment call documented in
`prompt-and-plan.md`; if you'd rather ask than assume, email the professor — the syllabus
promises a reply within one business day and you have until Sat 2026-10-03, 23:59.

---

## Part 1 — the narrative

**Tests:** whether you can describe a **current state** end to end without editorializing.
Same skill as Ch. 2's current-state activity diagram, in prose.

**Contains:** the service and what it does for you · the trigger that starts the process ·
the steps in order · what you supply and what comes back · how it ends. Present tense, first
person, 3–6 sentences.

**Traps:**

- **Describing only the broken part.** "The entire process" **[PROMPT]** means from trigger
  to outcome. The friction is a *detail inside* the narrative, not the narrative.
- **Complaining in part 1.** Keep the grievance for part 2. Part 1 should read like a neutral
  observer wrote it — that neutrality is what makes part 2 land as a finding rather than a mood.
- **Jumping to technology.** "The process does not have to be an online service or even a
  computer-based service" **[PROMPT]**. A counter, a phone tree, and a paper form are all
  legitimate current states.

**Calibration:** the professor's own part 1 is a single sentence naming the service and its
scope **[PROMPT]**. That is the floor. "The entire process" is the reason to go above it.

## Part 2 — the future-state need

**Tests:** the **WHAT/HOW** line that runs through the whole course. **[DECK §4.1]** Features
answer *what new capability is needed*; designs answer *how to build it*. Part 2 must stay on
the **what** side.

**Contains:** the gap, stated from your perspective as the user, in the shape
*"instead of \<current-state pain>, I would like \<capability>."* — which is literally how the
professor's example is built **[PROMPT]**.

**Traps:**

- **Naming a screen instead of a need.** "I would like a dashboard with a status column" is a
  design. "I would like to know when my order is ready without calling" is a need. The test:
  could two different teams build two very different things that both satisfy your sentence?
  If yes, it is a need. If only one implementation fits, you wrote a design.
- **Bundling.** One desire. Two desires become two stories and kill the **S** in INVEST.
- **Speaking for the organization.** "so the pharmacy can reduce call volume" is the
  *business* case. Part 2 says "from your perspective as the user" **[PROMPT]**.

## Part 3 — the user story

**Definition [DECK §4.3]:** *a brief narrative description of a system feature (capability)
that includes a **user role**, a **need** important to that role, and a **justification** for
the need.* Components: **Who** — actor, role, or persona · **What** — goal, need, or desire ·
**Why** — justification.

**Format [DECK §4.3 / PROMPT]:** `As a <role>, I want <goal>, so that <benefit>.`

**Deck example [DECK §4.3]:**

> As a retail store customer, I want to be able to easily find a product that meets my needs,
> so that I can complete picking up my purchases accurately, efficiently, and without delays.

### The three slots, and how each one fails

| Slot | Contains | Fails when |
|---|---|---|
| `As a <role>` | The persona **you** occupied **[PROMPT]** — named by relationship to the service | "As a user." Too generic to constrain anything. Both the deck and the professor's example name the relationship: *retail store customer*, *online banking service customer*. |
| `I want <goal>` | A capability | It names a UI element, a technology, or a vendor. Ch. 4.1's WHAT/HOW line again. |
| `so that <justification>` | The **benefit** that follows from having the capability | **It restates the goal.** This is the single most common failure. |

**The restatement trap, concretely.** These look like stories and are not:

- ✗ "…I want to get a notification, so that I am notified." — circular.
- ✗ "…I want to pay online, so that I can pay online." — same clause twice.
- ✓ "…I want to mail checks without physically writing them out, so that I can **save time
  and postage**." **[PROMPT]** — the benefit is a *consequence*, in a different currency
  (time, money, accuracy, risk, anxiety) than the goal.

**Diagnostic:** cover the `I want` clause. Does the `so that` clause still say something?
If it evaporates, rewrite it.

**Also know the "shall" form [DECK §4.3]:** `A <role> shall be able to <goal>.` A single-
sentence alternative for documenting the same business need. Not what this assignment asks
for — but an exam may ask you to convert between the two, so write your story knowing it
converts cleanly.

**One property worth stating in your head:** a user story "expresses ideas for business
requirements" and is **usually not sufficient by itself** to *be* one **[DECK §4.3]** — it is
"a promise of a conversation" **[DECK §4.9]**. That is exactly why part 4 exists.

## Part 4 — the two acceptance criteria

**Definition [DECK §4.4]:** *criteria that must be met for the solution to be acceptable by
the requesting user* — constraints that limit acceptable solutions, and the **foundation for
user acceptance tests**.

**Two kinds [DECK §4.4]:**

| | Covers |
|---|---|
| **Functional** | **Variations** — complexities or specific details · **Exceptions** — error conditions |
| **Nonfunctional** | Operational characteristics that don't directly affect functional behavior |

Look at what the professor's example does with its two **[PROMPT]**: (a) a *variation* —
one-time vendor addresses; (b) a *variation with a bounded limit* — recurring payments of the
same amount, on calendar dates, **up to a year** in the future. Both add a specific detail the
story's one sentence could not carry. Neither describes a screen.

**The deck's own criteria [DECK §4.4]** are worth studying for the same reason:

1. Available on at least the two most popular mobile computing platforms.
2. User can identify the product by entering (part of) its name **or** its UPC code.
3. If unavailable, indicate whether the store typically carries it and when it is expected back.
4. Communicate location as an aisle/bay combination **OR** on a map showing directions from
   the customer's current location.

Note #1 is **nonfunctional**, #3 is an **exception**, and #2 and #4 use an explicit **OR** —
which is what keeps them *constraints on acceptable solutions* rather than designs. That OR is
a technique you can steal.

**The testability bar.** "The criteria should be specific and testable. 'User friendly' is too
vague." **[PROMPT]** Operational test: **could you hand this to someone who has never seen the
system, and would they know how to make it pass or fail?** If the criterion contains *easy,
quick, intuitive, seamless, reliable, better, user friendly* — it has no pass/fail line. Replace
the adjective with a number, a list, or a condition.

Gherkin **[DECK §4.8]** is the stress test, not the deliverable. If you cannot phrase your
criterion as `Given <precondition> / When <action> / Then <outcome>`, it is not testable yet.
Write it in that shape on scratch paper, then flatten it back into the assignment's sentence form.

**Traps:**

- **Writing the design.** "There should be a bell icon in the top right corner." Wrong lens —
  that is Assignment #4.
- **Restating the story.** A criterion that just repeats the `I want` adds nothing. Each
  criterion must add a *detail the story could not carry*: a variation, an exception, a limit,
  or a quality threshold.
- **Two criteria that are the same criterion.** Vary the kind — e.g. one variation and one
  exception, or one functional and one nonfunctional.

**Optional strong move [DECK §4.5]:** *each acceptance criterion can carry its own MoSCoW
priority* — not just each story. Tagging one `(Must have)` and the other `(Should have)` shows
you read past the definition. Keep it to a parenthetical; don't let it crowd the criterion.

## Part 5 — the INVEST evaluation

**[DECK §4.6]** — criteria for evaluating a user story:

| | | The question to ask your story |
|---|---|---|
| **I**ndependent | of other user stories | Could this be built and released without first building something else you have not written? |
| **N**egotiable | room for discovery changes | Have I left the *how* open, so the team and I can still negotiate implementation? |
| **V**aluable | to the user — cf. MoSCoW | Does the `so that` clause name a benefit a real person would pay for in time or money? |
| **E**stimable | sized, so it can be prioritized | Is it concrete enough that a developer could guess at the work? Vague goals cannot be estimated. |
| **S**mall | completable within an iteration | One capability, or several wearing one sentence? Several = an **epic** **[DECK §4.7]**, which fails S. |
| **T**estable | according to acceptance criteria | Do my two criteria actually settle whether it's done? |

**Write one line per letter, and be willing to fail one.** An honest "**E** — estimable only
once we know whether the pharmacy's system can expose status changes; that dependency is the
first thing to resolve" is a better answer than six lines of "yes." **[STD]** The audit exists
to find problems. If it finds one, **fix the story, not the audit.**

---

## [SPECIMEN] — a worked example, with the seams showing

**Service: a retail pharmacy prescription refill.** Not your service. Do not submit this.
It is here so you can watch the four parts click together — and watch a first draft fail.

### 1. Narrative

> I refill a maintenance prescription at a chain pharmacy about every ninety days. When the
> bottle runs low I open the pharmacy's app, select the prescription, and tap refill, or I
> call the automated phone line and key in the prescription number. The pharmacy then fills
> the order at whatever point in their queue it reaches, which may be the same afternoon or
> the next day depending on whether they have the drug in stock. I have no way to see that
> progress, so I drive to the store and ask at the counter; if it is not ready I wait in the
> store or leave and come back later. Once it is filled I pay at the counter and the process
> ends.

*Why it works:* trigger (bottle runs low) → steps in order → what I supply (prescription
number) → what comes back (the filled order) → ending (pay and leave). The friction — no
visibility into progress — is **stated as a fact inside the narrative**, not complained about.

### 2. Future-state need

> Instead of driving to the store to find out whether my prescription is ready, I would like
> the pharmacy to tell me when it is ready, before I leave the house.

*Why it works:* it is a **need**, not a design. Text message, email, push notification, and a
phone call all satisfy it — which is the test from part 2 above. It is one desire, and it maps
to exactly one capability.

### 3. User story — first draft, then the repair

**First draft (broken — read this one critically):**

> ✗ As a pharmacy customer, I want a notification screen in the app showing my prescription
> status, so that I can see my prescription status.

Three failures, all diagnosable with the tables above:

1. *"a notification screen in the app"* is a **design**, not a capability — the WHAT/HOW line
   **[DECK §4.1]**. It also kills **N**: it forecloses the negotiation before it starts.
2. *"so that I can see my prescription status"* **restates the goal**. Cover the `I want`
   clause and the `so that` says nothing. No benefit, so it fails **V**.
3. "showing my prescription status" is broad enough to mean a status history, a refill
   calendar, and an order tracker — three stories in one sentence. Fails **S**.

**Repaired:**

> ✓ As a pharmacy customer, I want to be told when my prescription is ready for pickup, so
> that I can make one trip to the store instead of driving there to check.

*Why the repair works:* the role names the relationship to the service. The goal is a
capability with the implementation left open. The benefit — **one trip instead of two** — is in
a different currency (time and fuel) than the goal, and survives covering the `I want` clause.

### 4. Acceptance criteria

> a. When a prescription's status changes to "ready for pickup," the service sends a message
>    to the customer's registered mobile number within 15 minutes of that status change.
>    *(Must have)*
>
> b. The customer can set a notification preference of text message, e-mail, or none, per
>    prescription, and the change takes effect on the next refill without contacting the
>    pharmacy. *(Should have)*

*Why they work:* (a) is a **functional variation** with a number in it — a tester knows exactly
how to fail it. (b) is a second **variation** that adds a detail the one-sentence story could
not carry, and its "or none" is the deck's **OR** technique **[DECK §4.4]**, constraining the
solution without designing it. Neither mentions a button, a color, or a screen. Both are
written as *outcomes*, which is what makes them convertible to Gherkin:
`Given a prescription marked ready / When 15 minutes have elapsed / Then the customer has
received a message.`

### 5. INVEST evaluation

> **Independent** — the notification does not require any other story in my backlog; it needs
> only the status value the pharmacy's fill system already sets.
> **Negotiable** — the story does not specify text, e-mail, or push; the channel is settled in
> criterion (b) and remains open to discussion.
> **Valuable** — it removes one round trip per refill, roughly four trips a year per customer.
> **Estimable** — small, *conditional on* the fill system exposing a status-change event. If it
> does not, the estimate changes materially; that dependency is the first thing to verify.
> **Small** — one capability, one trigger, one message. Deliverable in a single iteration.
> **Testable** — criterion (a) gives a pass/fail threshold; criterion (b) is verifiable by
> changing the setting and running one refill.

*Why this works:* **E** is answered honestly, with a named dependency, instead of being waved
through. That is the audit doing its job.

---

## Order of work

1. `prompt-and-plan.md` — pick your service against the three tests, fill the eight questions.
2. Draft part 1. Read it back: does a stranger know what the service is and how it ends?
3. Draft part 2 in the *"instead of X, I would like Y"* shape. Check it is a need, not a screen.
4. Draft part 3. Run the three-slot table on it, then the cover-the-`I want` diagnostic.
5. Open **Ch. 4.2.1.1** **[CHECK BOOK]** and read the book's acceptance-criteria examples before
   drafting part 4. Match the book's register, not mine.
6. Draft two criteria of *different kinds*. Stress-test each in Gherkin.
7. Run INVEST. Fix the story if the audit bites.
8. Type into Word. Check the filename. Submit. Copy to `06 Submitted/`.

Bring the draft here for critique before you submit — that is the part I can actually do on
your own answer.

## Your draft

Blank until you fill it. Write here first, then ask for the critique.

| Part | Your text |
|---|---|
| 1 — narrative | |
| 2 — future-state need | |
| 3 — user story | |
| 4a — criterion | |
| 4b — criterion | |

### INVEST self-audit of *your* story

| | Verdict | Why |
|---|---|---|
| Independent | | |
| Negotiable | | |
| Valuable | | |
| Estimable | | |
| Small | | |
| Testable | | |
