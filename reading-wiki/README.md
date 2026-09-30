# Use the spec to build and check a wiki

Work from the repository root with your project spec in `spec.md`. [prompts.md](prompts.md) has a request for each Claude task below. Save each exchange in `evidence/` and keep your reading notes and checks in [sources/notes.md](sources/notes.md).

## 1. Find and read sources

Choose a requirement, assumption, or undecided choice in `spec.md`. The question can concern what to build or how to evaluate it. For example, [the writing-project spec](../spec-example.md) leaves open both how to represent an author's style and how to compare passages. Start with one decision.

Send Claude the [find request](prompts.md#find-candidate-papers) with that passage and an explicit literature question. Start with two relevant sources. If a paper is inaccessible, look for an accessible version or another relevant source. Record what you could not read.

Check that each paper exists and fill in [source-a.md](sources/source-a.md) and [source-b.md](sources/source-b.md). Save the title, URL, relevant passage, and its section or page number. Keep the original papers available, locally in `reading-wiki/sources/papers/` if useful. Put your own notes in [notes.md](sources/notes.md), clearly labelled as yours.

Before asking Claude to summarize the sources, skim each paper's abstract, introduction, figures, and conclusion yourself. Record brief answers in your notes and mark gaps rather than guessing.

- Why should this problem be solved?
- What did the authors do, and how did they judge the result?
- How did earlier work approach the problem?
- What does this paper do differently?

An abstract may establish broad relevance. For the claim you will use in a project decision, read the supporting passage closely, including its assumptions, comparisons, and limits.

Save a copy of your completed source records before Claude builds the wiki. Run this once from the repository root. If the snapshot folder already exists, choose another unused name and use that name in the comparison command too.

```sh
mkdir evidence/sources-before-agent && cp -R reading-wiki/sources/. evidence/sources-before-agent/
```

## 2. Build and connect the pages

Send Claude the [first-source request](prompts.md#incorporate-the-first-source), then the [second-source request](prompts.md#connect-the-second-source). Each source page should explain what the authors did, what they found, and what their evidence does not establish. The second request also creates a question page that connects both papers to your spec.

Read the pages yourself. Then compare the source records with your saved copy to check that Claude left them unchanged. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent reading-wiki/sources
```

## 3. Check and reuse the wiki

Compare the pages with your reading notes. Check one factual claim against its exact passage, and follow one claimed connection back to both original papers. For each, answer these questions.

- Does the passage support the claim, including its qualifiers?
- What inputs, data, metric, baseline, or assumptions does the result depend on?
- Does the paper report this result, or is it an inference by Claude or by you?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct an error or record why the claim is supported. Record the passage location and whether the claim is supported, corrected, or unresolved in [your notes](sources/notes.md#claim-checks).

Start a fresh Claude session and send the [saved-page query](prompts.md#query-the-saved-pages-in-a-fresh-session). Save the answer and any available file-read record. A fresh conversation alone does not show that Claude used the wiki.

Follow one answer claim through a wiki page to the original passage. Then save the checked answer as `reading-wiki/wiki/answer.md`, yourself or with the [save request](prompts.md#save-the-checked-answer). Mark unchecked claims and missing evidence.

## 4. Make or revisit a choice

Use the checked answer to choose or reconsider a benchmark, metric, baseline, method, or other part of your spec. A paper's use of a method establishes precedent under its conditions. It does not establish that the method will work for your project, so name where the paper's setting differs from yours.

Record the choice, reason, and supporting passages in your spec. You can keep the choice open and name the next check if the evidence does not settle it. If `spec.md` is a copy from another project folder, update that original and refresh the copy here.

You can repeat the workflow as new questions arise. Add source records as needed, adapt the prompts to name them, and take a fresh snapshot before each build. Keep the wiki's index and checked answer consistent with the sources you have added.
