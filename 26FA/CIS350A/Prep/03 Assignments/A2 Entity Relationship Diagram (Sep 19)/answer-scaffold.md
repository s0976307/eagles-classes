# A2 — answer scaffold

**What this file is:** the skeleton of your Word document, plus — per question — the concept
being tested and what a complete answer must contain. **It contains no answers.** You write
those from Figure 3-11 on p. 88, and you should be able to defend every one out loud.

**Provenance — read this before you trust anything below.**

- Items marked **[DECK]** come from `02 Readings and Notes/CH03-NOTES.md`, extracted from
  the professor's own Chapter 3 slides. Highest authority available in this workspace.
- Items marked **[STD]** are standard Crow's Foot / EER notation. Reliable in general, but
  Spurrier & Topi may notate their own way.
- Items marked **[CHECK BOOK]** are things I cannot verify without the figure. The book's
  prose around p. 88 is the authority — not generic notation, and not me.
- **I have not seen Figure 3-11.** Nothing below describes what is in it.

---

## Document skeleton

```
Assignment-2-<Lastname><Firstinitial>.docx

<Your Name>
CIS 350A — Systems Analysis & Design — Fall 2026
Assignment #2: Introduction to the Entity Relationship Diagram
<date submitted>

1. <answer>
2. <answer>
...
10. <answer>
```

Plain numbered list. No cover page, no diagram — nothing in the prompt asks for either.

---

## Notation you need before you start

### 1. Identifiers *(Q1)*

**[DECK]** In a *conceptual* ERD the key attribute is called an **identifier**, not a
primary key — "primary and foreign keys are technically not part of a conceptual ERD."
**Identifiers are shown underlined.**

So Q1 is a two-part answer: name the attribute, and say *how you know* (it's underlined /
marked as the identifier). Give the attribute's exact name as printed in the figure.

### 2. Cardinality vs. optionality — they are different questions *(Q2, Q3, Q6, Q7)*

**[DECK]** This is the distinction Q2 and Q3 are built to test, and the one students
collapse:

| | Asks |
|---|---|
| **Cardinality** | **How many?** — one, or many |
| **Optionality** | **Is participation required?** — mandatory, or optional |

Four combinations: **mandatory one** (exactly 1) · **mandatory many** (1 or more) ·
**optional one** (0 or 1) · **optional many** (0 or more).

Crow's Foot symbols **[DECK]**: `|` exactly one · `O` zero / optional · `<` many.
They come in pairs at each end. The mark **touching the entity box** is the **cardinality**
(`|` one, `<` many); the mark **behind it, toward the middle of the line**, is the
**optionality** (`O` optional, `|` mandatory). **[STD]**

> Sanity check that ordering against the prompt's own words: it calls the left-end symbol
> "crow's foot + 0" — crow's foot against the entity, `0` behind it. That is optional many.

| At one end | Reads as |
|---|---|
| `||` double bar | mandatory one — **one and only one** |
| `O|` circle + bar | optional one — **zero or one** |
| `|<` bar + crow's foot | mandatory many — **one or many** |
| `O<` circle + crow's foot | optional many — **zero to many** |

Q2 asks *cardinality* — so it wants the **1:1 / 1:M / M:N** shape of the EMPLOYEE–STORE
relationship. Q3 asks *optionality* — so it wants one of the four phrases above, applied
to how many stores an employee manages. Do not answer Q3 with a number alone.

> ⚠️ Check whether Figure 3-11 draws **two** lines between EMPLOYEE and STORE. Q3's
> existence as a separate question hints that *managing* a store is not the same
> relationship as *working at* one. If there are two, name which you're describing.

### 3. Reading direction — the rule that makes Q6 and Q7 work

The professor handed you the decoder in the prompt itself. Reverse-engineer it before you
touch Q6/Q7:

```
SALE -> CUSTOMER:  Each Sale is sold to one-and-only-one Customer.   ← justified by the symbol at the CUSTOMER end
CUSTOMER -> SALE:  Each Customer can have zero-to-many Sales.        ← justified by the symbol at the SALE end
```

**The rule:** to write "Each A … B", read the symbol pair sitting at **B's** end of the
line — the far end from A. **[STD, and consistent with the professor's example — verify it
against the SALE/CUSTOMER symbols in the figure before you rely on it.]**

Each sentence needs three things: the entity you start from, the optionality-plus-
cardinality phrase, and a **verb phrase** that says what the relationship actually means
("is sold to", "can have"). **[DECK]** Relationships are named with verb phrases. Don't
write "Each Line Item relates to one Product" — that's the symbol, not the meaning.

Q6 and Q7 are the *same* relationship read in the two directions. Write one sentence each,
and make sure they're consistent with each other.

### 4. Supertype / subtype constraints *(Q4)*

**[DECK]** Two independent pairs. Q4 is about the second pair:

