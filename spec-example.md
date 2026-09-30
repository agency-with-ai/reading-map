# Example project: write like a professor

## Purpose and scope

The project builds a tool that writes like a chosen EECS professor. This increment tests whether readers can tell its writing from the professor's.

The increment covers one professor and one kind of writing, short technical explanations. It compares a plain request to write like the professor with a method informed by the literature. A web app and fine-tuning are outside this increment.

## Inputs and outputs

I supply examples of the professor's public writing, a topic, the facts to include, an audience, and a word limit. The tool returns a draft in that professor's style.

Each comparison produces two passages on the same topic, one written by the professor and one generated, and readers' votes on which is which. Keep the prompts, drafts, and votes so someone else can inspect the comparison.

## Required behavior

The draft should sound like the professor, not describe their style. It should resemble how they build an argument, choose examples, and address the reader. It must not invent quotations or personal experiences.

Collect attributed public passages, keeping some for style examples and others for evaluation. For each comparison, derive a factual brief from a reserved original passage without copying its wording. Do not supply the original to the generator. Pair the generated draft with that original, on the same topic and at a similar length. Tell readers that one passage is generated and reveal the answer afterward.

Use the same model, briefs, and word limits for both approaches.

## Examples and acceptance checks

For example, I might ask the tool to write this passage.

> Explain to a student who knows gradient descent why high training accuracy does not guarantee good performance on new data. Include the role of a held-out test set. Use about 200 words.

An acceptable draft explains the gap correctly in about 200 words and reads like the professor's own explanation. A draft that treats training accuracy as proof of performance on new data fails, even if its prose sounds convincing.

Check facts and copied phrasing before judging style. Reject a draft with a factual error, wording copied from the reserved original, or an invented quotation or experience. Count rejected drafts as failures and report them alongside the style judgments.

The hypothesis is that readers sometimes mistake generated writing for the professor's, and the method does better than the plain request. The comparison design and threshold for improvement remain open below.

## Assumptions and open questions

I assume the professor has enough attributed public writing to supply style examples and still reserve passages for evaluation.

How should I show the model the professor's style? I need evidence to choose example passages, explicit style instructions, both, or another approach that fits this increment.

How should I test the result? I need a comparison that measures resemblance to this author, rather than whether readers prefer fluent prose or recognize copied sentences. The number of passages and readers, and the threshold for claiming improvement, remain open.

The method must be chosen before generating drafts. The number of passages and readers and the threshold must be set before any reader votes.

## Implementation constraints

Use a local script and keep the records in files someone else can inspect. The model and script design are open.

This example develops the [author-style writing project (2026)](https://github.com/agency-with-ai/courseware/issues/5).
