# Requests for Claude

Run these from the repository root. Fill in the bracketed question and spec passage before sending a request. Save exchanges in `evidence/`.

## Find candidate papers

```text
Read reading-wiki/CONVENTIONS.md and spec.md.
The choice I want to investigate is [choice].
The relevant spec passage is [passage].
Find candidate papers that could help answer [question].
Return titles, URLs, reasons for relevance, and any access limits.
I will choose two sources and check them. Do not change or download files.
```

## Incorporate the first source

```text
Read reading-wiki/CONVENTIONS.md and spec.md.
My question is [question], about [spec passage].
Read reading-wiki/sources/source-a.md.
Create reading-wiki/wiki/source-a.md with a short account of the source,
its evidence and limits, and how it bears on my question.
Link claims to the source record and original passage locations.
Add the page to reading-wiki/wiki/index.md.
Write only inside reading-wiki/wiki/. Do not browse or install anything.
```

## Connect the second source

```text
Read reading-wiki/CONVENTIONS.md, reading-wiki/sources/source-b.md,
reading-wiki/sources/notes.md, and the existing wiki pages.
Create reading-wiki/wiki/source-b.md and reading-wiki/wiki/question.md.
Connect both sources to my question [question] from spec.md.
Distinguish the papers' findings, my notes, and your own inferences.
Link to both source pages and record what the supplied passages cannot settle.
Update the index. Write only inside reading-wiki/wiki/. Do not browse.
```

## Query the saved pages in a fresh session

```text
Read reading-wiki/CONVENTIONS.md and reading-wiki/wiki/index.md.
Use the linked pages to answer [question].
Cite the wiki pages and source passages that support each claim.
State what evidence is missing and what remains unresolved.
Do not browse, change files, or fill gaps from memory.
Give the answer here for review.
```

## Save the checked answer

Send this only after you have checked the answer.

```text
Save the answer as reading-wiki/wiki/answer.md and link it from
reading-wiki/wiki/index.md. I checked [claims] against [passages]
and found [result]. Mark every other claim as unchecked and list
the missing evidence. Write only inside reading-wiki/wiki/.
```
