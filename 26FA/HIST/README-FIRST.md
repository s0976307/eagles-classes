# HIST — transfer payload

Staged 2026-10-07 from `%USERPROFILE%\Desktop\EAGLES 2026\CLASSES 2026\HIST\` on the school machine.
Destination: `<Desktop>\EAGLES 2026\CLASSES 2026\HIST\` on the Beelink.

## Run order

```
1.  D:\HIST-TRANSFER\SETUP-HIST.ps1 -DryRun   then without -DryRun
```

Drive letter may differ on the Beelink. Run the script from the folder it sits in.

## What is here

This is HIS 110 C (Fall 2026) material for the Beelink. It is files only: no Claude memory and no MAE setup. Nothing from the MAE Bunker or CIS350A/MAT102A is included.

| File | What it is |
|---|---|
| `HIS 110 C Syllabus, Fall 2026.docx` | Course syllabus |
| `George W_ Bush ... Anna's Archive.epub` | James Mann, *George W. Bush* (EPUB) |
| `George W_ Bush ... Ann.mobi` | Same Bush book (MOBI, Kindle format) |
| `clinton.pdf` | Joe Klein, *The Natural: The Misunderstood Presidency of Bill Clinton* (PDF) |
| `Book Summary - Mann George W Bush.txt` | Study summary of the Mann book |
| `Book Summary - Klein The Natural Clinton.txt` | Study summary of the Klein book |
| `Test Sheet - George W Bush.txt` | One-page test aid, Bush |
| `Test Sheet - Bill Clinton.txt` | One-page test aid, Clinton |
| `Miller Center Summaries - Bush Clinton Truman Kennedy.txt` | Miller Center essay summaries, four presidents |
| `Miller Center Summaries - Obama Trump Biden.txt` | Miller Center essay summaries, three presidents |

## Notes

- The summaries and test sheets are paraphrased from the Miller Center essays and the books. They are not verbatim. Check specific dates and quotes against the originals before the test.
- Trump's "Life Before the Presidency" and Biden's "Life After the Presidency" are not included. Those pages returned HTTP 404 when fetched.
- The Miller Center "bush" page is George H. W. Bush (41st). The files here cover George W. Bush (43rd).
- Verification uses SHA256 (see `MANIFEST.sha256`), not timestamps. The drive is exFAT, so timestamps round to two seconds.
