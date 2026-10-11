# A2 — answers with reasoning

Companion to [answer-scaffold.md](answer-scaffold.md). Worked 2026-09-28.

**This is not your submission.** It is the reasoning you need in order to write ten answers
you can defend out loud. The syllabus permits collaboration and requires your own work, so
the Word document gets written in your words, from your reading of the figure — not pasted
from here. Where I give a sentence, it's there to show you the *shape* a correct answer
takes, not to be copied.

---

## Provenance legend — check this per answer

| Tag | Means |
|---|---|
| **DERIVED** | Follows from the assignment prompt's own text plus Ch. 3 theory. I'm confident in this. |
| **INFERRED** | Reasoned from the question's wording and standard modeling practice. Likely right, **not verified.** Confirm against p. 88. |
| **UNKNOWN** | Cannot be answered without the figure. You read it off. |

**I have not seen Figure 3-11 (p. 88).** Everything below is built from the assignment's own
wording — which leaks a lot, because the prompt names the symbols — plus the professor's
Chapter 3 deck. Nothing below is a description of the figure itself.

---

## Q1 — Which attribute identifies each instance of STORE?

**UNKNOWN — you must read this one off the figure.**

**Concept.** In a conceptual ERD the unique-identifying attribute is called an
**identifier**, not a primary key. **[DECK]** *"Primary and foreign keys are technically not
part of a conceptual ERD — there they are called identifiers."* They are drawn
**underlined**.

**What to do.** Find STORE's box. The underlined attribute is your answer. It will be named
something along the lines of `Store ID` / `Store Number` / `Store Code` — **use the exact
spelling printed in the figure.** I will not guess at it; a wrong attribute name is a wrong
answer even when the concept is right.

**Answer shape.** Name the attribute, then say how you know:

> `<exact attribute name>` — it is shown underlined, which marks it as STORE's identifier,
> meaning its value is unique for every store instance.

The second clause is what earns the point. "Store ID" alone doesn't show you know *why*.

---

## Q2 — Cardinality of the relationship between EMPLOYEE and STORE?

**INFERRED, two candidates — resolved by counting lines in the figure.**

**Concept.** Cardinality asks **how many**, and is expressed as the shape of the
relationship: **1:1**, **1:M**, or **M:N**. **[DECK]** It is a *different* question from
optionality, which Q3 asks separately.

**Why there are two candidates.** Q3 asks how many stores an employee can *manage*. For
that question to have anything to point at, the figure must draw a **manages** relationship.
Comprehensive textbook figures usually also draw a **works at** relationship — that's how one
figure shows off both a 1:1 and a 1:M. So: **count the lines between EMPLOYEE and STORE.**

| If the figure draws… | Then Q2's answer is |
|---|---|
| **one** line (the *manages* relationship) | **1:1** — one employee manages one store, and one store is managed by one employee |
| **two** lines, and Q2 means *works at* | **1:M** — one store employs many employees; each employee works at exactly one store |

Q2 says "**the** relationship," singular — mild evidence for one line, which would make it the
same *manages* relationship Q3 asks about, giving **1:1**. Mild is not proof. Look.

**Answer shape.** State the cardinality *and* name the relationship you're describing, so
the grader can't mistake which line you meant:

> The `<verb phrase>` relationship between EMPLOYEE and STORE is **1:1** *(or 1:M)* —
> `<one sentence each direction>`.

If there really are two lines, answer for both. Costs you a sentence, removes all ambiguity.

---

## Q3 — How many stores can an employee manage — name its optionality?

**INFERRED — high confidence, confirm the symbol.**

**Concept.** Optionality asks **is participation required**. **[DECK]** Four legal phrases,
and the question demands one of them by name:

| | Meaning | Crow's Foot |
|---|---|---|
| Mandatory one | exactly 1 | `\|\|` |
| Mandatory many | 1 or more | `\|<` |
| **Optional one** | **0 or 1** | `O\|` |
| Optional many | 0 or more | `O<` |

**The reasoning.** The business rule is the giveaway: most employees are not store managers.
So a given employee manages **zero** stores or **one** store — never two, because a store has
one manager. Zero-or-one is **optional one**. The symbol at STORE's end of the *manages* line
should therefore be a **circle then a bar** (`O|`) — circle behind, bar touching STORE.
**Verify that's what's drawn.**

**Answer shape.** The question says "*i.e.*, name its optionality" — so it wants the term,
not a number:

