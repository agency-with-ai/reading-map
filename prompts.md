# Requests for Claude

Fill in the bracketed fields before sending a request. Supply paths to completed source records, not `sources/TEMPLATE.md` or your reading notes.

## Find candidate papers

```text
Read CONVENTIONS.md and spec.md.
The choice I want to investigate is [choice].
The relevant spec passage is [passage].
Find candidate papers that could help answer [question].
Return titles, URLs, reasons for relevance, and any access limits.
I will choose sources and check them. Do not change or download files.
```

## Incorporate sources

```text
Read CONVENTIONS.md, spec.md, sources/notes.md, and wiki/index.md.
My question is [question], about [spec passage].
Read these completed source records: [source-record paths].
For each record, create or update a page in wiki/ using the same filename.
Explain what the authors did, what they found, and the limits of their evidence.
Update wiki/question.md with what these sources support or leave open.
Read existing wiki pages and their cited records as needed to connect the papers.
Keep unaffected text and recorded checks. Mark revised claims as unchecked
and flag conflicts with checked claims for review.
Distinguish the papers' findings, my notes, and your own inferences.
Link claims to the source records and original passage locations.
Update the index. Write only inside wiki/. Do not browse or install anything.
```

## Query the saved pages in a fresh session

```text
Read CONVENTIONS.md and wiki/index.md.
Use the linked pages to answer [question].
Cite the wiki pages and source passages that support each claim.
State what evidence is missing and what remains unresolved.
Do not browse, change files, or fill gaps from memory.
Give the answer here for review.
```

## Save the checked answer

Send this only after you have checked the answer.

```text
Save the answer as wiki/answer.md and link it from
wiki/index.md. I checked [claims] against [passages]
and found [result]. Mark every other claim as unchecked and list
the missing evidence. Write only inside wiki/.
```
