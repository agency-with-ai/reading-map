# Use the spec to build and check a wiki

Begin with your revised project spec copied to `spec.md`. For Lab 3, start after Checkoff 1. Work from the repository root. Use [the prompts](prompts.md) for each task and save the exchanges in `evidence/`.

## 4a. Find and read two sources

Choose a requirement, assumption, or undecided choice in `spec.md`. Give Claude that passage and an explicit literature question. Two relevant sources are enough. Ask staff for help if you cannot find accessible papers.

The question can concern what to build or how to evaluate it. For example, [the writing-project spec](../spec-example.md) leaves both the way to represent an author's style and the comparison procedure open. Choose one decision for this lab.

Check that each paper exists and fill in [source-a.md](sources/source-a.md) and [source-b.md](sources/source-b.md). Save the title, URL, relevant passage, and its section or page number. Keep the original papers available, locally in `reading-wiki/sources/papers/` if useful. Put your own notes in [notes.md](sources/notes.md), clearly labelled as yours.

Close Claude and skim each paper using [Lab 2's four questions](../references/reading.md). Record brief answers in `lab3-note.md` and mark unanswered questions. An abstract may establish broad relevance; the claim used for a project decision needs its supporting passage checked.

Save a copy of your completed source records before Claude builds the wiki. Run this once from the repository root. If the snapshot folder already exists, choose another unused name and use that name in the comparison command too.

```sh
mkdir evidence/sources-before-agent && cp -R reading-wiki/sources/. evidence/sources-before-agent/
```

## 4b. Build and connect the pages

Reopen Claude. Give it [CONVENTIONS.md](CONVENTIONS.md), your spec passage, and your question. Ask it to incorporate the first source, then the second and your notes. It should create source pages and a question page that connects the methods, findings, and open questions to your spec. Each page belongs in `reading-wiki/wiki/` and links from its index.

Save the requests and responses. Read the pages yourself. Compare the source records with your saved copy to check that Claude left them unchanged. No output means the copies match.

```sh
diff -ru evidence/sources-before-agent reading-wiki/sources
```

## 4c. Check and reuse the wiki

Compare the pages with your reading notes. Follow one claimed connection back to both original papers. Check a factual claim against its exact passage and assumptions using [the claim-checking guide](../references/checking-claims.md). Correct an error or record why the claim is supported.

Start a fresh Claude session and use the saved-page query in [prompts.md](prompts.md). Save the answer and any available file-read record. A fresh conversation alone does not show that Claude used the wiki.

Follow one answer claim through a wiki page to the original passage. Revise as needed, then save the checked answer as `reading-wiki/wiki/answer.md` and link it from `reading-wiki/wiki/index.md`. You may ask Claude to make those edits after your review. Mark unchecked claims and missing evidence.

## 4d. Make or revisit a choice

Use the checked answer to choose or reconsider a benchmark, metric, baseline, method, or other part of your spec. Explain why the cited precedent fits your project and where its setting differs.

Add the decision and reason to the spec in your original project folder, or leave the choice open and name the next check. Refresh the local `spec.md` copy if you continue using the wiki. Close Claude and explain the decision to your partner with the wiki and original passages available. If promised behavior changed, have them judge the affected case again. Return to [Checkoff 2](https://agencyai.mit.edu/lab3/#checkoff-2).

If access fails, save the error and keep checking sources by hand. Mark the agent work pending and agree on a next step with staff.

The [optional search helper](../references/optional-search.md) extends this workflow after the required work.
