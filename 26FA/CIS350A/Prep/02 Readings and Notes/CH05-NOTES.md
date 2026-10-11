# Ch. 5 — Use Case Narratives and Functional Testing

Week 5–6 · **93 slides** — the largest deck in the course · revision `26FA-1`
**Exam #2** (Ch. 5, 6, 13, 14 — Sat 2026-11-07)
**Covers Assignment #7** (use case narrative, Nov 21) **and Assignment #9** (structured logic, Dec 12)

> **Provenance: SOURCE.** Extracted from
> `Systems Course Material\CIS350 Chapter 5 - Use Case Narratives.pptx` on 2026-10-05.
> Slide numbers cited. Figure/image slides (24–29, 60, 68–70, 75, 77, 83–86, 89–91, 93) are
> graphics — open the deck for Figures 5-1 through 5-14 and the decision-table worked examples.
> **This replaces the reported fragments in `CH05-CH14-STUB.md`.**

The deck title understates it. Five distinct blocks:

| Slides | Block |
|---|---|
| 2–33 | Use case narratives |
| 34–56 | Functional testing |
| 57–60 | Use case diagrams |
| 61–70 | Structured programming and Structured English |
| 71–93 | Business rules, decision trees, decision tables, DMN |

---

## 5.1 — Features vs. functional design *(slides 2–4)*

| | |
|---|---|
| **Feature requirements — the "what"** | **User stories** describe who/what/why of future-state capabilities **at a high level**. **Acceptance criteria** describe **variations and exceptions** in greater detail. |
| **Functional design — the nontechnical "how"** | **Logic model:** high-level business process logic = **activity diagrams**; detailed logic = **use case narratives**. **Data model:** ERD or class diagram. **User interfaces:** wireframes, mockups, prototypes, storyboards. |

> **Plan-driven ("waterfall")** separates the what and the how into **distinct analysis and
> design phases**. **Agile** has less distinct boundaries, merging them into **nearly
> simultaneous developer tasks** as detailed requirements **"emerge" during a build iteration.**

Timing (Fig. 5-1): user stories and ACs are **largely captured during business analysis and
refined thereafter**; use case narratives **expand on user stories during functional design and
are refined during development.**

Note "nontechnical **how**" — functional design is still the *how*, but not yet the technical
how. That's Ch. 13–14.

## 5.2 — What a use case narrative is *(slides 5–7)*

> A **use case** represents a **goal, purpose, feature, or function** of a software system.

**Origins — a clean matching pair:**

| Artifact | Came from |
|---|---|
| **Use case narratives** | **plan-driven** approaches |
| **User stories** | **agile** approaches |

> A **textual document** that articulates an integrated requirements description **more
> comprehensive than a user story**. Expands user stories with more detailed logic. **Links and
> integrates separate but interconnected perspectives** on requirements.

**Valuable when features are:** large or complex and cannot be further simplified ·
**interdependent** · **clear and stable**.

**Key elements (6):** written as a text document · focuses on **user–system interaction** ·
describes **how an actor achieves a goal with a system** · detailed interaction logic
**understandable to non-technical colleagues** · foundation for technical design, coding, and
testing · **"hub-and-spoke"** — can describe data inputs and informational outputs, the logic
transforming one into the other, supplemented with UI/UX models.

**Disadvantages (7):**

- Overly detailed scenarios become **unmanageable**.
- A single use case can contain multiple requirement components (data, process, business rules,
  external agents) **instead of documenting them separately**.
- **Individual requirement components should be defined separately and referred to by name.**
  This simplifies management, makes key requirements harder to overlook, and **enables reuse.**

## 5.3 — When to write one *(slides 8–10, 31)*

> **Good rule of thumb: include what's important AND not otherwise known or adequately
> communicated.** Follow **intelligent modeling** — devote effort to requirement information
> that is not already understood and not already adequately communicated.

**Three key factors (9)** — the more likely each is true, the more justifiable a detailed use
case: **requirement stability** · **requirement clarity** · **software development
interdependence**.

**Delivery team characteristics (10):**

| | Raises the need for use cases |
|---|---|
| Customer/stakeholder team | **Low** colocation and availability to IT · **many** stakeholder roles and variable business practices |
| IT team | Team size (**+**) · number of locations (**+**) · skill-set distribution (**+**) · **general level of capability (−)** |

