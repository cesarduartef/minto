# Minto

**A Claude skill that organizes your ideas with Barbara Minto's Pyramid Principle: the conclusion first, and supporting arguments grouped logically.**

🇪🇸 [Leer en español](README.md)

---

## What it does

Give it an email, a proposal, a report or a loose idea, and Minto helps your reader get what matters in the first line.

**You don't need to know the method: the skill applies it for you.** Talk to it about your text the way you'd talk to a colleague, and it answers about your text, not about theory.

It has four modes, and Claude picks the right one based on what you ask:

| Mode | When | What you get |
|---|---|---|
| **Clarify** | You have an intention but don't know how to frame it | Up to four questions and a card with your main idea and its supporting points |
| **Structure** | You have notes, data or a draft to reorganize | The text with the conclusion first, without losing or inventing any facts |
| **Review** | You want to know if your text comes across | A diagnosis with a verdict, findings that quote your text and the three fixes that matter most. It never rewrites anything without your permission |
| **Define the problem** | Before a proposal or a research project | A card with the situation, the result you don't want, the one you do, and the question your document must answer |

## An example

**Before**
> Hi Anna. Yesterday we met with the team to review the campaign's progress. We went over the metrics for the first three weeks, talked with the sales team and also looked at ad spend. Sales mentioned that leads come in with very little information. Cost per lead is up 30% over plan. The current form only asks for name and email. We think some adjustments may be needed. Can we talk about it?

**After**
> **Subject: Can you approve a change to the campaign form this week?**
> Hi Anna. I'd like your approval to change the campaign form this week, to address two problems we saw yesterday:
> 1. Cost per lead is 30% over plan.
> 2. Sales gets leads with only a name and email, with no data to qualify them.
>
> The proposal is to add company and job title. If you confirm today, I'll coordinate the change.

Not a single fact was added. Only the order changed, and the ask became clear.

## Who it's for

Anyone who writes so that others can decide or act: emails, proposals, quotes, reports, executive summaries, presentations, theses, academic papers and classes.

It isn't for everything, and the skill knows it: it won't reorder incident timelines, manuals or stories, because there the chronological order is the content.

## Installation

There are two versions of the same skill. **Install only one.** Both work the same way and respond in the language of your text; the only difference is the language of the instructions.

### In Claude (web, desktop or mobile)

1. Download [`minto-en.zip`](dist/minto-en.zip) (or [`minto-es.zip`](dist/minto-es.zip) for the Spanish version).
2. In Claude, go to **Customize > Skills**.
3. Click **+**, then **Create skill**, and choose **Upload a skill**.
4. Upload the zip and turn the skill on.

Code execution must be enabled under **Settings > Capabilities**. It also works on the free plan. See the [official skills guide](https://support.claude.com/en/articles/12512180-use-skills-in-claude) if you need help.

### In Claude Code

```bash
claude plugin marketplace add cesarduartef/minto
claude plugin install minto-en@minto
```

For the Spanish version, use `minto-es@minto`.

## How to use it

You don't need to type any command. Claude activates it on its own when you ask things like:

- "Review this email before I send it"
- "Structure these notes into a report for the board"
- "Does my main point come across?"
- "I need to convince my boss to do X and I don't know how to frame it"
- "Help me define this client's problem before the proposal"

You can also call it directly with `/minto`.

## What makes it different

There are other Pyramid Principle skills, all of them in English only. This one:

- **Comes in Spanish and English**, and responds in the language of your text.
- **Is built from the book.** Beyond the pyramid rules, it includes two parts of the book that almost nobody uses: how to **define a problem** before writing, and **seven patterns** for the most common documents (requesting approval for an expense, a proposal to a new client, a progress report, choosing between alternatives and more).
- **Covers academic writing and teaching**, not just business documents.
- **Doesn't invent facts.** Anything missing is marked as `[missing: ...]`.
- **Asks first.** If you just show it your draft, it tells you what it sees and offers to rewrite it, but it won't change it unless you ask.

## How it was tested

The skill was tested with 8 cases (an email with a buried conclusion, an incident timeline, an empty academic abstract, an English text, a client problem definition, among others), solved by agents that took no part in writing it. The cases and results are in [`evals/`](evals/) (in Spanish).

## Repository structure

```
minto/
├── plugins/
│   ├── minto-es/skills/minto/   ← Spanish version (original)
│   └── minto-en/skills/minto/   ← English version (translation)
├── dist/                        ← zips to install in Claude
├── evals/                       ← test cases and results
└── .claude-plugin/              ← for installing from Claude Code
```

## Credits

- Based on *The Pyramid Principle: Logic in Writing and Thinking* by **Barbara Minto**. The principles are explained in our own words. It's a tribute: this project is not affiliated with the author. If the skill helps you, read the book.
- Some design ideas are inspired by other open skills on the same topic: [millwright-labs/minto-pyramid-skill](https://github.com/millwright-labs/minto-pyramid-skill) (asking before rewriting), [welltraum/minto](https://github.com/welltraum/minto) (the mechanism versus reason test) and [tyroneross/pyramid-principle](https://github.com/tyroneross/pyramid-principle) (the review verdict). Thanks to their authors.

## License

[MIT](LICENSE). You can use, modify and share it with attribution.

## Author

**César Duarte** · [LinkedIn](https://www.linkedin.com/in/cesarduartef)

Ideas or issues? Open an [issue](../../issues).
