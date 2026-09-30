# Reading Map

A starter for building and checking a literature wiki around a question from your project spec. Connect papers to a project decision, check the evidence, and keep unanswered questions visible.

See [Write like a professor (2026)](spec-example.md) for a worked project. Build a tool that imitates one professor's writing, then ask readers to distinguish real passages from generated ones. Its open questions give the wiki something to investigate.

## Start

Clone the repository and work from its root.

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Put your project spec in `spec.md`. If you keep it in another project folder, copy it here. Ask another reader to judge one possible result from the spec alone. If they cannot, add the missing example or requirement.

Open the clone in a Claude session that can read and edit local files and search the web. Then follow [the wiki guide](reading-wiki/README.md).

No wiki app or package installation is needed. Keep local Git commits as you work; pushing is not required.

## Files

| File or folder | Use |
|---|---|
| `spec.md` | Your project spec, supplied by you |
| [Write like a professor (2026)](spec-example.md) | A concrete writing project with a sample request and two open literature questions |
| [reading-wiki/README.md](reading-wiki/README.md) | The guide to finding, reading, and checking sources |
| [reading-wiki/prompts.md](reading-wiki/prompts.md) | Requests to send Claude for each task |
| [reading-wiki/CONVENTIONS.md](reading-wiki/CONVENTIONS.md) | Rules Claude follows when it finds sources, builds pages, and answers from them |
| `reading-wiki/sources/` | Your source records and notes |
| `reading-wiki/wiki/` | Pages Claude creates and connects |
| `evidence/` | Saved conversations and file-read records |
| [references/](references/README.md) | Further reading on wikis and specifications |

Use project material you may share with Claude and anyone reviewing your work. Keep your working copy local or in a private repository. Git ignores `spec.md`, saved papers, and `evidence/`. Source records and notes can enter commits, so inspect them before sharing.

The starter is adapted from [Agency with AI course materials](https://github.com/agency-with-ai/courseware) under [CC BY-SA 4.0](LICENSE). Papers, excerpts, and your project files retain their own licenses.
