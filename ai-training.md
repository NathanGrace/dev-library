


# Goals of this Training
- Give an AI crash course
- Encourage experimentation
- replace fear with optimism
- find out if these clankers can actually help us



# Core Concepts
Obviously AI has become a massive thing that exists now and there's many layers to it, but like any abstraction, we don't have to know everything under the hood for us to use it effectively. We all know AI is not a one size fits all solution, so we have to get a feel for what we can and can't do with them. I think these core concepts are what help the most for getting that feel and learning where the edges are.
1. Models
2. Tokens & Context Window
3. Reliability (why do they hallucinate?)
4. How do we get higher quality outputs?
5. Where does AI best fit into the dev workflow?

## Models - the actual clankers.
over time models have become more of a commodity than you might think. The main things you should be thinking about when choosing a model for any given task is cost, reasoning, speed, and consistency/reliability. Beyond that there's no real reason to have loyalty to any one model because there's so many of them, and new ones are being released all the time.

## Tokens & Context Window - working memory.
  - information overload results in context rot

## Reliability (why do they hallucinate?) - statistics and non-determinism.
  - they are basically just prediction machines, so thinking in terms of statistics is helpful here.
	- an AI model is basically a system that predicts likely next pieces of text; it can sound confident without being correct.

## How do we get higher quality outputs? - set them up for success.
  - Existing Training Data, Prompts/Instructions, and Context are what determine the output quality.

## Where does AI best fit into the dev workflow? - when verification is cheap.
  - plan

# Harnesses and Interfaces for day to day use
tbh, what you choose to use will likely just come down to preferences. Although it sounds funny to admit, I do think that vibes matter when figuring out what works best for you. If you vibe with it, then stick with it. If you don't, it just ends up adding friction and frustration to whatever you're trying to do with it.

1. Normal chat apps
   I think we're basically only supposed to use the copilot chat cause it has data security, but in general chat apps are probably what we're all most familiar with and aware of. A lot of these exist.

- chatgpt.com
- copilot.com
- claude.ai
- gemini.google.com
- t3.chat

2. IDE features and/or extensions
Cursor is an example of an "AI first IDE". There are others but cursor seems to be the best of the bunch.
One editor that's like an inbeteween of AI first and a more traditional IDE is Zed which I'm keeping an eye on.
Most other editors have added some sort of AI integrations, or you're able to download extensions to get some.

  - tab completion
  - ai sidebar/agent panels
    - these can feel very different depending on the editor and extension you're using

3. CLI tools
Note: with these, you have to start thinking about permissions
- github copilot CLI
- claude code
- codex CLI
- opencode CLI

4. desktop apps build on top of CLI tools
- Codex App
- Opencode App
- T3 Code

# Added functionalities/capabilities that exist
I find it best to think of these as custom/context specific configuration you can define for the various harnesses and interfaces.

- Agents(sometimes called modes)
- rules/agents.md/copilot-instruction
- tools & toolcalls
- MCP servers
- skills
- lsp servers
- hooks
- Agent Client Protocol
- https://agentclientprotocol.com/get-started/introduction

# Examples

# Potential Dev Workflow with AI

For real work, do not treat AI like a slot machine.

1. Plan. You must define parameters, architecture, control flow, and systems.
2. ai writes the implementation
3. human evaluates the output, refines it, and ensures the structure is sound.

As always, the goal should always be to produce simple, understandable code. If you don't even understand what the ai produced, that's unacceptable because you will be held responsible for it regardless.

# Some Practical Takeaways

Note: Always remember that AI is non deterministic in nature, so a healthy degree of skepticism is required even when you're doing "all the right things".

- Helpful for code review (with the right tools in place)
- semantic search
- quickly building proof of concepts that you don't feel bad about throwing away
- learning (only if you're not lazy about it)
- summarizing
- searching docs
- finding and cloning existing patterns
- placeholder data
- well known, repetitive, and easily verifiable wide reaching changes

# More Resources

1. Prompts

- https://developers.openai.com/api/docs/guides/prompt-guidance
- https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices

2. Articles

- https://www.aihero.dev/posts (cringe name, but this guy is also well known for teaching typescript)

3. Skills

- https://skills.sh/
- https://github.com/mattpocock/skills

4. Agent Client Protocol

- https://agentclientprotocol.com/get-started/introduction