> **Optional one** (zero-or-one). An employee may manage zero stores or one store; managing
> a store is not required of an employee. Shown by the `O` + `|` symbol at the STORE end.

Writing only "one" or only "0 or 1" answers the cardinality half and skips the term asked for.

---

## Q4 — Why do PT and FT have a disjoint constraint relative to EMPLOYEE?

**DERIVED — fully answerable from theory. This is the one question the missing figure
doesn't block. Start here.**

**Concept.** Supertype/subtype constraints come in **two independent pairs** **[DECK]**:

| Pair | Options |
|---|---|
| Completeness | **Total** specialization (every supertype instance is in some subtype) vs. **Partial** (a supertype instance can stand alone) |
| Overlap | **Disjoint** `d` (an instance belongs to **only one** subtype) vs. **Overlap** `o` (an instance can belong to **several at once**) |

The `d` is the second pair. The deck's contrast is exactly the one to cite: `ADVERTISEMENT`
can be both `ONLINE` and `RADIO` simultaneously → overlap. `EMPLOYEE` must be either
`EXEMPT` or `NONEXEMPT`, never both at once → disjoint. **[DECK, Fig. 3-9 / 3-10]**

**The reasoning — and note the question asks "why," not "what."** So a complete answer has
two moves: define `d`, then give the **business rule about the real world** that makes it
apply to PT/FT. The rule is that employment status is a single exclusive classification —
an employee is scheduled, paid, and made benefits-eligible under *one* status at a time.
There is no coherent state in which the same employee is simultaneously part-time and
full-time; the hours threshold that defines one excludes the other.

**Answer shape:**

> The `d` marks a **disjoint** constraint, meaning any single instance of the supertype
> EMPLOYEE can belong to **only one** of its subtypes — never both at the same time. It
> applies to PT and FT because employment status is mutually exclusive by definition: an
> employee's scheduled hours place them in exactly one category, and payroll and benefits
> rules depend on that single classification. An employee who is part-time is by that fact
> not full-time. *(Contrast an overlap constraint `o`, where one instance may belong to
> several subtypes at once.)*

Write that in your own words. The contrast clause at the end is optional but it's cheap
evidence that you know `d` is a choice and not just decoration.

---

## Q5 — What type of entity is LINE ITEM?

**INFERRED — and there's a real terminology trap here. Read this one carefully.**

**Concept.** The deck is emphatic that two terms are **not** synonyms, and splits them by ERD
layer **[DECK]**:

| | **Weak entity** | **Associative entity** |
|---|---|---|
| Layer | **Conceptual** ERD | **Logical** ERD |
| Defined by | Has **no identifier of its own**; depends on other entities' identifiers | A **relationship converted into an entity**, because attributes emerge only from the association of two entities |
| Physical name | — | **Intersection table** — resolves M:N into two 1:M relationships |

> **[DECK]** *"Say 'associative entity' when working in the logical model and 'weak entity'
> in the conceptual model. Casual summaries collapse these; the deck does not."*

**The reasoning.** LINE ITEM is the textbook case. A sale involves many products; a product
appears on many sales — an M:N. But quantity-sold and price-charged belong to **neither**
SALE nor PRODUCT; they exist only because *this* sale included *this* product. That is the
tell **[DECK]**, and it's what forces the relationship to become an entity.

Which term to use depends on the layer, and the prompt gives you evidence: it names **crow's
feet** and **double bars**, which are **Crow's Foot** notation — and per the deck, Crow's
Foot means **logical** ERD, where the term is **associative entity**. That is my read.

**But two cautions.** (1) The chapter is titled *Conceptual* Data Modeling, and the deck notes
analysts often skip the conceptual ERD and go straight to logical — so confirm what the
figure's caption calls itself. (2) LINE ITEM is *simultaneously* weak/dependent: it has no
identifier of its own and is identified through SALE. Both descriptions are true of the same
box; they're answers at different layers.

**Answer shape.** Name the type, then prove it with the tell:

> LINE ITEM is an **associative entity** *(the logical-ERD form of a weak entity)*. It exists
> because the relationship between SALE and PRODUCT is many-to-many and carries attributes of
> its own — quantity and price belong to neither SALE nor PRODUCT, only to the pairing of a
> particular sale with a particular product. Converting the relationship into an entity
> resolves the M:N into two 1:M relationships. It is also a **dependent/weak** entity: it has
> no identifier of its own and is identified through SALE.

**If the book's caption or prose on p. 88 uses a specific term, use the book's term.** The
professor wrote the question from the figure, not from my table.

