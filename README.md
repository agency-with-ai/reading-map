# Reading Map

Build a literature wiki to answer a question from your project spec. You read and check the papers; Claude builds pages you can query. Use the evidence to make a project decision.

## Set up

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Copy your project spec to `spec.md`. The examples below use [the Feynman spec](spec-example-write-like-feynman.md). Keep your copy local or private, and use material you may share with Claude and your reviewers.

Open this folder in Claude Code, which reads [CLAUDE.md](CLAUDE.md) for its instructions. Fill in the brackets in the prompts below.

## 1. Find and read sources

Choose one open question from your spec.

For the Feynman project, ask “How should we test whether a generated passage resembles Feynman's writing?” Use the spec's comparison procedure as context.

```text
Find candidate papers about [question], using [spec passage].
```

Select papers you can access. For each, copy [the source template](paper-sources/TEMPLATE.md) to a descriptive filename in `paper-sources/` and fill it in. Keep the original paper available.

Identify the problem, approach, difference from earlier work, and how the authors judged the result. Read the passages your decision depends on. Record your observations in [your notes](paper-sources/notes.md#reading-notes).

## 2. Build and connect the pages

Continue with that question and the source records you filled in. For the Feynman project, the wiki should help compare ways to judge resemblance to an author.

```text
Build the wiki to help answer [question] about [spec passage].
Use these completed source records: [paths].
```

Start at [wiki/index.md](wiki/index.md). Read the source summaries and the comparison of evidence for your decision.

Claude saves a copy of your source records before building. Run the comparison command it provides; no output means the records match.

## 3. Check and query the wiki

Check a factual claim and a connection between papers against the original passages. Record the passages and any corrections in [your claim checks](paper-sources/notes.md#claim-checks), which include more detailed questions.

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

Record your choice, reasoning, and supporting passages in the spec. Explain any differences between the papers' conditions and your project's. If the evidence is insufficient, leave the question open and name the next check.

A hypothetical Feynman decision is to keep the blind comparison with reserved originals and first check whether readers recognize those originals. Adopt it only if your evidence supports it.

If `spec.md` is a copy, update the original too. Recheck saved answers when new sources affect them.
