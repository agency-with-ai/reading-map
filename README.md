# Reading Map

A starter for building and checking a literature wiki around a question from your project spec. Connect papers to a project decision, check the evidence, and keep unanswered questions visible.

## Start

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Put your project spec in `spec.md`. If you keep it in another project folder, copy it here. See [Write like a professor (2026)](spec-example.md) for an example.

Use only project material you may share with Claude and anyone reviewing your work, and keep your copy local or in a private repository. Open the clone in a Claude session that can read and edit local files and search the web.

Fill in the bracketed fields before sending each request to Claude. [CLAUDE.md](CLAUDE.md) defines how Claude handles each task. Save exchanges as described in [evidence/README.md](evidence/README.md), and keep reading notes and checks in [paper-sources/notes.md](paper-sources/notes.md).

## 1. Find and read sources

Choose one requirement, assumption, or open decision in `spec.md`. For example, [the writing-project spec](spec-example.md) leaves open how to represent an author's style and how to compare passages.

Ask Claude to find relevant papers.

```text
Read CLAUDE.md.
The choice I want to investigate is [choice].
The relevant spec passage is [passage].
Find candidate papers that could help answer [question].
```

Choose one or more papers. If a paper is inaccessible, look for an accessible version or another source. Record what you could not read.

Open each paper and fill in a copy of [TEMPLATE.md](paper-sources/TEMPLATE.md). Use a unique, descriptive filename such as `paper-sources/style-evaluation.md`, and leave the template unchanged. Keep the original papers available, locally in `paper-sources/papers/` if useful.

For a first pass, read the abstract, introduction, figures, and conclusion. These questions can guide your reading.

- Why should this problem be solved?
- What did the authors do, and how did they judge the result?
- How did earlier work approach the problem?
- What does this paper do differently?

An abstract may establish broad relevance. For the claim you will use in a project decision, read the supporting passage closely, including its assumptions, comparisons, and limits.

Before each build, save a copy of your source records from the repository root. If the snapshot folder exists, use an unused name here and in the comparison command below.

```sh
mkdir evidence/sources-before-agent && cp -R paper-sources/. evidence/sources-before-agent/
```

## 2. Build and connect the pages

Give Claude the paths to the completed source records you want to add.

```text
Read CLAUDE.md.
My question is [question], about [spec passage].
Build or update the wiki from these completed source records:
[source-record paths].
```

Read the pages in a Markdown viewer. GitHub and [Obsidian](https://obsidian.md) render the question page's diagram. Obsidian can also show the page links as a graph when you open the repository as a vault.

Compare the source records with your saved copy. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent paper-sources
```

## 3. Check and reuse the wiki

Check the claims and connections your decision depends on against the original passages and your reading notes.

- Does the passage support the claim, including its qualifiers?
- What inputs, data, metric, baseline, or assumptions does the result depend on?
- Does the paper report this result, or is it an inference by Claude or by you?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct any errors you find. Record the passage location and whether each claim is supported, corrected, or unresolved in [your notes](paper-sources/notes.md#claim-checks). Leave unchecked claims marked as such.

Ask Claude to answer from the saved wiki, in this session or a new one.

```text
Read CLAUDE.md.
Use the saved wiki to answer [question].
```

Check the answer before using it. To keep it, write `wiki/answer.md` with unchecked claims and missing evidence marked, or send this request in the same session.

```text
Read CLAUDE.md.
Save the answer. I checked [claims] against [passages]
and found [result].
```

## 4. Make or revisit a choice

Use the evidence you checked to choose or reconsider a benchmark, metric, baseline, or method. Name where the paper's setting differs from yours. Its results may not hold under your project's conditions.

Record the choice, reason, and supporting passages in your spec. You can keep the choice open and name the next check if the evidence does not settle it. If `spec.md` is a copy from another project folder, update that original and refresh the copy here.

Repeat as new questions arise. Recheck any saved answer affected by new sources.
