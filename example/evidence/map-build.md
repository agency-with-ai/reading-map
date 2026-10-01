# Reading map build record

Build summary. See [example status](../README.md#status).

## Task prompt

```text
Build the example reading map.
Question: How should we test whether a generated technical explanation
resembles Feynman's writing?
Spec passage: example/project-spec.md, Comparison procedure and open decision 2.
Source records:
- example/paper-sources/style-evaluation.md
- example/paper-sources/tinystyler.md
Treat these as agent-prepared drafts, not user-checked records.
Write the reading map under example/map/.
```

## Outputs

The [index](../map/index.md), [Mir page](../map/style-evaluation.md), [TinyStyler page](../map/tinystyler.md), and [question page](../map/question.md) make up the reading map. The question page has a comparison table and Mermaid diagram. It distinguishes source claims from project inferences.

## Source integrity

Before the reading map is built, the source directory is copied to [sources-before-agent](sources-before-agent/). The snapshot is archival evidence. Its relative links retain their original source-directory context; navigate the current [research notes](../paper-sources/notes.md) instead.

Run this from the repository root:

```sh
diff -ru "example/evidence/sources-before-agent" "example/paper-sources"
```

No output and exit code 0 mean the files match. The paper records match the snapshot; the current `notes.md` differs. See [verification](verification.txt) for the comparison results.
