# Reading Map

Build a literature wiki to answer a question from your project spec. You read and check the papers; Claude builds pages you can query. Use the evidence to make a project decision.

## Set up

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Copy your project spec to `spec.md`. The examples below use [the Feynman spec](spec-example-write-like-feynman.md). Keep your copy local or private, and use only material you may share with Claude and your reviewers.

Open this folder in Claude Code, which reads [CLAUDE.md](CLAUDE.md) for its instructions. Fill in the brackets in the prompts below.

## 1. Find and read sources

Choose one open question from your spec.

For the Feynman project, the question could be "How should we test whether a generated passage resembles Feynman's writing?" The spec passage could be its Comparison procedure section.

```text
Find candidate papers.
Question: [question]
Spec passage: [spec passage]
```

Select papers you can access. Save each one in `paper-sources/papers/` or note its URL. You need the original to check claims in step 3.

Read each paper using the prompts in [your reading notes](paper-sources/notes.md#reading-notes), and record your observations there. Then copy [the source template](paper-sources/TEMPLATE.md) to a descriptive filename in `paper-sources/` and fill it in.

## 2. Build and connect the pages

Continue with that question and the source records you filled in. For the Feynman project, the wiki should help compare ways to judge resemblance to an author.

```text
Build the wiki pages.
Question: [question]
Spec passage: [spec passage]
Source records: [paths]
```

Start at [wiki/index.md](wiki/index.md). Read the source pages, then `wiki/question.md`, which compares the sources and connects them to your decision.

Before building, Claude copies your source records into `evidence/`. Run the `diff` command it gives you. No output means Claude left your records unchanged.

## 3. Check and query the wiki

Check at least one factual claim and one connection between papers against the original passages. Record each passage and any correction in [your claim checks](paper-sources/notes.md#claim-checks). That section of your notes lists questions to ask.

For example, if the wiki recommends an evaluation method for the Feynman project, check whether the cited paper tests resemblance to a particular author or only fluent writing.

```text
Use the saved wiki to answer [question].
```

Check the answer against the cited passages. Then ask Claude to save it.

```text
Save the answer. I checked [claims] against [passages]
and found [result].
```

Save the conversation using [these instructions](evidence/README.md).

## 4. Make or revisit the decision

Record your choice, reasoning, and supporting passages in `spec.md`. Explain any differences between the papers' conditions and your project's. If the evidence is insufficient, leave the question open and name the next check.

A hypothetical Feynman decision is to keep the spec's paired comparison with reserved originals and first check whether readers recognize those originals. Adopt it only if your evidence supports it.

Copy the same changes to your original spec. Recheck saved answers when new sources affect them.
