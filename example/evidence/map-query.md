# Reading map query record

Query summary. See [example status](../README.md#status).

## Task prompt

```text
Read CLAUDE.md. Use the saved example reading map to answer:
How should we test whether a generated technical explanation
resembles Feynman's writing?
Start at example/map/index.md. Do not browse or read the original papers.
Cite saved pages and original passage locations. State what is unresolved.
```

## Context

The query uses the index, two source pages, and comparison page. It runs in the build session; paper content is already in context.

## Answer result

The [answer draft](../map/answer-draft.md) recommends an exploratory comparison with separate checks. It leaves the reader task, counts, threshold, and writing method unresolved. Answer check A1 in the [ledger](agent-checks.md) compares its human-evaluation claim with TinyStyler §4.2.

## Fresh-session completion

To test retrieval from the saved map, use the prompt above in a fresh session and follow the [checking and saving prompts](../../README.md#3-check-and-query-the-reading-map).
