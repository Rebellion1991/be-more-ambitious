---
name: "be-more-ambitious"
description: "Use when the user wants to raise the ambition of a task or prompt: aim at the outcome (altitude), work like a top expert (depth), or bring in other fields (range). Use this whenever the user says 'be more ambitious', 'think bigger', 'go deeper', 'upgrade this prompt' or 'make this better', or shares a task that feels shallow, template-like or too small, even if they never name the skill."
---

# Be More Ambitious

Takes a task or prompt the user has in mind and raises its ambition along three axes: Altitude, Depth, Range. Speed (same work, faster) is the default and is not covered here. Based on Felix Rieseberg's article "How to be more ambitious: A tutorial for humans with models" (https://felixrieseberg.com/how-to-be-more-ambitious-a-tutorial-for-humans-with-models/). This is an independent implementation of its ideas, not affiliated with or endorsed by the author.

## When to use
- The user states a task and wants a more ambitious version of it.
- The user says a result feels shallow, generic, or like a template fill-in.
- The user asks to upgrade, deepen, or rethink a prompt before running it.

Do not use for quick factual questions or small edits. Do not apply all three axes by default if one clearly fits; say which you chose and why.

## Workflow

### 1. Restate the task
One or two sentences: what the user asked for, and what they will do with the result.

### 1b. Fit verdict
Decide before upgrading, and say the verdict in one line with the reason:
- **Full upgrade:** the real aim is an outcome or a decision, and the task is currently pitched at the level of a single deliverable.
- **Light touch:** the work is mostly creative or taste-driven. Skip altitude, apply depth and range only where they help (for example a real-user test as the outside judge).
- **Leave as is:** the task is already well pitched, or extra ambition would add cost without value.
A stated verdict keeps the output predictable and stops the framework from being forced onto work it doesn't suit.

### 2. Altitude (aim at the outcome)
Ask: what is the goal beyond the goal? What decision or action follows this task?
- Write three versions of the task, each one level higher: the literal task, the question the task answers, the outcome the task serves.
- Check fit. Altitude works when the real aim is an outcome (a decision, a standing result such as "keep X healthy"). It fits poorly for purely creative work.
- List what the higher version needs in order to work unattended: data access, connectors, a way to reproduce and verify, permission boundaries.

### 3. Depth (work like a field-leading expert)
Answer these four questions, then rewrite the task:
1. What would a top professional do here that the user did not ask for?
2. What is the rawest source material they would start from, instead of already-digested summaries?
3. Which specific methods and tools would they use? Insist on real instruments (databases, statistical models, simulators, protocol analyzers), not a change of vocabulary.
4. What, other than the model or the user, would show the result is right? Name an outside judge: a test suite, a validation tool, a held-out dataset, a reconciliation against an independent source. Never rely on the model grading itself.

Then add, where they fit:
- **Stretch goal:** set a goal beyond what looks reasonable and state that it is solvable and the model should keep going.
- **Challenge beliefs:** pick one assumption the user holds and have the model try to disprove it from raw data.
- **Produce new knowledge:** once deep in the data, ask for blind spots or early signals nobody tracks yet, validated on data the model has not seen.

### 4. Range (bring in other fields)
1. Rewrite the nouns as verbs. A "report" becomes "getting busy people to believe a causal story and decide under uncertainty". The verb exposes which fields are relevant.
2. Assemble a crew of two to five roles whose methods help (for example analyst, editor, domain specialist, red team).
3. For each role, write what that person DOES, not how they talk. Avoid role-play; use roles only to find techniques and fields.
4. Always include one adversarial role that tries to break the result.

### 5. Output
Deliver in this order:
1. **Upgraded prompt**, ready to paste, written in the user's voice.
2. **Prerequisites**: data, tools, connectors, environment, and the outside judge.
3. **Risks and limits**: where the ambition may exceed current model reliability, what needs human approval, and anything that could affect production systems or be irreversible.
4. **Smallest first run**: a cheap way to test the upgraded approach before committing to the full version.

## Rules
- Keep it practical. Prefer one strong upgrade over a long menu.
- Say plainly when the task is already well pitched and extra ambition would add cost without value.
- Ask a clarifying question only if the missing answer would change the upgrade materially; otherwise state assumptions and proceed.
- Do not invent data sources or tools the user lacks. If a prerequisite is missing, say so.
- Any step that is destructive, touches live systems, or commits money or external communications must be flagged for explicit user approval.

## Example (short)
User task: "Update the numbers in the quarterly review deck."
- Altitude: "Tell me what changed this quarter, why, and what we should do; name the three most urgent decisions with arguments for and against."
- Depth: start from raw logs rather than the dashboard; test the team's churn explanation against the data; validate any prediction on held-out data.
- Range: analyst, journalist, editor, plus a forensic accountant as red team, each doing their actual job.