# Example project: write like Feynman

## Goal and scope

Eventually I would like a tool that can imitate anyone's writing style. This first version covers one author, Richard Feynman, and one kind of writing, short technical explanations. It is for people who want a technical idea explained to a particular audience, such as a student learning a topic or a teacher preparing notes.

Test whether readers mistake the drafts for Feynman's writing. Compare a method chosen from the literature with a plain one-line request to write like Feynman.

Use a local script and save the prompts, drafts, and reader votes for others to inspect. A web app and fine-tuning are outside the scope. The model and script design are open.

## Inputs and output

The user supplies a topic, an audience, and a word limit. The tool returns an explanation that resembles how Feynman builds an argument, chooses examples, and addresses the reader.

Feynman's published writing is part of building the tool, not an input. I collect it as described in the comparison procedure below.

For example, a user asks for a 200-word explanation of overfitting for a college student. A good draft explains why high training accuracy does not guarantee good performance on new data, and the role of a held-out test set. A draft that treats training accuracy as proof of performance on new data fails, even if it sounds convincing.

## One-day version

Keep the plain request, one version of the method, and three reserved passages. Judge each pair myself instead of recruiting readers. Leave out the reader comparison and the improvement threshold.

This version is useful if method drafts pass the fact and copying checks and read closer to the reserved originals than the plain drafts do. It cannot show whether readers mistake the drafts for Feynman's writing.

## Comparison procedure

Collect attributed passages from the author's published writing. Use some as style examples and reserve others for evaluation. Prefer reserved passages that readers are unlikely to have read.

For each reserved passage, prepare a factual brief without copying its wording. Give the tool the brief in place of a topic, but not the original passage.

Choose the method before generating drafts. Use both that method and the plain request, keeping the model, briefs, and word limits the same.

Before collecting reader votes, settle open decision 2 below.

Unless the literature points to a better design, pair each generated draft with its reserved original on the same topic and at a similar length. Tell readers that one passage is generated and ask which one. Reveal the answer after they vote.

The comparison should measure resemblance to the author, rather than a preference for fluent prose or recognition of a familiar passage.

## Acceptance checks

Check facts and copied phrasing before asking readers to judge style. Reject drafts with factual errors, wording copied from the reserved original, or invented quotations or personal experiences. A draft that describes the author's style instead of explaining the topic also fails.

Count rejected drafts as failures and report them alongside reader judgments.

## Challenges

- The model may have memorized Feynman's best-known passages and copy their wording.
- Readers may recognize a famous original and vote from memory instead of judging style.
- Drafts may invent quotations or anecdotes to sound like Feynman.

## Assumptions and open decisions

I assume some of Feynman's published passages are obscure enough that neither readers nor the model recognize them.

The literature search should inform two decisions.

1. How should I show the model the author's style? Consider example passages, explicit style instructions, a combination, or another approach within scope.
2. How should I measure success? Decide whether the paired comparison tests resemblance to the author, how many passages and readers to use, and how much improvement over the plain request counts.
