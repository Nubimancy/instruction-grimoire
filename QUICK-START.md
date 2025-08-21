# Quick Start Guide 🚀

*Get up and running with the Instruction Grimoire in 5 minutes*

## For Claude Code Users

### 1. Install Agents (One-Time Setup)

Copy all agent files to your project's Claude Code agents directory:

```powershell
# Run from project root directory
Copy-Item "instruction-grimoire\agents\*.md" ".claude\agents\" -Force
```

After copying, **restart Claude Code** for agents to be recognized.

### 2. Verify Agent Installation

```bash
# Check if agents are available
/agents
```

You should see: atlas, conductor, curator, echo, forge, herald, maven, mentor, nexus, quill, scribe, synth

### 3. Usage Patterns

**🎭 Persona Mode** (Direct Interaction):
```
Hey Atlas, what's your take on this project timeline?
Can you respond as Forge and help me design this CI/CD pipeline?
```

**🤖 Agent Mode** (Behind-the-scenes):
```
Help me create a content strategy for Q1 2025
[Claude uses quill agent automatically]

Optimize this DevOps workflow
[Claude uses forge agent automatically]
```

## For GitHub Copilot Users

### 1. Reference Persona Files

Load persona context by referencing the instruction files:

```
@instruction-grimoire/personas/project-management.instructions.md

Help me plan this project using Atlas's strategic approach
```

### 2. Copy Relevant Context

Since Copilot doesn't support custom agents, copy relevant sections from agent files when needed:

```
Using the expertise from instruction-grimoire/agents/forge.md, 
help me set up a CI/CD pipeline for this project
```

## Quick Reference

| Need | Claude Code | GitHub Copilot |
|------|-------------|----------------|
| **Project Planning** | Ask for help (atlas agent auto-used) | `@instruction-grimoire/personas/project-management.instructions.md` |
| **Content Strategy** | Ask for help (quill agent auto-used) | `@instruction-grimoire/personas/content-planner.instructions.md` |
| **DevOps Help** | Ask for help (forge agent auto-used) | `@instruction-grimoire/personas/devops-engineer.instructions.md` |
| **Direct Roleplay** | "Hey Atlas, what do you think..." | "Respond as Atlas from this context..." |

## Available Personas & Agents

| Character | Expertise | Persona File | Agent File |
|-----------|-----------|--------------|------------|
| 🎯 **Atlas** | Project Management | `personas/project-management.instructions.md` | `agents/atlas.md` |
| 🎭 **Conductor** | Multi-Agent Orchestration | `personas/conductor.md` | `agents/conductor.md` |
| 📝 **Quill** | Content Creation | `personas/content-planner.instructions.md` | `agents/quill.md` |
| 📣 **Herald** | Community Outreach | `personas/community-outreach.instructions.md` | `agents/herald.md` |
| 📜 **Scribe** | Voice Synthesis | `personas/scribe.instructions.md` | `agents/scribe.md` |
| 📚 **Mentor** | Education Design | `personas/education-planning.instructions.md` | `agents/mentor.md` |
| ✏️ **Echo** | Editorial Excellence | `personas/editor.instructions.md` | `agents/echo.md` |
| 🔧 **Forge** | DevOps Engineering | `personas/devops-engineer.instructions.md` | `agents/forge.md` |
| 🏰 **Maven** | Business Central | `personas/business-central-developer.instructions.md` | `agents/maven.md` |
| 🤖 **Synth** | AI Development | `personas/ai-developer.instructions.md` | `agents/synth.md` |
| 📚 **Curator** | Content Organization | `personas/curator.instructions.md` | `agents/curator.md` |
| ⚙️ **Nexus** | M365 Copilot | `personas/m365-copilot-extensibility.instructions.md` | `agents/nexus.md` |

## Common Usage Examples

### Claude Code

```bash
# Content planning session
"I need to create a blog post series about Azure AI integration"
# → quill agent automatically helps plan content strategy

# Project coordination
"Help me break down this Q1 initiative into manageable sprints"
# → atlas agent automatically creates project structure

# Code review and optimization
"Review this DevOps pipeline and suggest improvements"
# → forge agent automatically analyzes and optimizes
```

### GitHub Copilot

```bash
# Load specific context first
@instruction-grimoire/personas/ai-developer.instructions.md

# Then request help
"Using Synth's expertise, help me integrate Azure OpenAI into this app"

# For multiple contexts
@instruction-grimoire/personas/project-management.instructions.md
@instruction-grimoire/personas/devops-engineer.instructions.md

"Help me plan and implement CI/CD for this project"
```

## Troubleshooting

### Claude Code Agents Not Working

1. **Check installation**: Agents must be in `.claude\agents\` (project directory)
2. **Restart required**: Always restart Claude Code after copying agent files
3. **Verify with**: `/agents` command should list all 11 agents

### GitHub Copilot Context Issues

1. **File references**: Use `@instruction-grimoire/personas/filename.md` format
2. **Context size**: For large contexts, copy relevant sections instead of entire files
3. **Multiple personas**: Reference multiple files when needing combined expertise

---

**🎯 Ready to start?** Pick your AI assistant, choose your persona, and begin your Nubimancy adventure!