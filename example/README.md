# Feynman reading-map example

How can we tell whether a generated technical explanation sounds like Feynman? This example uses two papers to examine that question and decide what to test.

The decision is to compare drafts on separate dimensions, including factual accuracy, readability, and resemblance to the author. The papers do not establish a reliable test of whether readers recognize Feynman's writing, so that question remains open.

Start with the [project spec](project-spec.md), then read the [evidence comparison](map/question.md) and [answer draft](map/answer-draft.md). The [research notes](paper-sources/notes.md) show the passages and reasoning behind the decision.

| Artifact | What it records |
|---|---|
| [Lab notes](lab-notes.md) | Project scope, worked case, critique, and decision. |
| [Source records](paper-sources/notes.md#candidate-selection) | Selected papers, original URLs, passage locations, and limits. |
| [Reading map](map/index.md) | What the two source records support and leave open. |
| [Agent checks](evidence/agent-checks.md) | Factual, connection, and answer checks against the papers. |
| [Build record](evidence/map-build.md) | Build input, output, source snapshot, and integrity command. |
| [Query record](evidence/map-query.md) | Query prompt, answer, and session context. |
| [Verification](evidence/verification.txt) | File, link, snapshot, and whitespace check results. |

## Status

The notes and checks are agent-authored and have not been independently checked. The answer comes from the build session, where the agent had already read the papers; it does not test retrieval in a fresh session. Build and query records are summaries, not conversation exports. No model experiment or reader study has been run.
