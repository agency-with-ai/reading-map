# Example project: write like Feynman

## Goal and scope

Build a tool that drafts short technical explanations in Richard Feynman's style. Test whether readers mistake the drafts for his writing. Compare a method chosen from the literature with a plain request to write like him.

This version covers one author and one kind of writing. Use a local script and save the prompts, drafts, and reader votes for others to inspect. A web app and fine-tuning are outside the scope. The model and script design are open.

## Inputs and output

I supply passages from Feynman's published lectures and books, the facts to include, an audience, and a word limit. The tool returns an explanation that resembles how he builds an argument, chooses examples, and addresses the reader.

For example, an explanation for a student who knows gradient descent covers why high training accuracy does not guarantee good performance on new data. It also explains the role of a held-out test set. A draft that treats training accuracy as proof of performance on new data fails, even if it sounds convincing.

## Comparison procedure

Collect attributed passages from the author's published writing. Use some as style examples and reserve others for evaluation. Prefer reserved passages that readers are unlikely to have read.

For each reserved passage, prepare a factual brief without copying its wording. Give the generator the brief, but not the original passage.

Choose the method before generating drafts. Use both that method and the plain request, keeping the model, briefs, and word limits the same.

Before collecting reader votes, settle open decision 2 below.

Unless the literature points to a better design, pair each generated draft with its reserved original on the same topic and at a similar length. Tell readers that one passage is generated and ask which one. Reveal the answer after they vote.

The comparison should measure resemblance to the author, rather than a preference for fluent prose or recognition of a familiar passage.

## Acceptance checks

Check facts and copied phrasing before asking readers to judge style. Reject drafts with factual errors, wording copied from the reserved original, or invented quotations or personal experiences. A draft that describes the author's style instead of explaining the topic also fails.

Count rejected drafts as failures and report them alongside reader judgments.

## Assumptions and open decisions

I assume some of Feynman's published passages are obscure enough that neither readers nor the model recognize them.

The literature search should inform two decisions.

1. How should I show the model the author's style? Consider example passages, explicit style instructions, a combination, or another approach within scope.
2. How should I measure success? Decide whether the paired comparison tests resemblance to the author, how many passages and readers to use, and how much improvement over the plain request counts.
