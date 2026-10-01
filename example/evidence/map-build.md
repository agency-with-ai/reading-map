# Reading map build record

This is an agent-written run record, not a verbatim conversation export.

## Task and scope

Run the Feynman example using the local Lab 3 instructions and record the results under `example/`. The two existing candidates are retained after inspecting their original PDFs. The independent-reading and partner portions remain pending.

## Build input

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

This block records the build task used in this session; it is not a quotation of a separate user exchange. The build uses the named records. Browsing and PDF inspection belong to source preparation and agent checking.

## Outputs

The [index](../map/index.md), [Mir page](../map/style-evaluation.md), [TinyStyler page](../map/tinystyler.md), and [question page](../map/question.md) make up the reading map. The question page has a comparison table and Mermaid diagram. It distinguishes source claims from project inferences.

## Source integrity

Before the reading map is built, the source directory is copied to [sources-before-agent](sources-before-agent/). The snapshot is archival evidence. Its relative links retain their original source-directory context; navigate the current [research notes](../paper-sources/notes.md) instead.

Run this from the repository root:

```sh
diff -ru "example/evidence/sources-before-agent" "example/paper-sources"
```

No output and exit code 0 mean the source records match. See [verification](verification.txt) for the agent's executed result. User execution of the comparison remains unrecorded.

## Access and execution limits

The local Lab 3 source and Lab 2 reading questions were read from the course checkout. The hosted Lab 3 page returned an access error and is not used as the assignment source.

Original PDFs were inspected using public ACL URLs and the installed `pdftotext` command. No dependencies were installed. The source records retain the public URLs; no PDF or extracted full text is bundled. No model experiment or recurring search ran.

A conversation export must be produced by the host application. This record supplies neither a build export nor a fresh-query export.
