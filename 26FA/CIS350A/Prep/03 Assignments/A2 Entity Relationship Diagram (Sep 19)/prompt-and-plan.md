# Assignment #2 — Introduction to the Entity Relationship Diagram
Due: Sat 19 Sep 2026, 23:59 — **PAST. As of 2026-10-05 that is 16 days.**
At the syllabus's stated −10%/day this is past full value, so the grade now depends on an
extension, not on speed. Extensions are granted on request per syllabus. **Email Prof.
Inomoto before finishing this** — confirm the real date in Canvas while you're at it.

File name: `Assignment-2-<Lastname><Firstinitial>.docx` (e.g. `Assignment-2-SmithJ`).
Your name must appear inside the document.

## Canvas prompt (verbatim, pages 1–2 as supplied)

> Submit your answers to the following exercises as a Word document. Name your document
> "Assignment-2-LastnameFirstinitial," for example "Assignment-2-SmithJ." Include your name
> in the document.
>
> Use Figure 3-11 (p. 88) to answer the following questions:
>
> 1. Which attribute is used to identify each individual instance of STORE separately?
> 2. What is the cardinality of the relationship between EMPLOYEE and STORE?
> 3. How many stores can an employee manage, i.e., name its optionality?
> 4. Why do the employee subtypes PT (Part Time) and FT (Full Time) have a disjoint
>    constraint (as indicated by the "d") relative to supertype EMPLOYEE?
> 5. What type of entity is LINE ITEM?
> 6. What is the meaning of the optionality symbol (crow's foot + 0) on the left end of the
>    relationship between LINE ITEM and PRODUCT? Describe the relationship in a sentence.
> 7. What is the meaning of the optionality (double bar) symbol on the right side of the
>    relationship between LINE ITEM and PRODUCT? Describe the relationship in a sentence.
> 8. What relationship degree is diagrammed at the lower right of PRODUCT?
> 9. What type of attribute is PRODUCT.Product Ingredient?
> 10. What type of attribute is PRODUCT.Target GPM?
>
> For Questions 6 and 7, your description should resemble the following descriptions for the
> relationship between SALE and CUSTOMER.
>
> SALE -> CUSTOMER: Each Sale is sold to one-and-only-one Customer.
> CUSTOMER -> SALE: Each Customer can have zero-to-many Sales.
>
> Figure 3-11 is included on the following page.

## Rubric

None published in the prompt. 10 points, 10 questions — assume 1 point each.

## Deliverables

- [ ] One Word `.docx`, named per the convention above
- [ ] Your name inside the document
- [ ] Ten numbered answers
- [ ] Q6 and Q7 each include a **full sentence** in the SALE/CUSTOMER style — not just the
      symbol's name
- [ ] Copy dropped into `06 Submitted/`

**No diagram is required.** Nothing here asks you to draw. `04 Diagrams/` stays untouched
for this one — this is a notation-reading exercise, not a modeling exercise.

## Blocking gap

**Figure 3-11 (p. 88) is not in this workspace and was not in the pasted prompt.**
Open the textbook in Canvas → Course Materials → Spurrier & Topi, 2nd ed., p. 88.
The reproduction inside the assignment PDF is likely too small to read — the same problem
hit A1. Use the book.

Until the figure is in front of you, questions 1, 2, 3, 5, 6, 7, 8, 9, 10 are unanswerable.
Only Q4 is answerable from Ch. 3 theory alone.

## Ambiguities to resolve

- **Q2 "the relationship between EMPLOYEE and STORE"** — Figure 3-11 may show **two**
  relationships between these entities (a *works at* and a *manages*), because Q3 asks
  separately about managing. Check whether there are two lines. If there are, say which
  one you are describing and consider covering both.
- **Q5 "what type of entity"** — depends on whether Figure 3-11 is drawn as a *conceptual*
  or *logical* ERD. The deck (CH03-NOTES.md §3.3) insists these get different names for
  the same idea. See the scaffold.
- **Q6/Q7 left/right** — you must confirm which entity sits on the left of the figure
  before you can write the sentences. Do not assume LINE ITEM is on the left.
- **"Target GPM"** — gross profit margin. Ask yourself whether the figure shows it being
  *stored* or *computed from other attributes*. That is the whole question.

## Analysis — the eight questions

Not applicable in the usual way. This assignment is comprehension of a supplied model, not
elicitation of a new one. The framework returns for Assignment #6 (Nov 07), which is a
build-an-ERD assignment.

## Self-check before submitting

- [ ] Every one of the 10 has an answer — no blanks
- [ ] Q6 and Q7 are sentences, in the professor's stated format
- [ ] I can point at the exact symbol in Figure 3-11 that justifies each answer
- [ ] I can explain every answer out loud without notes
- [ ] Name, course, assignment number on the document
- [ ] Filename matches `Assignment-2-<Lastname><Firstinitial>.docx`
- [ ] Copy saved to `06 Submitted/`
