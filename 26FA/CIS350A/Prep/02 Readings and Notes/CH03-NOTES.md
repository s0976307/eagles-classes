# Ch. 3 — Conceptual Data Modeling

Weeks 3–4 · **40 slides** · deck revision `25FA-2` · Exam #1 (Ch. 1–4)

> **Provenance: SOURCE.** Extracted directly from
> `Systems Course Material\CIS350 Chapter 3 - Conceptual Data Modeling.pptx` on
> 2026-09-28. Slide numbers cited throughout. Figure slides (7, 8, 11–14, 16, 17, 20–27)
> are images — open the deck for those; text extraction can't render them.
>
> ⚠️ Deck stamps **Revision 25FA-2** — last fall's revision, unlike the Ch. 4 deck
> (`26FA-1`). Content may have been updated in lecture. Check your class notes.

## 3.1 — Domain modeling *(slides 2–3)*

Chapter 3 concerns modeling the **"key concepts of the domain of interest."**

- **Domain of interest** — the focus of the BA investigation; the specific area that will
  be transformed from current state to future state. **Delineated by a context diagram.**
- **Concepts** — features or characteristics of the domain; essential or "ideal" forms,
  structures, or categories.

> Many breeds of dogs exist, but there is an idealized abstraction called `DOG` with
> attributes shared by all actual dogs. `STUDENT` would be a key concept in an
> investigation whose domain of interest was a college grading system.

Two methods, and the course picks one:

| Model | Artifact |
|---|---|
| Conceptual domain (data) model | **Enhanced entity-relationship diagram (EER / ERD)** |
| Domain (data) model | Class diagram — also usable, but tends to support OO programming |

**This class focuses on ERDs, not class diagrams** (slide 3). They share basic features
but use different notation.

## 3.2 — Why ERDs *(slide 4)*

An ERD visually represents **the organization's information requirements.**

- Data requirements are **more stable over time** than process requirements or business
  rules — which facilitates data reuse and sharing.
- Can **elicit business rules** about data use that aren't obvious from workflow analysis.
- Useful for communicating with IT technical staff such as a **database administrator**.
- **Primary and foreign keys are technically not part of a conceptual ERD** — there they
  are called **identifiers** — but are often included to simplify analysis and design.

## 3.3 — Key terms *(slides 5–6)*

| Term | Definition | Named as |
|---|---|---|
| **Entity** | Person, place, object, event, concept | **Singular nouns** (entity types = "classes") |
| **Relationship** | Association between entity *instances* | **Verb phrases** — has, includes, assigned, contains, belongs |
| **Attribute** | Properties or characteristics of an entity | **Nouns** |

Identifiers are shown **underlined** (slide 7).

### Weak vs. associative entity — the distinction to get right

These are **not** synonyms. The deck separates them by ERD layer:

| | **Weak entity** | **Associative entity** |
|---|---|---|
| Layer | **Conceptual** ERD | **Logical** ERD version of a weak entity |
| Defined by | Has **no primary key of its own**; depends on other entities' primary keys | Relationship converted to an entity because attributes emerge **only** from the association between two entities |
| Created when | Entity attributes are desired on a relationship | Same driver, logical layer |
| Physical name | — | **Intersection table** — converts M:N into two 1:M relationships for relational implementation |

> Say "associative entity" when working in the logical model and "weak entity" in the
> conceptual model. Casual summaries collapse these; the deck does not.

## 3.4 — ERD types *(slide 9)*

| Type | Scope | Notation |
|---|---|---|
| **Conceptual** | Core "essential" requirements or concepts | **Chen's** — relationships drawn explicitly as **diamonds** |
| **Logical** | Assumes a **relational database** architecture | **Crow's Foot** |
| **Physical** | Mapped to a real DBMS — Access, SQL Server, MySQL, Oracle | tool-specific |

**Analysts often skip past the conceptual ERD straight to the logical ERD.**

