# One agent + skills: the two prompts

Anthropic's own engineers said they stopped building a new agent for every task. They use one general agent and give it skills instead. A skill is just a folder with a text file (`SKILL.md`) that describes how you do one job.

These are the two prompts from my reel. They work in Claude Code and in the Claude app.

## Prompt 1: do the job once, then save it as a skill

Paste this before you start a task that you do often:

```text
We are going to do this task together once: <describe the task>.
Watch how we do it and remember every correction I make.
When I say "save it", turn this chat into a skill with the skill creator:
the steps we followed, my corrections as rules, and one finished example.
```

Do the task, correct Claude like you would correct a new hire, and then write:

```text
Save it. Turn this chat into a skill.
```

Next time you do this task, Claude already works your way. When something is still off, correct it and say "update the skill".

## Prompt 2: when a new model comes out, test the skill

Old instructions were written for weaker models, so they can hold a new model back. Boris Cherny, who created Claude Code, said that every six months you should delete your skills and see what the model does without them. You don't have to delete anything. Run the task twice:

```text
Do this task twice and show me both results side by side: <describe the task>.
Run 1: use my <skill name> skill.
Run 2: do not use any skill, and ignore my saved instructions for this task.
Then tell me which result is better and which lines of the skill made run 1 worse.
```

Keep the skill only if it still wins. If the run without the skill is better, delete the lines that made it worse.

## Sources

- RoboNuggets, "Anthropic's Engineers Stopped Building AI Agents (Here's What They Build Instead)": https://youtu.be/IMSYKloMFrE (the reel is based on this video)
- Barry Zhang and Mahesh Murag (Anthropic), "Don't Build Agents, Build Skills Instead", AI Engineer: https://youtu.be/CEvIs9y1uog
- "Boris Cherny: We Cut 80% of Claude Code's Prompt", Y Combinator: https://youtu.be/qyPCVqFUyDo

The wording of both prompts is mine. Made for the reel on [@aipractically](https://www.instagram.com/aipractically/).