---

## Q6 — Meaning of the crow's foot + 0 on the **left** end of LINE ITEM–PRODUCT?

**DERIVED for the symbol · INFERRED for the direction.**

**Step 1 — decode the symbol. [DERIVED]** Crow's foot = **many**. `0` = **optional / zero**.
Together: **optional many**, read as **zero-to-many**. **[DECK]**

**Step 2 — figure out which entity that describes.** The professor handed you the decoder in
the prompt. Reverse-engineer it:

```
"Each Sale is sold to one-and-only-one Customer."   ← the || sits at the CUSTOMER end
"Each Customer can have zero-to-many Sales."        ← the O< sits at the SALE end
```

**The rule: to write "Each A … B", read the symbol pair at B's end — the far end from A.**
So the **left-end** symbol describes **how many of the left entity** relate to one instance of
the right entity.

**Step 3 — which entity is on the left? [INFERRED]** The prompt writes the pair as "LINE ITEM
and PRODUCT," which normally tracks left-to-right, so LINE ITEM on the left. The semantics
confirm it: "each Product can appear on zero-to-many Line Items" is a sensible rule — a
product that has never sold has zero line items. The alternative reading, "each Line Item
refers to zero-to-many Products," is nonsense, since a line item exists precisely to name one
product. **Glance at the figure to confirm the orientation, then commit.**

**Answer shape** — the prompt wants both the meaning *and* a sentence:

> The crow's foot plus `0` means **optional many** — zero-to-many — and it governs how many
> LINE ITEMs relate to one PRODUCT. It tells us participation is not required: a product
> need not appear on any line item.
> **PRODUCT → LINE ITEM: Each Product can appear on zero-to-many Line Items.**

Note the verb phrase — "can appear on," not "relates to." **[DECK]** Relationships are named
with verb phrases; a sentence without one describes the symbol instead of the business rule.

---

## Q7 — Meaning of the double bar on the **right** side of LINE ITEM–PRODUCT?

**DERIVED for the symbol · INFERRED for the direction (same orientation call as Q6).**

**Decode. [DERIVED]** Two bars: the one touching the entity is the **cardinality** — `|` =
**one**. The one behind it is the **optionality** — `|` = **mandatory**. Together:
**mandatory one**, read as **one-and-only-one**. **[DECK]**

**Direction.** By the same rule, the **right-end** symbol describes how many of the **right**
entity (PRODUCT) relate to one instance of the left entity (LINE ITEM).

**Answer shape:**

> The double bar means **mandatory one** — one-and-only-one — and it governs how many PRODUCTs
> relate to one LINE ITEM. Participation is required: a line item cannot exist without a
> product, and it cannot name more than one.
> **LINE ITEM → PRODUCT: Each Line Item is for one-and-only-one Product.**

**Cross-check Q6 against Q7 before you submit.** Together they must read as a coherent 1:M:
one product, many line items. If your two sentences both say "many," or both say "one," one
of them is wrong — and the likeliest cause is reading a symbol from the wrong end of the line.

---

## Q8 — What relationship degree is diagrammed at the lower right of PRODUCT?

**INFERRED — high confidence on the term, lower on the business meaning.**

**Concept. [DECK]** Degree = **the number of entities involved in a relationship.** Most
relationships are binary.

| Degree | Name | Drawn as |
|---|---|---|
| 1 | **Unary** (also *recursive* / *self-referencing*) | a line from the entity back to **itself** |
| 2 | **Binary** | two different entities |
| 3 | **Ternary** | three entities in one relationship |

**The reasoning.** The question localizes the relationship to one corner of **a single entity**
— "the lower right of PRODUCT" — and asks for its *degree*. If the line ran to some other
entity, the answer would be "binary," which is true of nearly every line in the figure and
would make for a pointless question. A loop leaving PRODUCT and returning to PRODUCT is the
standard way that corner gets drawn. So: **degree 1, a unary / recursive relationship.**

**Confirm two things in the figure.** (1) That the line genuinely returns to PRODUCT rather
than running off to a third entity — if three entities meet at one relationship, it's
**ternary**, degree 3. (2) The relationship's **verb phrase label**, which tells you what the
recursion *means*. Common business readings are a product being composed of other products
(a kit or bundle), or a product substituting for another. **Don't assert which one — read the
label.**

**Answer shape:**

> A **unary** (recursive) relationship — **degree 1** — because PRODUCT participates in a
> relationship with **itself**: one product instance relates to other product instances.
> Per the label, `<verb phrase>`, this records `<what it means in business terms>`.

