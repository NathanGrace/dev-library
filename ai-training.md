 
 # Goal of this Training:
 - AI crash course
 - Encourage experimentation 
 - 
 - replace fear with optimism
 - 

# Core Concepts (models, tokens, context)
  - Models
  - Tokens
  - Context window
    
  
  
  
  
# Harnesses and Interfaces for day to day use
1. Normal chat apps
I think we're basically only supposed to use the copilot chat cause it has data security, but in general chat apps are probably what we're all most familiar with and aware of. A lot of these exist.
  
  - chatgpt.com
  - copilot.com
  - claude.ai
  - gemini.google.com
  - t3.chat

2. IDE features and/or extensions
Cursor, windsurf, antigravity, zed
  - tab completion
  - 

3. CLI tools
  Note: with these, you have to start thinking about permissions
  - github copilot CLI
  - claude code
  - codex cli
  - opencode
4. desktop apps build on top of CLI tools
  - 





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
