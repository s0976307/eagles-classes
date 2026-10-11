# Assignment #3 — User Story
Due: Sat 2026-10-03, 23:59 · 10 pts · Ch. 4 · −10%/day late · extensions on request

## Canvas prompt (verbatim)

> Submit your answers to the following exercise as a Word document. Name your document
> "Assignment-3-LastnameFirstinitial," for example "Assignment-3-SmithJ." Include your name
> in the document.
>
> Consider an organizational or individual service which you have personally used, such as
> making an online purchase, making a travel reservation, paying a bill, looking up a library
> resource, registering for a class, and so on. For a real-life example you have encountered,
> complete the following steps:
>
> 1. Write a brief narrative description of the entire process.
> 2. Identify a future state need or desire from your perspective as the user. For example,
>    some feature you would like to be added to the current state.
> 3. For the desired feature identified in (2) above, write a user story for the relevant
>    persona in which you act in the context of that user story. The user story should be
>    stated in the format "As a \<user role>, I want \<user goal>, so that \<user
>    justification>."
> 4. Identify two acceptance criteria for the user story. See Ch. 4.2.1.1 of the textbook for
>    examples. The criteria should be specific and testable. "User friendly" is too vague.
>
> Your solution should follow this example:
>
> 1. This is an online banking service that enables me to manage my checking, savings, debit,
>    and credit card accounts.
> 2. Instead of manually writing checks to pay my bills or transfer money, I would like to
>    pay bills with paper checks mailed by the bank service to the vendor or individual.
> 3. As an online banking service customer, I want to be able to mail checks without
>    physically writing them out, so that I can save time and postage.
> 4. a. The service should allow one-time vendor addresses.
>    b. The service should allow recurring payments of the same amount based on calendar
>    dates up to a year in the future.
>
> Parts (1) and (2) help you focus on the problem area. Part (3) is the user story and Part
> (4) comprises the acceptance criteria. The process does not have to be an online service or
> even a computer-based service, it could be partly or completely manual. Evaluate your user
> story against the INVEST guidelines: Independent, Negotiable, Valuable, Estimable, Small,
> and Testable.

## Rubric (verbatim)

None published in the prompt. The prompt's own structure is the de-facto rubric:
four numbered parts + the INVEST evaluation instruction in the closing paragraph.

## Deliverables

- [ ] `Assignment-3-<Lastname><Firstinitial>.docx`
- [ ] Name in the document
- [ ] Part 1 — narrative of the **entire** current-state process
- [ ] Part 2 — one future-state need, stated from the user's perspective
- [ ] Part 3 — one user story in the exact `As a / I want / so that` format
- [ ] Part 4 — exactly two acceptance criteria, specific and testable
- [ ] INVEST evaluation (see ambiguity below)
- [ ] No diagram required — nothing in this prompt asks for one
- [ ] Copy to `06 Submitted/`

## Ambiguities to resolve

| Question | Assumption I'm making |
|---|---|
| Does the INVEST evaluation go **in** the document? The closing paragraph says "Evaluate your user story against the INVEST guidelines," but the worked example stops at part 4. | **Include it as a short part 5.** Cost of including it if unwanted: near zero. Cost of omitting it if the professor expected it: a graded instruction visibly unaddressed. Asymmetric — include. Label it "5. INVEST evaluation" so it is clearly an addition, not a misnumbered part 4. |
| Exactly two criteria, or at least two? | Prompt says "two," example shows two (a, b). **Write exactly two.** More is not safer here; it reads as not choosing. |
| How long is "brief"? | The worked example's part 1 is **one sentence**. Yours can be 3–6 — "the entire process" in part 1 asks for more than the example gives — but it is a paragraph, not a page. |
| Whose persona? | The prompt pins it: "the relevant persona in which **you** act." The role is the one **you** occupied. Not the pharmacist, not the bank. |

## Analysis — the eight questions

Fill these for **your** chosen service before writing a single sentence of the document.
Parts 1 and 2 of the assignment fall out of this table almost verbatim.

- **Who** (the roles that touch the process, including you):
- **Why** (what the service exists to accomplish for you):
- **What** (the capability you actually came for):
- **Data** (what information moves — what you supply, what comes back):
- **Process** (trigger → steps → outcome, in order):
- **Rules** (constraints: deadlines, eligibility, limits, fees):
- **Interface** (how you touched it — app, web, phone, counter, paper):
- **How** (what is automated vs. what a human does by hand):

## Candidate services — pick one, then stop

Three tests. A candidate that fails any one of them will fight you for the whole assignment.

1. **You personally used it.** Part 1 says so explicitly. This is why I cannot write part 1
   for you — I do not have your experience, and inventing one would be fabrication.
2. **You noticed a real friction.** Not a hypothetical improvement — a moment where you
   thought "why doesn't it just…". That moment *is* part 2.
3. **The fix is small.** One capability, buildable in one iteration. If your desire needs a
   whole new subsystem, it is an **epic**, and it will fail the S in INVEST.

Write three candidates here, then cross out two:

| Service | The friction I actually hit | Small enough? |
|---|---|---|
| | | |
| | | |
| | | |

## Order of work

1. Pick the service (three tests above).
2. Fill the eight questions.
3. Draft parts 1 → 2 → 3 → 4 **in that order**. The order is not cosmetic: part 3 is only
   as good as part 2, and part 2 is only as good as part 1.
4. Run the INVEST audit in `answer-scaffold.md` and fix the story, not the audit.
5. Read parts 3 and 4 aloud. Bring the draft back here for critique.
6. Type into Word, name the file correctly, submit, copy to `06 Submitted/`.

## Self-check before submitting

- [ ] Filename is exactly `Assignment-3-<Lastname><Firstinitial>.docx`
- [ ] My name is inside the document, not just in the filename
- [ ] Part 1 describes the process **end to end**, not just the part I dislike
- [ ] Part 2 names a **need**, not a screen
- [ ] Part 3 is one sentence, in the literal `As a … , I want … , so that …` format
- [ ] Part 3's "so that" is a **benefit**, not a restatement of the "I want"
- [ ] Both criteria in part 4 could be handed to a tester who would know how to pass/fail them
- [ ] Neither criterion contains "easy," "user friendly," "quickly," "intuitive," or "better"
- [ ] I can defend every line out loud without this file open
- [ ] Copy saved to `06 Submitted/`