---

## Q9 — What type of attribute is PRODUCT.Product Ingredient?

**INFERRED — confirm against the notation drawn.**

**Concept.** Attributes get classified on several **independent** axes, and each question here
is testing a different one:

| Axis | Options | Typical notation |
|---|---|---|
| Decomposability | Simple vs. **Composite** | sub-attributes listed beneath |
| Count of values | Single-valued vs. **Multivalued** | double oval, `{braces}`, or a repeat marker |
| Origin | Stored vs. **Derived** | dashed oval, or a `/` prefix |
| Uniqueness | Identifier | **underlined** |

**The reasoning.** The question to ask is *how many values can one instance hold?* A single
product — think of any packaged food item — contains flour, sugar, salt, and so on. One
PRODUCT instance therefore holds **many** ingredient values in that one attribute. That is a
**multivalued attribute**.

**[DECK]** Note the connection to the data dictionary: multivalued attributes are what the
`{ }` braces mean — *"repeating group of elements"* — and *"repeating groups occur in
non-normalized user views."* Mentioning that a multivalued attribute is normally resolved
into a separate entity is a genuine bonus clause, not padding.

**Check the figure** for the marker Spurrier & Topi use — a double oval, braces, or a
parenthetical like `(0..*)`. Name it in your answer.

**Answer shape:**

> A **multivalued attribute** — shown by `<the notation in the figure>`. One product instance
> can have many ingredient values, so the attribute holds a set rather than a single value.
> *(In a logical/physical design this would normally be resolved into its own entity related
> to PRODUCT, since a relational table cannot store repeating values in one column.)*

---

## Q10 — What type of attribute is PRODUCT.Target GPM?

**INFERRED — confirm against the notation drawn.**

**The reasoning.** GPM is **gross profit margin**. It is an arithmetic result:
`(selling price − cost) / selling price`. The question to ask — the *other* axis from Q9 — is
*does somebody type this in, or does the system work it out?* If PRODUCT already carries a
price attribute and a cost attribute, then GPM is not independent data; storing it would
duplicate information already present and create an update anomaly the moment either input
changes. So it is a **derived attribute** — computed on demand rather than stored.

**Check the figure** for how it's marked — a **dashed** oval/outline, or a `/` prefix, are the
usual notations **[STD]**. Also check whether PRODUCT actually shows the price and cost
attributes the calculation needs; naming them makes your answer concrete and hard to argue
with.

**Answer shape:**

> A **derived attribute** — shown by `<the notation in the figure>`. Its value is calculated
> from other attributes rather than stored independently: gross profit margin is
> `(price − cost) / price`, computable from `<name the attributes you can see>`. Storing it
> would duplicate data already in the model and risk inconsistency when price or cost changes.

> ⚠️ **"Target" is worth a second look.** A *target* margin could be a goal somebody sets
> rather than an actual computed figure — and a set goal would be **stored**, not derived.
> The figure's notation settles it, not the word. If it's drawn dashed, it's derived; if it's
> drawn plain, reconsider. This is the one answer on the sheet where I'd most want the figure
> in front of me.

---

## Where you stand

| Q | Status | What's still needed |
|---:|---|---|
| 1 | **UNKNOWN** | the attribute's exact name |
| 2 | INFERRED ×2 | count the EMPLOYEE–STORE lines |
| 3 | INFERRED | confirm the `O\|` symbol |
| 4 | **DERIVED** | nothing — write it now |
| 5 | INFERRED | confirm notation style / the book's term |
| 6 | DERIVED + orientation | confirm LINE ITEM is on the left |
| 7 | DERIVED + orientation | same call as Q6 |
| 8 | INFERRED | confirm it loops to PRODUCT; read the verb label |
| 9 | INFERRED | confirm the multivalued marker |
| 10 | INFERRED | confirm dashed vs. plain — see the warning |

**Nine of ten hinge on p. 88.** Open the textbook in Canvas → Course Materials, fill the
attempt table in [answer-scaffold.md](answer-scaffold.md), and bring it back — I'll critique
the answers against what you actually see rather than against what I've reasoned out here.

**And the deadline is still the live issue.** [COURSE-INFO.md](../../01%20Syllabus%20and%20Course%20Info/COURSE-INFO.md)
puts this at Sat 19 Sep, which is nine days past at −10%/day. Email Prof. Inomoto before you
spend an evening on the answers.
