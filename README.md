# Reading Map

Files and prompts for building a reading map from papers that bear on a project question.

Open a terminal inside your local copy of this repo and ask Claude to give you a sense of the repo structure.
You can then skim through the folders. The [Feynman example](example/README.md) includes the specification example, and the end result an agent run produced (including source records, a reading map, etc.).

The prompts below are copyable, and they help walk you through the individual steps. The [] brackets are placeholders for your own questions, observations, or records. You may also improvise with Claude.

## 1. Find and read sources

```text
Find candidate papers.
Question: [question]
Spec passage: [spec passage]
Spec path: [path to your spec file]
```

Take a look at the sweeping result, identify papers you'd read closely and ask Claude to keep a record:

```text
Prepare papers [numbers or titles] from your candidate list.
```

Read the papers, including the passages your decision depends on.

## 2. Build and connect the pages

```text
Here are my reading notes: [notes, identifying the paper each concerns].
Save them and build the reading map from the source records you prepared.
```

## 3. Check and query the reading map

Open [map/index.md](map/index.md) and follow its links to the source summaries and evidence comparison. Check their claims against the cited passages in the original papers.

```text
Record my checks in paper-sources/notes.md and correct the affected map pages.
Claims or connections: [claims]
Original passage locations: [locations]
My findings: [supported, corrected, or unresolved, with reasons]
```

Export the build conversation to `evidence/map-build.txt` using the application's export command. In Claude Code, use `/export`. Start a fresh session and use this prompt.

```text
This is a new session, separate from the one that built the map.
Read CLAUDE.md. Answer the project question recorded in
paper-sources/notes.md using the saved reading map, starting at map/index.md.
Do not browse or read the original papers.
```

Check a claim in the answer against its original passage.

```text
Save the answer to map/answer.md and link it from map/index.md.
I checked [claims] against [passages and locations] and found [result].
Record my check in paper-sources/notes.md and update the affected map pages.
```

Export the query conversation to `evidence/map-query.txt`.

## 4. Make or revisit the decision

Decide what the evidence supports, or which question remains open.

```text
Record this decision in my spec and notes: [decision or open question].
Use the reading map for supporting passages, limits, and any next check.
```
