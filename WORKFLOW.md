# Use the spec to build and check a wiki

[prompts.md](prompts.md) has a request for each Claude task below. Save each exchange in `evidence/` and keep your reading notes and checks in [sources/notes.md](sources/notes.md).

## 1. Find and read sources

Choose a requirement, assumption, or undecided choice in `spec.md`. The question can concern what to build or how to evaluate it. For example, [the writing-project spec](spec-example.md) leaves open both how to represent an author's style and how to compare passages. Start with one decision.

Send Claude the [find request](prompts.md#find-candidate-papers) with that passage and an explicit literature question. Choose sources that could help answer it. You can start with one paper and add others as needed. If a paper is inaccessible, look for an accessible version or another relevant source. Record what you could not read.

Check that each paper exists. Copy [TEMPLATE.md](sources/TEMPLATE.md) for each paper you choose, using a unique, descriptive filename such as `sources/style-evaluation.md`. Leave the template unchanged. Fill each record with the title, URL, relevant passage, and its section or page number. Keep the original papers available, locally in `sources/papers/` if useful.

Before asking Claude to summarize the sources, skim each paper's abstract, introduction, figures, and conclusion yourself. Record brief answers in your notes and mark gaps rather than guessing.

- Why should this problem be solved?
- What did the authors do, and how did they judge the result?
- How did earlier work approach the problem?
- What does this paper do differently?

An abstract may establish broad relevance. For the claim you will use in a project decision, read the supporting passage closely, including its assumptions, comparisons, and limits.

Save a copy of your completed source records before Claude builds the wiki. Run this once from the repository root. If the snapshot folder already exists, choose another unused name and use that name in the comparison command too.

```sh
mkdir evidence/sources-before-agent && cp -R sources/. evidence/sources-before-agent/
```

## 2. Build and connect the pages

Send Claude the [incorporate request](prompts.md#incorporate-sources) with the paths to the completed source records you want to add. You can supply one or several. Each record gets a page in `wiki/` with the same filename, explaining what the authors did, what they found, and what their evidence does not establish. The question page connects the sources to your spec and records what remains unanswered.

Read the pages yourself. Then compare the source records with your saved copy to check that Claude left them unchanged. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent sources
```

## 3. Check and reuse the wiki

Compare the pages with your reading notes. Check at least one factual claim against its exact passage. If the wiki connects papers, check one connection against the passages it cites. For each check, answer these questions.

- Does the passage support the claim, including its qualifiers?
- What inputs, data, metric, baseline, or assumptions does the result depend on?
- Does the paper report this result, or is it an inference by Claude or by you?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct an error or record why the claim is supported. Record the passage location and whether the claim is supported, corrected, or unresolved in [your notes](sources/notes.md#claim-checks).

Start a fresh Claude session and send the [saved-page query](prompts.md#query-the-saved-pages-in-a-fresh-session). Save the answer and any available file-read record. A fresh conversation alone does not show that Claude used the wiki.

Follow one answer claim through a wiki page to the original passage. Then save the checked answer as `wiki/answer.md`, yourself or with the [save request](prompts.md#save-the-checked-answer). Mark unchecked claims and missing evidence.

## 4. Make or revisit a choice

Use the checked answer to choose or reconsider a benchmark, metric, baseline, method, or other part of your spec. A paper's use of a method establishes precedent under its conditions. It does not establish that the method will work for your project, so name where the paper's setting differs from yours.

Record the choice, reason, and supporting passages in your spec. You can keep the choice open and name the next check if the evidence does not settle it. If `spec.md` is a copy from another project folder, update that original and refresh the copy here.

You can repeat the workflow as new questions arise. Add source records as needed, name their paths in the request, and take a fresh snapshot before each build. Keep the wiki's index and checked answer consistent with the sources you have added.