## 3.5 — Degree, cardinality, optionality *(slides 10, 23)*

**Relationship degree** = the number of entities involved in a relationship. **Most
relationships are binary.** The diamond symbol is often omitted; when used, it is labeled
with the relationship description ("has", "includes").

Cardinality asks **how many**. Optionality asks **is participation required**. Four
combinations:

| | Meaning |
|---|---|
| Mandatory one | exactly 1 |
| Mandatory many | 1 or more |
| Optional one | 0 or 1 |
| Optional many | 0 or more |

Crow's Foot symbols: `|` exactly one · `O` zero / optional · `<` many.
`DEPARTMENT ||──O< EMPLOYEE` = one department may have zero or many employees; each
employee belongs to exactly one department.

**M:N resolution** — an associative entity breaks one many-to-many into two
one-to-many relationships:

```
STUDENT 1 ──< ENROLLMENT >── 1 COURSE
             EnrollmentDate, Term, Grade, Status
```

The attributes belong to neither `STUDENT` nor `COURSE` — they exist only because a
particular student enrolled in a particular course. That is the tell.

Slides 15–17 cover EER notation for **attributes associated with a relationship**
(Figures 3-7, 3-8). Slide 17 asks directly: *what is the difference between the two, and
what additional options does the second give?* — likely lecture discussion, worth an answer.

## 3.6 — Supertype / subtype *(slides 18–21)*

**Not in the tutorial summary. It is in the deck, and it is exam-eligible.**

EER supertype ≡ class-diagram superclass. EER subtype ≡ subclass. Generalization and
specialization **minimize attribute redundancy**.

- **Generalization** — creates supertypes by moving *shared* subtype attributes up to a
  supertype.
- **Specialization** — creates subtypes by identifying attributes *specific* to a subtype.
- The subtype **inherits** attributes from its supertype.

Four characteristics, two independent pairs:

| Constraint | Meaning |
|---|---|
| **Total specialization** | Each supertype instance belongs to one of its subtypes |
| **Partial specialization** | A supertype instance can stand on its own |
| **Overlap** | A supertype instance can belong to **multiple** subtypes |
| **Disjoint** | A supertype instance belongs to **only one** subtype |

Deck examples:

- **Overlap** — `ADVERTISEMENT` can be both `ONLINE` and `RADIO` (Fig. 3-9, generalization).
- **Disjoint** — `EMPLOYEE` must be either `EXEMPT` or `NONEXEMPT`, never both at once
  (Fig. 3-10, specialization).

## 3.7 — Data flow diagrams *(slides 28–32)*

**Also absent from the tutorial summary.**

DFDs were invented in the **1970s**. They illustrate the **movement and transformation of
data** between entities, processes, and data stores.

> Sometimes called a process model but **should be classified as a data model.** A
> flowchart or activity diagram is the process model. A DFD shows only processes that
> **transform** data from inputs to different outputs.

**Properties (slide 29) — the exam traps live here:**

- DFD flow lines do **NOT** show sequence of tasks or activities.
- Think of flow lines as **"pipes"** through which bundles of data move as inputs/outputs.
- A bundle is a **data structure** of elements/fields — also called a *record* or *row*.
- Process → data store = a **write**. Data store → process = a **read**.
- Data elements in flows to/from a data store **must also be present in that data store**.

**Symbol sets (slide 30):** Yourdon-DeMarco (intended for **freehand**) vs. Gane-Sarson
(bundled with tools like **draw.io**, Dia, Visio). Yourdon-DeMarco is sometimes called
Yourdon-Coad.

| Level | Contains |
|---|---|
| **Context-level (Level-0)** | Describes system scope. A **single** process + external entities. **No data stores.** |
| **Level-1 (Diagram-0)** | External entities, main sub-processes of Process 0, primary data stores. Flows to/from external entities **must be identical** to the Context DFD. |

## 3.8 — Data dictionary *(slides 33–37)*

