# Example project: write like a professor

Build a tool that writes like a chosen EECS professor. Give staff two passages, one written by the professor and one generated, and test whether they can tell which is which.

## What I give the tool and what I get back

I supply examples of the professor's public writing, a topic, the facts to include, an audience, and a word limit. The tool returns a draft in that professor's style.

For example, I might ask it to write this passage.

> Explain to a student who knows gradient descent why high training accuracy does not guarantee good performance on new data. Include the role of a held-out test set. Use about 200 words.

I want an explanation that sounds like the professor, not a description of their style. It should resemble how they build an argument, choose examples, and address the reader. An answer that treats training accuracy as proof of performance on new data fails, even if its prose sounds convincing.

## The first version

Start with one professor and one kind of writing, short technical explanations. Collect attributed public passages, keeping some for style examples and others for evaluation.

Use a local script and one available model. Compare a plain request to write like the professor with a method informed by the literature. That method might give the model example passages, explicit instructions about style, or both. I have not chosen between them yet. Use the same model, briefs, and word limits for both approaches. A web app and fine-tuning are outside this first version.

## What would count as a good result

Staff sometimes mistake generated writing for the professor's, and the method does better than the plain request. That is the hypothesis to test, not a result I can promise.

For each comparison, derive a factual brief from a reserved original passage without copying its wording. Pair the generated draft with that original, on the same topic and at a similar length. Do not supply the original to the generator. Tell readers that one passage is generated and reveal the answer afterward.

Check facts and copied phrasing before judging style. Do not invent quotations or personal experiences. Count rejected drafts as failures and report them alongside the style judgments. Keep prompts, drafts, and votes so someone else can inspect the comparison.

## What I need from the literature

How should I show the model the professor's style? I want evidence for choosing examples, explicit style instructions, or another approach that fits this first version.

How should I test the result? I need a comparison that measures resemblance to this author, rather than whether readers prefer fluent prose or recognize copied sentences. The number of passages and readers, and the threshold for claiming improvement, remain open.

For Lab 3, choose one of these questions and use two relevant sources. The wiki should explain what each paper suggests trying, what it actually tested, and whether its evidence applies here. Use the checked evidence to make one choice in this spec, or explain why the choice remains open.

This example develops the [author-style writing project (2026)](https://github.com/agency-with-ai/courseware/issues/5). Its questions draw on the [feature-spec template (2026)](https://github.com/github/spec-kit/blob/main/templates/spec-template.md).