> The capability sign is inverted on purpose: a **more capable** team needs **fewer** use cases.

**Avoid or create selectively when (31):** small amount of simple functionality · features are
**independent** and can be built in any order · requirements are **unclear** (may be impossible
to envision ahead — use prototypes instead) · requirements are **changing rapidly** (startups,
turbulent competitive environments).

## 5.4 — Linking user stories to use cases *(slides 11–14)*

**The mapping process (Fig. 5-6)** — worth memorizing as a sequence:

1. Identify key business processes as likely **epic** user stories.
2. Create an **activity diagram** for each business process, then identify individual features
   within it — classified **Existing** (not new scope) · **New** (new scope) · **Revised** (new scope).
3. Create user stories from each **new or revised** feature.
4. Identify and classify acceptance criteria:
   - **Functional ACs → become use case extensions**
   - **Nonfunctional ACs → do NOT map to use cases**
5. Create the narrative: **each base user story becomes a step in the MSS**; **each functional AC
   becomes an extension to the corresponding MSS step.**
6. **Prioritize each MSS step and extension using MoSCoW** (may reuse the base story's priorities).

### Four correspondence patterns *(12)*

| Pattern | When |
|---|---|
| **One-to-one** | Frequent — a story describing a single well-defined feature |
| **One-to-none** | **No use case needed, the story suffices.** Examples: **CRUD** operations, well-understood standard operations ("reset a password") |
| **One story → many use cases** | A high-level, complex story (13: the treasurer/FX example → ETL, summarization, historical reporting, projection modeling, future reporting) |
| **Many stories → one use case** | Multiple simple features integrated into the same interaction flow (14: the two pharmacist stories) |

## 5.5 — Sections of a fully dressed use case *(slides 17, 30)*

| Section | Contains |
|---|---|
| **Use Case Name** | Uniquely identifies the use case for reference |
| **User Story** | The story the use case details |
| **Stakeholders and Interests** | Users and other impacted or interested parties |
| **Related Models and Mock-ups** | Implements the **hub-and-spoke** requirements model |
| **Preconditions** | What must be true (or completed) for the functionality to work |
| **Trigger** | What causes the use case to start |
| **Minimal Guarantee** | Outcomes in the **worst-case** scenario |
| **Success Guarantee** | Outcomes after **successful** execution |
| **Main Success Scenario** | Basic flow / "happy path" |
| **Alternative Scenarios / Extensions** | MSS variations or exceptions |

> Slide 30: **"A use case doesn't have to include every element."**

**Three levels of detail (19):** **fully dressed** (the course's focus) · **casual** — a
paragraph or two · **brief** — as terse as a user story.

## 5.6 — MSS and extensions *(slide 18)* ★

**The core of the chapter.** *"The main value of a use case narrative is in the low-level logic
steps detailed by the MSS and extensions."*

**Main Success Scenario** — aka **basic flow** or **happy path**:

- The **simplest, most fundamental** version of the steps
- Represents a **complete start-to-finish** process
- **No variations (complications). No exceptions (errors).**
- **Each MSS corresponds to a base user story**
- **Loops ARE often included in the MSS**
- ⚠️ **Decisions are generally NOT included in the MSS.** In programming these are if/else or
  case logic — in use cases, variations and exceptions are handled **as extensions instead.**

**Extensions** — aka **alternative flows**. An extension is either a **variation
(complication)** of MSS logic or an **exception (error)** to it.

- **Each extension corresponds to a *functional* acceptance criterion**
- **Does NOT correspond to nonfunctional ACs** — *these don't change system behavior*

> **Loops in, decisions out** is the single most likely exam trap in this chapter.

### Use case slices *(23)*

Extensions expressed as **"use case slices"** specify **the order in which extensions should be
built — descending order of priority.** Each slice is the foundation for the next. Slices ensure
the most important ACs are done first and break work into pieces that fit sprints and assignments.

**Numbering:** if an extension modifies MSS step 2., the modified step is **2a.** (sub-steps
2a1., 2a2.). If another extension modifies 2a., it becomes **2b.** (sub-steps 2b1.).

### Goal levels, highest to lowest *(20)*

| Level | Scope |
|---|---|
| **Summary** | Extremely high-level, multiple user goals — often an entire business model of multiple processes/epics (WPL Add Item, Checkout, Check-in) |
| **User Goal** | How a user achieves a **specific goal**, typically multiple activity-diagram steps — often an entire business process/epic (the VFA example, WPL Checkout) |
| **Sub-Function** | A sub-goal that **may be included in several other use cases** — often a **single activity diagram step** (WPL fine calculation within Check-in) |

### Worked example — WPL fines *(21–23)*

Story **CHKIN6** (MH): *"As a librarian, I need the system to determine if an item was returned
after its due date and, if so, be able to store the fine for the loan transaction and update the
overall fines owed by the patron."* Its five ACs carry MoSCoW priorities — AC 6.1 basic formula
(**fine = item type fine per day × number of days late**) MH · 6.2 limit: not greater than item
cost MH · 6.3 limit: item > 10 years old SH · 6.4 automated update of patron's overall fines CH ·
6.5 logging of fine messages CH.

## 5.7 — Use cases deepen other models *(slides 32–33)*

The VFA six-entity ERD was built from the base story *"As an online store customer, I want to
place an order for items in my shopping cart so I can complete my purchase."* Working through the
ACs and extensions surfaced needs for **default values**, **changing the shipping address**, and
**selecting a different payment method** — which **added two entities**: `CUSTOMER PAY METHOD`
and `CUSTOMER SHIP ADDRESS`, both to store multiples.

> This is **triangulation** (Ch. 4 s34) demonstrated: the logic lens revealed a gap in the data
> lens. Good exam short-answer material.

---

# Functional testing *(slides 34–56)*

## 5.8 — Fundamentals *(34–35)*

> **Verify** that the system's behavior satisfies functional requirements.

Test plan → define which **test types** to include → assign IT or client member to each → define
**test cases** (does a requirement get met or not) → for each, detail **testing steps and the
desired outcome of each step**.

- **Plan-driven:** testing is a **distinct phase following construction.**
- **Agile:** testing occurs **as part of every build iteration.**

**The mapping chain — memorize it:**

```
Use case MSS / extension  →  at least one test case (often more)
Test case                 →  one test script
Use case step             →  test script step
Test script step          →  specific data input → specific data output
```

Example inputs/outputs: *"Item return date = 3/15/2025"* → *"Fine amount calculated to be $1.71."*

**Test data must be created for all involved data model entities**, and **re-running a failed
test may require refreshing it** — you can't check in the same Loan transaction twice without
resetting.

## 5.9 — Software environments *(36–37)*

Minimum two — **Test** and **Production (Live)**. More commonly **three**:

| Environment | Also called | Purpose | Testing done there |
|---|---|---|---|
| **Development** | Dev, **trunk** | New programs created, or copied from the repository into developer-only space | **Unit testing** by developers at program, class, method level |
| **Test / QA** | quality assurance | **Integration** environment where developers merge changes | **Integration** (code works together) · **Regression** (existing features unchanged) · **System** (features meet functional requirements) |
| **Stage / UAT** | user acceptance testing | **Production-like** environment | **UAT** |

A developer may use a **"working copy" or "sandbox"** locally — the whole environment with
**Git**, or just needed files with **Subversion**. Release to Live checks code back into the
repository; a **version control system** keeps history so you can drop back to an earlier release.

## 5.10 — Testing phases *(38–39)*

**Alpha testing** is conducted by the **delivery team**, typically unit through system testing:

| Phase | Validates |
|---|---|
| **Unit** | Functional specifications for individual programs, by the developer (TDD) |
| **Integration** | Technical requirements — related groups of programs as a subsystem |
| **System** | **Functional AND non-functional** requirements — performance, stress, security testing |
| **Regression** | Software changes caused **no unexpected side-effects** in unchanged parts |
| **UAT** | Users validate their business requirements |
| **Beta** | Conducted by **users outside the delivery team**; usually the **final phase of UAT**, as close to Live as possible |
| **Post-implementation user assessment** | Final validation **after the software has been in use for some time** |

> ⚠️ **"Business stakeholders should perform UAT, not the BA or developers."** Stated flatly.

## 5.11 — TDD vs. BDD vs. FDD *(40–41, 46)*

| | |
|---|---|
| **TDD** — Test Driven Development | Create test cases **before** the software is fully developed. Programmer writes the test **before** the program. |
| **BDD** — Behavior Driven Development | Specify tests based on the **desired behavior** of the software unit |
| **FDD** — Feature Driven Development | **Not a testing scheme** — an agile **methodology** for developing feature by feature. OO development using **sequence and class diagrams.** |

> **TDD is not a substitute for objective SQA testers** — *cf. confirmation bias.* The BA might
> do double duty as SQA tester, and **should articulate business requirements so they are
> testable or verifiable.**

**Two different approaches (46):** the BRUF route is **use cases → test cases → test scripts**,
widely used in large complex projects. **TDD is quite different — there the test cases ARE the
requirements**, and may precede detailed requirements that emerge during sprints. Makes sense
when project characteristics point to a highly agile approach.

**Gherkin / Cucumber (42)** — identical to Ch. 4 slide 13. `Given / When / Then`.

## 5.12 — Test data, coordination, automation *(43–48, 50–56)*

> **Creating test data "is an art, not a science."**

- Key is data that **fits each test case scenario**; some (e.g. Item Type) is **reusable**.
- **Artificial values** may facilitate testing — e.g. Loan Duration in **days, not weeks**.
- **Meaningful names** help testers pick relevant data — *"Riley Overduepatron," "Alex Earlypatron."*
- **Resetting** is typically required after a failed script.

**Why test twice (44–45):** IT testers are **less familiar with expected outcomes than clients**,
so clients catch problems IT misses. **UAT is more production-like than QA**, so a test passing in
QA may fail in UAT. IT's cases and scripts can be **reused by the client**, freeing client time
for cases IT missed.

**IT support of UAT (47):** copy data from Production, **anonymize by encrypting and removing
("masking" or "redacting") sensitive data**, refresh for reruns.

**Conference room pilot (49):** used for acceptance testing or comparing **COTS** packages, and
adaptable to a requirements review — a documents-only **script read-through**, like actors reading
a screenplay around a table. A full CRP with workstations validates **end-to-end processes
spanning departments** (e.g. "Place Purchase Order" → "Pay Vendor"), **usually not individual
requirements**.

**Test case labeling (52):** uses the **slice number and corresponding AC number**; order starts
with the MSS then proceeds in slice order. Each slice needs at least one case, often several —
late, early, and on-time check-ins.

---

# Use case diagrams *(slides 57–60)*

> A UML diagram giving a **summary view** of a system's use cases, their relationships, and
> actors. Represents the **functional requirements of the interaction** between a system and its
> actors. Often used by the BA to **show the scope** of a project or business area. **Catalogs**
> a system's use cases.
>
> ⚠️ **NOT intended for decomposition or internal logic specification.**

**How to draw one (59):**

1. Draw and name the **system scope boundary rectangle**.
2. Identify use cases and draw them **inside** the boundary. Describe with **verb + noun** —
   "Place Order."
3. Identify **actors** along the **outside perimeter**. Name by **role with respect to the system**.
   - ⚠️ **User ≠ actor.** One user could comprise multiple actors/roles.
   - **Primary actor initiates** the system action — usually on the **left**.
   - **Secondary/supporting actor responds** to system actions — usually on the **right**.
4. Connect actors to use cases with relationship lines.
5. Connect two use cases with `<<include>>` or `<<extend>>`.

| Relationship | Meaning | Arrow points to |
|---|---|---|
| `<<include>>` | **Always executes** the related use case | the use case being **included** |
| `<<extend>>` | **Optional** use case — think decision or error path | the use case being **extended** |

> `Study Guide - Use Case Diagrams.pdf` is in the materials folder, still unextracted. A#7 is
> due Sat 2026-11-21.

---

# Structured programming and Structured English *(slides 61–70)*

**Covers Assignment #9 — structured logic, Sat 2026-12-12.**

## 5.13 — Structured programming *(61)*

**Top-down design** — also known as **functional decomposition** or **stepwise refinement**.

**Modularization:**

- **Cohesion should be STRONG** — every statement in a module relates to a common task, and
  **that common task should be the name of the module.**
- **Coupling should be WEAK** — minimize side-effects between modules.

> Same pair as Ch. 1 slide 31. Second appearance, different chapter.

**Structured logic — four constructs:** **Sequence · Selection · Iteration · Case (multipath
selection)**. Build logic incrementally by connecting blocks with **one path in and one path out
of a block.**

## 5.14 — Structured English *(62)*

| | Describes |
|---|---|
| **Structured English** | a **business activity or business rule** in words |
| **Pseudocode** | **program logic** in words |

**No standard format for either.** The logic model covers **process logic** (sequence of tasks
within a process) · **task/activity logic** (sequence of steps within a task) · **business rules**
(constraint or formula).

> Restating a business activity narrative elicited from stakeholders **can reveal hidden
> assumptions on the part of both the analyst and the SME.** Unstated assumptions will eventually
> surface when a developer must translate them into working software — **but the result will be
> delay and possibly costly redesign.**

## 5.15 — The four coding structures *(63–66)*

**Sequence** — group related actions, label them, execute with `DO` as a subroutine equivalent:

```
DO MyProcedure              PROCEDURE MyProcedure
                               Action 1
                               Action 2
                               Action 3
                            END
```

> Structured English and pseudocode are **identical**, though **subroutines in Structured English
> are unusual. Keep Structured English at a high level for business stakeholders — don't force
> them to read pages of text when a diagram might be clearer.**

**Selection** — one-sided and two-sided:

```
IF Condition is true THEN        IF Condition is true THEN
   Action 1                         Action 1
ENDIF                            ELSE
                                    Action 2
                                 ENDIF
```

**Iteration** — note which tests where:

```
Condition tested BEFORE action      Condition tested AFTER action
FOR EACH item                       DO WHILE True        DO UNTIL True
    Action 1                           Action 1             Action 1
ENDFOR                              ENDDO                ENDUNTIL/ENDDO
(Structured English)                (Pseudocode)
```

**Case (multipath selection)** — the deck gives **three** accepted Structured English versions:

```
WHEN Condition                 CASE OF Condition              SELECT Condition
   IS Value 1 THEN Action 1       WHEN Value 1 Action 1          WHEN Value 1 Action 1
   IS Value 2 THEN Action 2       WHEN Value 2 Action 2          WHEN Value 2 Action 2
   IS OTHER THEN Default          WHEN OTHER Default Action      WHEN OTHER Default Action
ENDWHEN                        ENDCASE                        ENDSELECT
```

## 5.16 — Alternative flowchart notation *(67–70)*

Standard **ANSI** notation labels a **large diamond** with the condition being tested. The
**alternative**: define an **activity describing the decision**, then connect it to a **smaller
diamond used as a "gate"** to multiple paths.

- The decision task is still labeled **verb + noun** — *"Evaluate …", "Decide …", "Determine …"*
- Decision paths are **terminated or merged with a second, unlabeled diamond.**

> That unlabeled merge diamond is the same symbol Assignment #1 asks about.

---

# Business rules and decision models *(slides 71–93)*

## 5.17 — Business rules *(71)*

Two kinds:

| Kind | Example | As logic |
|---|---|---|
| **Constraint or condition** | Orders over $75 ship for free | `IF Order Amount > $75 THEN Shipping Charges = 0 ENDIF` |
| **Formula or calculation** | Gross pay is the product of hours worked and pay rate | `Gross Pay = Hours Worked * Pay Rate` |

Business rules can also be illustrated with **decision trees and decision tables.**

## 5.18 — Decisions *(72)*

> A **decision derives a result (output) from given facts (input) using decision logic (rules).**

Three decision models: **decision tree** · **traditional decision table** · **DMN decision table**.

## 5.19 — Decision trees *(73–75)*

Used when **complex branching occurs in a structured decision process**; useful when it is
essential to **keep a string of decisions in a particular sequence**. Widely used for
**troubleshooting, diagnostics, and machine learning**.

**Advantages:** the **order** of checking conditions and executing actions is immediately
noticeable · conditions and actions are found **on some branches but not others** · **more
readily understood** by others in the organization than decision tables.

**Drawing (74):** identify all conditions and actions **and their order and timing** → build
**left to right**, listing **all possible alternatives before moving right**.

**Three symbols:** **decision node** (a decision to be made) · **chance node** (multiple
**probabilistic** outcomes) · **endpoint node** (final outcome of a path). **Not all symbols have
to be used in a single tree.**

## 5.20 — Decision tables *(76–87)*

> A logic model that **formalizes the rules by which a decision is made.** Used to verify
> **"completeness"** — all possible condition paths are considered.

**Structure — four parts:** **condition stub** · **condition entries** · **action stub** ·
**action entries**.

**Nine development steps (78):**

1. List the conditions
2. List the actions
3. List the condition entries
4. **Calculate the number of decision rules (columns)**
5. Fill in the condition entries
6. Fill in the action entries
7. Simplify the table
8. Inspect for **impossible situations, contradictions, redundancies**
9. Rearrange conditions, actions, or rules to clarify

> **Number of rules = multiply the number of alternatives for each condition across all
> conditions.** Two binary conditions → 4 columns; three → 8. Expect to compute this.

**Three defects (79):**

| Defect | Means |
|---|---|
| **Impossible situation** | Two conditions cannot be true at once — usually a **misstatement of conditions**, e.g. mixing annual and monthly salary |
| **Contradiction** | Same set of condition values yields a **different** set of actions. Can result from **over-simplifying** — too many indifferent conditions |
| **Redundancy** | One rule is the **same** as another — same conditions, same actions |

**Decision table → CASE logic (87):** `"ANY"` indicates an **indifferent condition**.

```
WHEN Student AND Seat Available AND Approved Training
     IS "Y" AND "Y" AND "Y" THEN Confirm registration
     IS "Y" AND "Y" AND "N" THEN Deny registration
     IS "Y" AND "N" AND ANY THEN Deny registration
     IS "N" AND ANY AND ANY THEN Deny registration
ENDWHEN
```

> *"The developer would translate the specifications into the most appropriate and efficient
> version for the computing environment. The business analyst writes requirements with a
> different purpose and audience in mind."*

## 5.21 — DMN *(88–93)*

**Decision Model and Notation.** Decision logic *can* be modeled as a chain of gateways in
activity or BPMN diagrams, **but this is usually not a good idea** because:

- Not all relevant items that go into decision-making are modeled — e.g. **data elements**
- The process model becomes **more complex and difficult to maintain**
- A series of gateways **implies a particular order** of decision-making
- **Activity diagrams model process logic, not task logic, while DMN models the data and internal
  logic of a decision**

**Decision Requirements Diagram (DRD)** shows **all the inputs that go into a decision**, and can
link one decision's output as another decision's input.

**DMN decision table (92–93)** — rule processing is more flexible than traditional tables via a
**"hit policy"**:

| Policy | Meaning |
|---|---|
| **U**nique | Exactly one rule can match per condition set |
| **F**irst | First rule that matches is selected |
| **P**riority | Matching rule with **highest priority** is selected |
| **C**ollect | **Accumulates** the (usually numeric) results of all matching rules |

> ⚠️ **In DMN, conditions and actions are in COLUMNS and rules are in ROWS — the reverse of
> traditional decision tables.** Stated explicitly on slide 93. Near-certain exam item.

---

## Core card

| Concept | Remember |
|---|---|
| Use case narrative vs. user story | Narrative = plan-driven origin, detailed interaction logic · Story = agile origin, high-level who/what/why |
| MSS | Simplest complete path, no variations, no exceptions. **Loops in, decisions out.** Corresponds to a base user story |
| Extension | Variation **or** exception. Corresponds to a **functional** AC only |
| Nonfunctional ACs | Do **not** map to use cases — they don't change system behavior |
| Use case slices | Build order, descending priority. Numbering 2a., 2a1., then 2b. |
| Goal levels | Summary > User Goal > Sub-Function |
| One-to-none | CRUD and standard operations need no use case |
| Environments | Dev (unit) → Test/QA (integration, regression, system) → Stage/UAT (UAT) |
| Alpha vs. beta | Alpha = delivery team · Beta = users outside it, final phase of UAT |
| Who does UAT | **Business stakeholders — not the BA or developers** |
| TDD / BDD / FDD | Test-first / behavior-specified / **not a testing scheme at all** |
| `<<include>>` vs `<<extend>>` | Always executes vs. optional; arrow points at the included/extended case |
| User ≠ actor | One user can be several actors |
| Cohesion / coupling | Strong / weak |
| Structured English vs. pseudocode | Business activity or rule / program logic |
| Decision rule count | Multiply alternatives across all conditions |
| Table defects | Impossible · contradiction · redundancy |
| DMN orientation | Conditions and actions in **columns**, rules in **rows** — reversed |