A data dictionary is a collection of data about data — **metadata** — describing data
structures and elements. DFD entities, data flows, and data stores are looked up in it
by name. Structures can nest (**composite** vs. **primitive** elements).

**Algebraic notation — memorize these five:**

| Symbol | Meaning |
|---|---|
| `=` | is composed of |
| `+` | and |
| `{ }` | repeating group of elements |
| `[ ]` | set of mutually exclusive elements |
| `( )` | optional elements |

Examples from the deck:

```
Customer   = CustomerID + CustomerName + Address + CustomerPhone
Address    = StreetAddress + City + State + ZipCode + (Country)     ← Country optional
Product    = ProductID + Description + ProductABC[A|B|C]            ← mutually exclusive
List of Goods Sold = ProductID + QuantitySold
Invoice    = InvoiceNumber + InvoiceDate + {InvoiceLine}            ← repeating group
InvoiceLine = Description + Quantity + UnitPrice + Amount
```

**Repeating groups occur in non-normalized user views** — forms, reports, screens.
Slide 37 gives the full invoice worked example.

## 3.9 — Data elements and COBOL PICTURE *(slides 38–40)*

**Entirely absent from the tutorial summary, and the professor is explicit: "In this
course, we'll use aspects of COBOL programming to define field size and format."** This
is instructor-added content not in the textbook — exactly the kind the syllabus warns
about.

COBOL uses the **PICTURE clause** to specify characteristics and editing requirements.

| PICTURE | Type | In | Out | Meaning |
|---|---|---|---|---|
| `AAAA` | Alpha (Text) | ✓ | ✓ | max 4 letters |
| `X(20)` | Alphanumeric | ✓ | ✓ | max 20 letters and numbers |
| `9(8)` | Numeric | ✓ | ✓ | max 8 integers, zero-filled |
| `11/03/2018` | Edited (Date) | — | ✓ | 8 numerics separated by slashes |
| `9(4)V99` | Numeric | ✓ | — | `V` = implied decimal point |
| `S9(4)V99` | Signed numeric | ✓ | — | as above, with sign |
| `Z,ZZ9.99-` | Numeric edited | — | ✓ | `Z` = **zero suppress** (zeros → spaces) |
| `$Z,ZZZ.99-` | Numeric edited (currency) | — | ✓ | with dollar sign |

**Three course simplifications to remember:**

1. Alpha and alphanumeric are combined into one **"Text"** type.
2. COBOL has no Date type — the course **mimics** one as an 8-integer number `YYYYMMDD`.
   November 3, 2018 → `20181103`.
3. COBOL has no Currency type — emulated as numeric with **2 decimal places** and a
   variable number of integer dollars.

Slide 40 is the worked table (Invoice Number, Invoice Date, Payment Terms, Unit Price,
Quantity, Amount, Tax Rate, Invoice Total) with input vs. output formats. Note the
recurring point: `(  )` and `%` **have no COBOL equivalent**.

## Running case

**Wayback Public Library** (slides 24–27) — four image slides. This is the deck's worked
case and doesn't survive text extraction. Open the deck.

---

## Open exercises — not yet answered

Two are outstanding from the tutorial session. Both are model-extraction, no drawing yet.

**A — Enrollment.** University has `COURSES` and `STUDENTS`; each student enrolls in many
courses, each course has many students; for every enrollment the university records
Enrollment Date, Final Grade, Enrollment Status.
→ *entities · relationship · cardinality · associative entity*

**B — Rugby club.** `PLAYERS` and `TEAMS`. A player may belong to multiple teams over
time; a team may have many players. The club records the date a player joined the team
and the player's position on that team.
→ *entities · relationship · cardinality · associative entity · its attributes*

**Status: awaiting the Commander's own reasoning.** Record attempts here, then the critique.

> Hint on B without giving it away: "over time" is doing work in that sentence. Ask what
> it implies about whether one associative-entity row per player-team pair is enough.
