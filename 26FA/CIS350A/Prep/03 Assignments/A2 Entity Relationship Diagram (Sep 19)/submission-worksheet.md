# A2 — submission worksheet (late turn-in)

Regenerated 2026-10-05 for late submission. Fill the fields, then type the result into Word.

**Why this is a worksheet and not a finished document.** Two reasons, both hard.
(1) I have not seen Figure 3-11 (p. 88) — nine of ten answers are observations of that
figure, and inventing them would be fabrication, not help. (2) The syllabus permits
collaboration and requires your own work, so the answers go in your words. The reasoning for
every field is already worked out in [answers-and-reasoning.md](answers-and-reasoning.md) —
read that beside this, and these fields take about 30 minutes with the book open.

**Do this first, before the fields.** Email Prof. Inomoto. At 16 days the grade depends on
an extension, not on how fast you finish. Draft at the bottom of this file.

---

## Document header fields

Type these at the top of the Word document.

```
FILENAME:   Assignment-2-________________.docx
            └─ format: Assignment-2-LastnameFirstinitial  (e.g. Assignment-2-SmithJ)

NAME:       ____________________________________
COURSE:     CIS 350A — Systems Analysis & Design — Fall 2026
ASSIGNMENT: Assignment #2: Introduction to the Entity Relationship Diagram
FIGURE:     Figure 3-11, Spurrier & Topi 2nd ed., p. 88
DATE:       ____________________
```

Plain numbered list after that. No cover page, no diagram — neither is asked for.

---

## Answer fields

Each field has three parts. **TERM** is the vocabulary word that must appear or the point is
lost. **EVIDENCE** is the symbol in the figure that proves it — fill this even though it does
not go in the Word doc, because if you can't fill it you don't have the answer.

### Q1 — Attribute that identifies each STORE instance

```
ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     "identifier"  (not "primary key" — see note)
EVIDENCE: the attribute is shown ______________ in STORE's box
```

- **Status: you must read this off the figure.** I will not guess an attribute name.
- Use the **exact spelling** printed in the figure.
- Say *how you know*, not just the name. Underlining is the evidence.
- **The note:** in a conceptual ERD the term is **identifier**; primary/foreign keys are not
  formally part of a conceptual ERD. If the figure is a logical ERD, "primary key" is fair —
  but "identifier" is safe either way.

### Q2 — Cardinality of the EMPLOYEE–STORE relationship

```
COUNT THE LINES between EMPLOYEE and STORE first:  ______ line(s)

RELATIONSHIP I AM DESCRIBING (verb phrase):  ______________________

ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     one of  1:1  /  1:M  /  M:N
EVIDENCE: symbols at each end: ________  and  ________
```

- Cardinality = **how many**. Not the same question as Q3.
- If **two** lines exist, answer for both and name each verb phrase. Costs a sentence,
  removes all ambiguity about which line you meant.
- Candidates worked out in the reasoning file: **1:1** if this is the *manages* line,
  **1:M** if it is the *works at* line.

### Q3 — How many stores can an employee manage — name its optionality

```
ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     one of  mandatory one / mandatory many / optional one / optional many
EVIDENCE: symbol at the STORE end of the manages line: ________
```

- The question says "**name** its optionality" — so the **term** is the answer. A bare
  "0 or 1" answers cardinality and skips what was asked.
- Then add the plain-English rule: an employee may manage zero stores or one store;
  managing a store is not required of an employee.

### Q4 — Why do PT and FT have a disjoint constraint relative to EMPLOYEE?

```
WHAT "d" MEANS:  ______________________________________________________

WHY IT APPLIES TO PT/FT (the business rule):

          ______________________________________________________________

          ______________________________________________________________

TERM:     "disjoint" — an instance belongs to ONLY ONE subtype
CONTRAST: "overlap" (o) — an instance may belong to several at once
EVIDENCE: none needed — the prompt states the "d" for you
```

- **This is the only field that needs nothing from the figure. Write it first.**
- The question asks **why**, so two moves: define `d`, then give the real-world rule that
  makes PT and FT mutually exclusive. Hours thresholds, payroll and benefits classification —
  an employee who is part-time is by that fact not full-time.
- The contrast clause is cheap evidence you know `d` is a choice, not decoration.

### Q5 — What type of entity is LINE ITEM?

```
NOTATION STYLE OF THE FIGURE:   Chen diamonds ☐   Crow's Foot ☐
THEREFORE THE LAYER IS:         conceptual ☐      logical ☐

ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     "associative entity" (logical)  /  "weak entity" (conceptual)
          — and it is also dependent: no identifier of its own
EVIDENCE: attributes that belong to neither parent: ______________________
```

- Tick the boxes before you write. The term depends on the layer.
- The tell: quantity and price belong to **neither** SALE nor PRODUCT — only to the pairing.
  That is what forces the relationship to become an entity, resolving M:N into two 1:M.
- **If the book's caption on p. 88 uses a specific term, use the book's term.**

### Q6 — Crow's foot + 0 on the **left** end of LINE ITEM–PRODUCT

