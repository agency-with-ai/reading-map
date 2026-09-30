# Use the spec to build and check a wiki

Work from the repository root with your revised spec copied to `spec.md`. [prompts.md](prompts.md) has a request for each Claude task below. Save each exchange in `evidence/`.

## 4a. Find and read two sources

Choose a requirement, assumption, or undecided choice in `spec.md`. The question can concern what to build or how to evaluate it. For example, [the writing-project spec](../spec-example.md) leaves open both how to represent an author's style and how to compare passages. Choose one decision for this lab.

Send Claude the find request with that passage and an explicit literature question. Two relevant sources are enough. Ask staff for help if you cannot find accessible papers.

Check that each paper exists and fill in [source-a.md](sources/source-a.md) and [source-b.md](sources/source-b.md). Save the title, URL, relevant passage, and its section or page number. Keep the original papers available, locally in `reading-wiki/sources/papers/` if useful. Put your own notes in [notes.md](sources/notes.md), clearly labelled as yours.

Close Claude and skim each paper's abstract, introduction, figures, and conclusion. Answer [Lab 2's four questions](https://agencyai.mit.edu/lab2/) about motivation, solution, old idea, and delta in `lab3-note.md`, and mark gaps rather than guessing. An abstract may establish broad relevance. For the claim you will use in a project decision, read the supporting passage closely, including its assumptions, comparisons, and limits.

Save a copy of your completed source records before Claude builds the wiki. Run this once from the repository root. If the snapshot folder already exists, choose another unused name and use that name in the comparison command too.

```sh
mkdir evidence/sources-before-agent && cp -R reading-wiki/sources/. evidence/sources-before-agent/
```

## 4b. Build and connect the pages

Reopen Claude and send the two build requests. The first creates a page for source A. The second adds a page for source B and a question page that connects both papers to your spec.

Read the pages yourself. Then compare the source records with your saved copy to check that Claude left them unchanged. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent reading-wiki/sources
```

## 4c. Check and reuse the wiki

Compare the pages with your reading notes. Check one factual claim against its exact passage, and follow one claimed connection back to both original papers. For each, answer these questions.

- Does the passage support the claim, including its qualifiers?
- What inputs, data, metric, baseline, or assumptions does the result depend on?
- Does the paper report this result, or is it an inference by Claude or by you?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct an error or record why the claim is supported. Record the passage location and whether the claim is supported, corrected, or unresolved in `lab3-note.md`.

Start a fresh Claude session and send the saved-page query. Save the answer and any available file-read record. A fresh conversation alone does not show that Claude used the wiki.

Follow one answer claim through a wiki page to the original passage. Then save the checked answer as `reading-wiki/wiki/answer.md`, yourself or with the save request. Mark unchecked claims and missing evidence.

## 4d. Make or revisit a choice

Use the checked answer to choose or reconsider a benchmark, metric, baseline, method, or other part of your spec. A paper's use of a method establishes precedent under its conditions. It does not establish that the method will work for your project, so name where the paper's setting differs from yours.

Add the decision and reason to the spec in your original project folder, or leave the choice open and name the next check. Copy the spec here again if you keep using the wiki. Then return to [4d on the Lab 3 page](https://agencyai.mit.edu/lab3/#lab-4d-make-or-revisit-a-choice) to explain the decision to your partner and prepare for Checkoff 2.
