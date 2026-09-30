# Example spec for author-style writing

This example develops the [author-style writing project (2026)](https://github.com/agency-with-ai/courseware/issues/5). Its structure adapts the [feature-spec template (2026)](https://github.com/github/spec-kit/blob/main/templates/spec-template.md). Use your own revised project spec as `spec.md`.

## Purpose and scope

Build a writing tool that produces short technical explanations resembling one chosen EECS professor's public writing while preserving supplied facts. The first increment covers one author and one genre, technical blog posts. Use a local script, Markdown files, and one available model. No fine-tuning or web application is required.

Compare a plain request to write like the author with a candidate method for representing their style. Examples plus an explicit style guide are one candidate, not a settled choice.

## User scenarios and acceptance checks

### Produce a draft

Given attributed reference samples, a factual brief, an audience, and a word limit, the tool returns a draft for each condition.

A brief says a method worked on one dataset and has not been tested elsewhere. A draft claiming it works generally fails, however convincing its style.

### Compare the writing

Given checked drafts and reserved original passages, staff or classmates judge which passage in each pair the author wrote. They know one passage is generated but do not see the answer until afterward.

A comparison fails its check if it reveals the answer early or pairs passages with different subject matter or substantially different lengths.

## Requirements

- Accepted drafts must preserve the brief's claims, numbers, and qualifications without inventing quotations, citations, or personal experiences.
- Keep evaluation passages out of the reference samples and style instructions. Derive factual briefs from those passages without copying their phrasing.
- Use the same briefs, model settings, and length limits for both conditions.
- Pair each draft with the original passage used to derive its factual brief. Match audience and approximate length. Randomize display order. Do not show one reader the same original across conditions.
- Save drafts, sample IDs, prompts, model settings, display order, and votes. Label generated drafts in saved records.
- Review drafts for factual changes and distinctive copied wording. Exclude failed drafts from style comparisons and report their failures separately. Shared technical terms alone do not count as copying.

## Success criteria

The tool must save complete records, construct comparisons as specified, and tally votes correctly. A rejected draft remains in the records with its reason for rejection. Passing these checks does not establish that the candidate method reproduces the author's style.

For each condition, report factual and copying failures and how often readers select the generated passage as the author's. Include the number of passages and judgments. This measures identification, not reader preference. A threshold for claiming improvement remains open pending evidence and a pilot.

## Assumptions and open questions

The samples are attributable to this author, and readers can inspect separate reference samples. Whether the model encountered evaluation passages during training is unknown. A small pilot does not establish a general ability to reproduce the author's voice.

## Literature task for Step 4

Two project decisions need evidence.

- How should the tool represent the author's style, using examples, explicit instructions, or another method?
- How should we compare passages so readers judge author style rather than topic, fluency, or copied wording?

For the lab, choose one question and two relevant sources. Follow the separate search, build, and query stages in [the wiki instructions](reading-wiki/prompts.md).

Connect the papers' methods, evidence, and limits to the chosen decision. Distinguish approaches worth trying from evidence that they work. Check the supporting passages, then use the wiki to support or revise a project choice, or explain why it remains unresolved. Keep this spec unchanged while the agent builds the wiki.