```
WHICH ENTITY IS ON THE LEFT IN THE FIGURE?  ______________________

MEANING OF THE SYMBOL:  ______________________________________________

SENTENCE:

  __________________ → __________________:
  Each ______________ can ______________ zero-to-many ______________.

TERM:     "optional many" / zero-to-many
EVIDENCE: crow's foot = many (touching the entity) · 0 = optional (behind it)
```

- Confirm the orientation before writing. The reading rule: to write "Each A … B", read the
  symbols at **B's** end — the far end from A. So the left-end symbol tells you how many of
  the **left** entity relate to one of the right.
- Must include a **verb phrase** ("can appear on"), not "relates to". A sentence without a
  verb phrase describes the symbol instead of the business rule.

### Q7 — Double bar on the **right** side of LINE ITEM–PRODUCT

```
MEANING OF THE SYMBOL:  ______________________________________________

SENTENCE:

  __________________ → __________________:
  Each ______________ is ______________ one-and-only-one ______________.

TERM:     "mandatory one" / one-and-only-one
EVIDENCE: bar touching entity = one (cardinality) · bar behind it = mandatory (optionality)
```

- **Cross-check against Q6 before you submit.** Together the two sentences must read as a
  coherent 1:M — one product, many line items. If both say "many," or both say "one," one of
  them is read from the wrong end of the line.

### Q8 — Relationship degree at the lower right of PRODUCT

```
WHERE DOES THE LINE GO?   back to PRODUCT ☐    to a third entity ☐

VERB PHRASE ON THE LABEL:  ______________________

ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     "unary" (recursive), degree 1  —  or "ternary", degree 3
EVIDENCE: PRODUCT participates in a relationship with ______________
```

- Degree = **the number of entities involved**. A loop back to PRODUCT is **unary, degree 1**.
  If three entities meet at one relationship it's **ternary, degree 3**. Tick the box first.
- Read the **label** to say what the recursion means in business terms — product-composed-of-
  products (a kit) and product-substitutes-for-product are both common. Don't guess; read it.

### Q9 — Type of attribute: PRODUCT.Product Ingredient

```
HOW MANY VALUES CAN ONE PRODUCT HOLD HERE?   one ☐   many ☐

ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     "multivalued attribute"
EVIDENCE: notation drawn in the figure: ______________________
          (double oval / {braces} / repeat marker / other)
```

- The axis being tested is **count of values**. One packaged product contains flour, sugar,
  salt — many values in one attribute.
- Bonus clause worth having: this is the data dictionary's `{ }` repeating group, and in a
  logical design it would be resolved into its own entity, since a relational column cannot
  hold repeating values.

### Q10 — Type of attribute: PRODUCT.Target GPM

```
IS IT DRAWN DASHED OR PLAIN?   dashed ☐   plain ☐

ATTRIBUTES THE CALCULATION WOULD NEED, IF VISIBLE:  ______________________

ANSWER:   ______________________________________________________________

          ______________________________________________________________

TERM:     "derived attribute"  (if dashed)  /  "stored"  (if plain — read the warning)
EVIDENCE: notation drawn: ______________________
```

- GPM = gross profit margin = `(price − cost) / price`. The axis is **origin**: computed, or
  typed in? A derived attribute isn't stored, because storing it duplicates data already in
  the model and goes stale the moment price or cost changes.
- ⚠️ **"Target" is doing work in that name.** A *target* margin could be a goal somebody sets
  — and a set goal is **stored**, not derived. **The notation settles it, not the word.**
  Tick the dashed/plain box honestly. This is the likeliest field on the sheet to go wrong.

---

## Pre-submission checklist

- [ ] All ten fields filled — no blanks
- [ ] Every **TERM** line's vocabulary actually appears in my answer
- [ ] Every **EVIDENCE** line filled (even though it isn't typed into Word)
- [ ] Q6 and Q7 are full sentences in the professor's SALE/CUSTOMER format, each with a verb phrase
- [ ] Q6 and Q7 are consistent with each other
- [ ] Q2 names which relationship I described
- [ ] Filename is `Assignment-2-<Lastname><Firstinitial>.docx`
- [ ] My name is inside the document
- [ ] I can point at the symbol justifying each answer, out loud, without notes
- [ ] Copy saved to `06 Submitted/`

---

## Extension email — draft for you to edit and send

Yours to send, not mine. Edit the brackets, keep it short, don't over-explain. The syllabus
says extensions are granted on request, so the ask is routine — make it a request, not an
apology.

```
To:      inomoto@niagara.edu
Subject: CIS 350A — Assignment #2 late submission

Professor Inomoto,

I'm requesting an extension to submit Assignment #2 (Introduction to the
Entity Relationship Diagram). I have it completed and can turn it in by
[DATE].

[One sentence of reason, if you want to give one — optional, and the
syllabus does not require it.]

I also want to confirm I'm current on [Assignment #3 / Exam #1] — please
let me know if anything else is outstanding on my record.

Thank you,
[Your name]
```

That last paragraph is the valuable one. It surfaces whatever else is open in one exchange
instead of three.