| Constraint | Meaning |
|---|---|
| **Total** specialization | Each supertype instance must belong to one of the subtypes |
| **Partial** specialization | A supertype instance can stand on its own |
| **Overlap** (`o`) | An instance can belong to **multiple** subtypes at once |
| **Disjoint** (`d`) | An instance belongs to **only one** subtype |

The deck's own example: `EMPLOYEE` must be either `EXEMPT` or `NONEXEMPT`, never both
(Fig. 3-10). Contrast `ADVERTISEMENT`, which can be both `ONLINE` and `RADIO` — overlap.

Q4 asks **"why"**, not "what". A complete answer states what `d` means *and* gives the
business-rule reason it applies to PT/FT specifically — something about the nature of
employment status that makes the two mutually exclusive at any one time. That reason is
yours to state; it's a sentence about the real world, not about notation.

### 5. Entity types *(Q5)*

**[DECK]** The deck is emphatic that these are **not** synonyms, and separates them by
ERD layer:

| | **Weak entity** | **Associative entity** |
|---|---|---|
| Layer | **Conceptual** ERD | **Logical** ERD |
| Defined by | No primary key of its own; depends on other entities' keys | A relationship converted into an entity because attributes emerge **only** from the association of two entities |
| Physical name | — | **Intersection table** — resolves M:N into two 1:M relationships |

The tell **[DECK]**: the attributes belong to *neither* parent entity — they exist only
because a particular instance of one met a particular instance of the other.

So Q5 turns on two observations you make from the figure:
1. Does LINE ITEM's attributes-and-key structure match that tell?
2. Is Figure 3-11 drawn in **Chen's** notation (relationships as diamonds → conceptual) or
   **Crow's Foot** (→ logical)? **[DECK]** The question mentions crow's feet and double
   bars, which is evidence — but confirm, and name your entity type to match the layer.

If the book's own caption or prose around p. 88 uses a specific term, **use the book's
term.** **[CHECK BOOK]**

### 6. Relationship degree *(Q8)*

**[DECK]** Degree = **the number of entities involved in a relationship.** Most
relationships are binary.

| Degree | Name | Looks like |
|---|---|---|
| 1 | **Unary** / recursive | A line from an entity back to **itself** |
| 2 | **Binary** | Two different entities |
| 3 | **Ternary** | Three entities joined in one relationship |

Q8 says "at the lower right of PRODUCT" — so look at what the line's *other* end connects
to. Name the degree, and a strong answer adds one clause on what it means in business
terms (what a product's relationship to that thing represents).

### 7. Attribute types *(Q9, Q10)*

**[STD]** EER classifies attributes along several independent axes. Q9 and Q10 are each
testing a different one:

| Type | Means | Usual notation |
|---|---|---|
| **Simple** | Cannot be broken down further | plain |
| **Composite** | Decomposes into sub-attributes (Address → Street, City, Zip) | sub-attributes shown beneath |
| **Single-valued** | Exactly one value per instance | plain |
| **Multivalued** | **Many values** for a single instance | double oval, `{braces}`, or a repeating marker |
| **Stored** | Physically held in the data | plain |
| **Derived** | **Calculated** from other attributes; not stored | dashed oval, or `/` prefix |
| **Identifier** | Uniquely identifies the instance | **underlined** |
| **Optional** | May be null | `(parens)` or `O` |

Ask of each attribute, in order: *how many values can one product have?* and *is this a
number somebody types in, or one the system works out?*

- **Q9, `Product Ingredient`** — a singular noun naming a thing a product contains.
  How many ingredients does a product have? That framing points at one axis of the table.
- **Q10, `Target GPM`** — gross profit margin. A margin is `(price − cost) / price`.
  If price and cost are already attributes elsewhere in the figure, that points at a
  different axis.

**Match your answer to the notation actually drawn in Figure 3-11**, and name the notation
in your answer ("it is shown as a …, which indicates …"). **[CHECK BOOK]** — Spurrier &
Topi's symbol for these may differ from the generic ones above. If the figure marks them a
way the table doesn't cover, go with the book.

---

## Work order

1. Open p. 88 in Canvas → Course Materials. Do **not** work from the PDF thumbnail.
2. Before answering anything, identify the notation style and the ERD layer (§5).
3. Answer Q4 first — it's pure theory and builds momentum.
4. Q1 → Q2 → Q3 → Q5 → Q8 → Q9 → Q10 (each is one figure observation + one concept name).
5. Q6/Q7 last. Decode the SALE/CUSTOMER example against the figure first (§3), confirm the
   reading rule holds, *then* write your two sentences.
6. Read your ten answers aloud. Any you can't justify by pointing at a symbol is not done.

## Your attempts

Write them here first, then ask for the critique. Blank until you fill it.

| Q | Your answer | Symbol/evidence in the figure |
|---|---|---|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |
| 6 | | |
| 7 | | |
| 8 | | |
| 9 | | |
| 10 | | |
