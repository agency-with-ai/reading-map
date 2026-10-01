# Reading map query record

This is an agent-written run record, not a conversation export.

## Prompt

```text
Read CLAUDE.md. Use the saved example reading map to answer:
How should we test whether a generated technical explanation
resembles Feynman's writing?
Start at example/map/index.md. Do not browse or read the original papers.
Cite saved pages and original passage locations. State what is unresolved.
```

This is the query task used for the rehearsal, not a quotation of a separate user message.

## Execution

The agent reads the index, the two source pages, and the question page from disk. The [answer draft](../map/answer-draft.md) cites those saved pages. No new source is retrieved during answer drafting.

This is the same session as source preparation and building the reading map. The agent already has paper content in context. This run therefore does not test whether a fresh session can answer from the reading map alone.

## Answer result

The answer recommends an exploratory comparison with separate checks. It leaves the reader task, counts, threshold, and writing method unresolved. Answer check A1 in the [ledger](agent-checks.md) compares its human-evaluation claim with TinyStyler §4.2.

No user check is supplied. There is no `map/answer.md` presented as checked. The draft is retained because the user asked to record all rehearsal results.

## Fresh-session completion

Start a new conversation and use the prompt above. Check a claim against its original passage, record the user's finding in the research notes, and explicitly request that the answer be saved. Export that conversation separately from the build conversation using the host application's export function. These actions are pending.
