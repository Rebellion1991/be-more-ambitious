# be-more-ambitious

A Claude skill that takes a task or prompt and raises its ambition along three axes:

- **Altitude:** aim at the outcome, not the individual task.
- **Depth:** work the way a field-leading expert would, with real tools, raw data and an outside judge.
- **Range:** bring in other fields, and a red team, by describing what those people *do* rather than role-playing them.

Speed (the same work, faster) is the default and is not covered.

Based on Felix Rieseberg's article, [How to be more ambitious: A tutorial for humans with models](https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/). This is an independent implementation of its ideas and is not affiliated with or endorsed by the author.

## What you get

For each task the skill returns:

1. A fit verdict (full upgrade, light touch, or leave as is)
2. An upgraded prompt, ready to paste
3. Prerequisites: data, tools, connectors, and the outside judge
4. Risks and limits, including steps that need human approval
5. The smallest first run to test the approach cheaply

## Example

Task: "Update the numbers in the quarterly review deck."

- Altitude: ask what changed, why, and which three decisions are most urgent.
- Depth: start from raw logs rather than the dashboard, challenge the team's explanation, validate on held-out data.
- Range: analyst, journalist, editor, plus a forensic accountant as red team, each doing their actual job.

## Install

**As a plugin (marketplace):**

```bash
claude plugin marketplace add Rebellion1991/be-more-ambitious
claude plugin install be-more-ambitious@be-more-ambitious
```

**Manually (copy the skill folder):**

```bash
git clone https://github.com/Rebellion1991/be-more-ambitious
cp -r be-more-ambitious/skills/be-more-ambitious ~/.claude/skills/
```

## Use

Ask Claude things like "be more ambitious about this", "think bigger", "go deeper", or "upgrade this prompt", and paste your task.

## License

MIT. See [LICENSE](LICENSE).
