# Reading Map

Build a literature wiki to help answer a question from your project spec. You read and check the papers; Claude connects your source records into pages you can query. Use the checked evidence to make a project decision or name what you still need to learn.

## Set up

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Put your project spec in `spec.md`. You can copy it from another project folder. See [Write like Feynman](spec-example.md) for an example.

Keep your copy local or in a private repository. Include only material you may share with Claude and anyone reviewing your work. Open the repo in a Claude session that can read and edit local files and search the web.

Use these files as you work.

| File or folder | What goes here |
|---|---|
| `spec.md` | Your project requirements, question, and decision |
| [paper-sources/TEMPLATE.md](paper-sources/TEMPLATE.md) | A template to copy for each paper you read |
| [paper-sources/notes.md](paper-sources/notes.md) | Your observations and checks |
| [wiki/index.md](wiki/index.md) | Links to the pages Claude builds |
| [evidence/](evidence/README.md) | Saved conversations and source snapshots |

[CLAUDE.md](CLAUDE.md) defines the agent's tasks and limits. Fill in the bracketed fields in each request below.

## 1. Find and read sources

Choose one requirement, assumption, or open decision in your spec. The [example spec](spec-example.md), for instance, asks how to represent an author's style and test whether generated writing resembles it.

```text
Read CLAUDE.md.
The choice I want to investigate is [choice].
The relevant spec passage is [passage].
Find candidate papers that could help answer [question].
```

Select papers from the candidates. If a paper is inaccessible, find an accessible version or another source, and note what you could not read.

For each paper you open, copy [TEMPLATE.md](paper-sources/TEMPLATE.md) to a descriptive filename such as `paper-sources/style-evaluation.md`. Fill in the copy and leave the template unchanged. Keep the original paper available; you can save it in `paper-sources/papers/`.

Start with the abstract, introduction, figures, and conclusion. Identify the problem, the authors' approach, how it differs from earlier work, and how they judged the result. Then read the passage behind any claim you might use in your decision, including its assumptions and limits. An abstract alone may establish relevance, but not support that claim.

## 2. Build and connect the pages

Before each build, copy your source records so you can check that Claude leaves them intact. Run this from the repository root. If the destination exists, choose an unused name and use it in both commands below.

```sh
mkdir evidence/sources-before-agent && cp -R paper-sources/. evidence/sources-before-agent/
```

Give Claude the completed records to use.

```text
Read CLAUDE.md.
My question is [question], about [spec passage].
Build or update the wiki from these completed source records:
[source-record paths].
```

Start reading at [wiki/index.md](wiki/index.md). Each source gets a page; `wiki/question.md` compares the evidence and diagrams how it bears on your decision. View the diagram on GitHub or in [Obsidian](https://obsidian.md). Opening the repo as an Obsidian vault also lets you view page links as a graph.

Check that the source records match your copy. No output means they match.

```sh
diff -ru evidence/sources-before-agent paper-sources
```

## 3. Check and query the wiki

Check the claims and connections your decision depends on against the original passages.

- Does each passage support the claim and its qualifiers?
- What data, metric, baseline, or assumptions does the result depend on?
- Is the claim a reported result, your inference, or Claude's inference?
- For a connection between papers, what does each passage contribute?
- Which conditions match your project, and which remain untested?

Correct errors in the pages. In [your claim checks](paper-sources/notes.md#claim-checks), record the passage location and whether the claim is supported, corrected, or unresolved. Leave claims you have not checked marked as unchecked.

Ask Claude to answer from the wiki, in this session or a new one.

```text
Read CLAUDE.md.
Use the saved wiki to answer [question].
```

Check the answer against the cited passages. To save it, send this request in the same session.

```text
Read CLAUDE.md.
Save the answer. I checked [claims] against [passages]
and found [result].
```

Claude saves it in `wiki/answer.md`, preserving your checks and marking remaining claims as unchecked. You can also write that file yourself and link it from the index. Save the conversation as described in [evidence/README.md](evidence/README.md).

## 4. Make or revisit the decision

Record your choice, reasoning, and supporting passages in the spec. Explain where the papers' conditions differ from your project's. If the evidence does not settle the question, leave the choice open and name the next check.

If `spec.md` is a copy, update the original spec and refresh this copy. Repeat the process for new questions, and recheck saved answers when new sources affect them.
