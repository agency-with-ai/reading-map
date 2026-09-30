# Use the spec to build and check a wiki

Each Claude task below comes with a request to send. Fill in its bracketed fields first. Save each exchange in `evidence/` and keep your reading notes and checks in [paper-sources/notes.md](paper-sources/notes.md).

## 1. Find and read sources

Choose a requirement, assumption, or undecided choice in `spec.md`. The question can concern what to build or how to evaluate it. For example, [the writing-project spec](spec-example.md) leaves open both how to represent an author's style and how to compare passages. Start with one decision.

Send Claude this request with that passage and an explicit literature question.

```text
Read CLAUDE.md and spec.md.
The choice I want to investigate is [choice].
The relevant spec passage is [passage].
Find candidate papers that could help answer [question].
Return titles, URLs, reasons for relevance, and any access limits.
I will choose sources and check them. Do not change or download files.
```

Choose sources that could help answer it. You can start with one paper and add others as needed. If a paper is inaccessible, look for an accessible version or another relevant source. Record what you could not read.

Check that each paper exists. Copy [TEMPLATE.md](paper-sources/TEMPLATE.md) for each paper you choose, using a unique, descriptive filename such as `paper-sources/style-evaluation.md`. Leave the template unchanged. Fill each record with the title, URL, relevant passage, and its section or page number. Keep the original papers available, locally in `paper-sources/papers/` if useful.

These optional questions can guide a first pass through a paper's abstract, introduction, figures, and conclusion.

- Why should this problem be solved?
- What did the authors do, and how did they judge the result?
- How did earlier work approach the problem?
- What does this paper do differently?

An abstract may establish broad relevance. For the claim you will use in a project decision, read the supporting passage closely, including its assumptions, comparisons, and limits.

Save a copy of your completed source records before Claude builds the wiki. Run this once from the repository root. If the snapshot folder already exists, choose another unused name and use that name in the comparison command too.

```sh
mkdir evidence/sources-before-agent && cp -R paper-sources/. evidence/sources-before-agent/
```

## 2. Build and connect the pages

Send Claude this request with the paths to the completed source records you want to add. You can supply one or several.

```text
Read CLAUDE.md, spec.md, paper-sources/notes.md, and wiki/index.md.
My question is [question], about [spec passage].
Read these completed source records: [source-record paths].
For each record, create or update a page in wiki/ using the same filename.
Update wiki/question.md with what these sources support or leave open.
Keep unaffected text and recorded checks. Mark revised claims as unchecked
and flag conflicts with checked claims for review.
Update the index. Write only inside wiki/. Do not browse or install anything.
```

Each record gets a page in `wiki/` with the same filename, explaining what the authors did, what they found, and what their evidence does not establish. The question page connects the sources to your spec and records what remains unanswered.

Read the pages yourself in any Markdown viewer. GitHub and [Obsidian](https://obsidian.md) also draw the question page's diagram, and Obsidian shows the pages as a graph if you open the repository folder as a vault. Then compare the source records with your saved copy to check that Claude left them unchanged. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent paper-sources
```

## 3. Check and reuse the wiki

Check the claims and connections your decision depends on against the original passages. Compare them with any reading notes you made. For each check, ask these questions.

- Does the passage support the claim, including its qualifiers?
- What inputs, data, metric, baseline, or assumptions does the result depend on?
- Does the paper report this result, or is it an inference by Claude or by you?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct any errors you find. Record the passage location and whether each claim is supported, corrected, or unresolved in [your notes](paper-sources/notes.md#claim-checks). Leave unchecked claims marked as such.

When you want an answer from the saved wiki, send this request. You can use it in a new Claude session.

```text
Read CLAUDE.md and wiki/index.md.
Use the linked pages to answer [question].
Do not browse or change files.
Give the answer here for review.
```

Check the answer the same way before you use it.

If you want to keep the answer, save it as `wiki/answer.md` and mark unchecked claims and missing evidence. You can write it yourself or, after checking the answer, send this request in the same session.

```text
Save the answer as wiki/answer.md and link it from
wiki/index.md. I checked [claims] against [passages]
and found [result]. Mark every other claim as unchecked and list
the missing evidence. Update wiki/question.md to show the checks
recorded in paper-sources/notes.md. Write only inside wiki/.
```

## 4. Make or revisit a choice

Use the evidence you checked to choose or reconsider a benchmark, metric, baseline, method, or other part of your spec. A paper's use of a method establishes precedent under its conditions. It does not establish that the method will work for your project, so name where the paper's setting differs from yours.

Record the choice, reason, and supporting passages in your spec. You can keep the choice open and name the next check if the evidence does not settle it. If `spec.md` is a copy from another project folder, update that original and refresh the copy here.

You can repeat the workflow as new questions arise. Add source records as needed, name their paths in the request, and take a fresh snapshot before each build. Keep the wiki's index current and recheck any saved answer affected by new sources.
