# Reading Map

Files and prompts for the reading map in [Lab 3, Step 4](https://agencyai.mit.edu/lab3/#step-4-put-the-spec-to-work). Follow the lab page for the assignment, reading and checking requirements, partner exchange, and checkoffs.

## Set up

Claude's instructions are in [CLAUDE.md](CLAUDE.md). Fill in the brackets in the prompts below.

[The Feynman example](example/project-spec.md) shows a project spec with open literature questions. Its source records in `example/paper-sources/` are unchecked drafts, and its reading notes are incomplete.

## 1. Find and read sources

Record your question and spec passage in [your notes](paper-sources/notes.md#question-from-my-spec).

```text
Find candidate papers.
Question: [question]
Spec passage: [spec passage]
```

Save papers in `paper-sources/papers/` or record their URLs. Put your reading observations in [your reading notes](paper-sources/notes.md#reading-notes). For each paper, copy [the source template](paper-sources/TEMPLATE.md) to a descriptive filename in `paper-sources/` and fill it in.

## 2. Build and connect the pages

```text
Build the reading map.
Question: [question]
Spec passage: [spec passage]
Source records: [paths]
```

The generated pages start at [map/index.md](map/index.md). Each paper gets a source page; `map/question.md` compares the evidence for your question.

Before building, Claude copies your source records into `evidence/`. Run the `diff` command it gives you. No output means the records match the snapshot.

## 3. Check and query the reading map

Record the checks required by the lab in [your claim checks](paper-sources/notes.md#claim-checks). Include original passage locations and any corrections to the reading map.

Export the build conversation to `evidence/` using [these instructions](evidence/README.md). Use this prompt in the lab's fresh-session query.

```text
Read CLAUDE.md. Use the saved reading map to answer [question],
starting at map/index.md. Do not browse or read the original papers.
```

After recording your answer check in `paper-sources/notes.md`, ask Claude to save it.

```text
Save the answer. I checked [claims] against [passages]
and found [result].
```

Claude writes `map/answer.md` and links it from the index. Export the query conversation separately and link both exports from your notes.

## 4. Make or revisit the decision

Put the decision in your spec and its supporting passages and limits in [your notes](paper-sources/notes.md#project-decision).

Return to [Lab 3](https://agencyai.mit.edu/lab3/#step-4-put-the-spec-to-work) for the partner exchange and Checkoff 2.
