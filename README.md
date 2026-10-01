# Reading Map

Use your project spec to decide what to read, then build a reading map, an LLM-maintained wiki. You read and check the papers; Claude builds pages you can query. Use the evidence to make a project decision. These instructions cover Step 4 of [Lab 3](https://agencyai.mit.edu/lab3/).

## Set up

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Copy the project spec you reviewed with your partner to `spec.md`. It should describe what you want to do, what you will try first, how you would judge that result, and what is still undecided. You can start the reading with open choices about methods or evaluation.

The examples below use [the Feynman spec](example/spec.md). The source records in `example/paper-sources/` are unchecked drafts, and their reading notes are incomplete. They show how the files fit together; use your own reading and source records for the lab. Keep your work local or private, and use only material you may share with Claude and your reviewers.

Open this folder in Claude Code, which reads [CLAUDE.md](CLAUDE.md) for its instructions. Fill in the brackets in the prompts below.

## 1. Find and read sources

Choose one open question from your spec and record it in [your notes](paper-sources/notes.md#question-from-my-spec). Name the project choice the answer could help you make. Use Claude to find candidate papers.

For the Feynman project, the question could be "How should we test whether a generated passage resembles Feynman's writing?" The spec passage could be its Comparison procedure section.

```text
Find candidate papers.
Question: [question]
Spec passage: [spec passage]
```

Pick two papers you can access that bear on that question. Save each one in `paper-sources/papers/` or note its URL. You need the originals to check claims in step 3.

Close Claude while you read. Use [Lab 2's four reading questions](https://agencyai.mit.edu/lab2/) and record your observations in [your reading notes](paper-sources/notes.md#reading-notes). Read closely the passages your decision depends on. Then copy [the source template](paper-sources/TEMPLATE.md) to a descriptive filename in `paper-sources/` and fill it in for each paper.

## 2. Build and connect the pages

Reopen Claude in this folder. Continue with your question and the two source records you filled in. For the Feynman project, the wiki should help compare ways to judge resemblance to an author.

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

Save the conversation that built the wiki using [these instructions](evidence/README.md). Then start a fresh Claude session in this folder, so it must work from the saved pages.

```text
Read CLAUDE.md. Use the saved wiki to answer [question],
starting at wiki/index.md. Do not browse or read the original papers.
```

Check at least one claim in the fresh answer against the original passage. Record your check in `paper-sources/notes.md`, including anything the evidence does not settle. Then ask Claude to save the answer with those limits visible.

```text
Save the answer. I checked [claims] against [passages]
and found [result].
```

Save this fresh conversation too, and link both exports from your notes.

## 4. Make or revisit the decision

Record your choice, reasoning, and supporting passages in `spec.md`. Explain any differences between the papers' conditions and your project's. If the evidence is insufficient, leave the question open and name the next check.

A hypothetical Feynman decision is to keep the spec's paired comparison with reserved originals and first check whether readers recognize those originals. Adopt it only if your evidence supports it.

Copy the same changes to your original spec. Close Claude and explain your decision to your partner using the wiki and the papers. If a requirement changed, have your partner judge their Step 3 case again. Record what they understood and any further revision in your notes.

Return to Lab 3 for Checkoff 2. Bring your spec, wiki, original papers, and saved conversations. Recheck saved answers when new sources affect them.

## Optional: automate a literature search

Ask Claude how you could set up a recurring search for your project question using this repo. Ask it to explain unfamiliar terms, and ask staff for help if needed. Decide where the search would run, how often, which sources it would use, and how you would review candidates before adding them to the wiki. A proposed setup is enough to discuss with staff; the required wiki work above uses the two papers you chose and checked.
