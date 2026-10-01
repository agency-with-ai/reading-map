# Reading Map

Files and prompts for building a reading map from papers that bear on a project question. 

Open terminal inside your local copy of this repo and ask Claude to give you a sense of the repo structure. 
You can then skim through the folders. The [Feynman example](example/README.md) includes the specification example, and the end result an agent run produced (including source records, a reading map, etc.)

The prompts below are copiabel, and they help walk you through the individual steps. The [] brackets are placeholders for your own questions, observations, or record. You may also improvise with Claude.

## 1. Find and read sources

```text
Find candidate papers.
Question: [question]
Spec passage: [spec passage]
Save the question and spec passage in paper-sources/notes.md.
Return candidate titles, URLs, reasons for relevance, and access limits.
```

Take a look at the sweeping result, identify papers you'd read closely and ask Claude to keep a record:

```text
Prepare these papers: [titles or URLs].
Save accessible papers in paper-sources/papers/. If a paper cannot be
saved, record its URL and access limit.
Use paper-sources/TEMPLATE.md to create a source record for each paper.
Fill in bibliographic details and source-supported passages with locations
and limits. Link the records from paper-sources/notes.md.
```

Read the papers, including the passages your decision depends on.

```text
Record my reading observations in paper-sources/notes.md.
Paper: [title or source record]
Observations, questions, and uncertainties: [your notes]
```

## 2. Build and connect the pages

```text
Build the reading map from these source records: [paths].
Use the question and spec passage in paper-sources/notes.md.
Snapshot paper-sources/ in a new directory under evidence/ before building.
Create linked source pages and a comparison page under map/, starting
at map/index.md. Include passage locations, limits, a comparison table,
and a diagram connecting evidence to the project decision.
Run diff -ru between the snapshot and paper-sources/ after building.
Report the command, exit code, and any differences.
```

## 3. Check and query the reading map

Read the map and check its claims against the original passages.

```text
Record my checks in paper-sources/notes.md and correct the affected map pages.
Claims or connections: [claims]
Original passage locations: [locations]
My findings: [supported, corrected, or unresolved, with reasons]
```

Export the build conversation to `evidence/map-build.txt` using the application's export command. In Claude Code, use `/export`. Start a fresh session and use this prompt.

```text
Read CLAUDE.md. Use the saved reading map to answer [question],
starting at map/index.md. Do not browse or read the original papers.
Cite supporting pages and original passage locations, and state what
remains unresolved.
```

Check a claim in the answer against its original passage.

```text
Save the answer to map/answer.md and link it from map/index.md.
I checked [claims] against [passages and locations] and found [result].
Record my check in paper-sources/notes.md and update the affected map pages.
```

Export the query conversation to `evidence/map-query.txt`, then use this prompt.

```text
Link evidence/map-build.txt and evidence/map-query.txt from the saved
exchanges section of paper-sources/notes.md.
```

## 4. Make or revisit the decision

Decide what the evidence supports, or which question remains open.

```text
Record this decision in my spec at [path]: [decision or open question].
Supporting passages and limits: [evidence and differences from my setting]
Next check, if needed: [next check]
Record the reasoning and source links in the project decision section
of paper-sources/notes.md.
```
