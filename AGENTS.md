# Claude Code Subagent Instructions 🤖

*For AI Assistants (Claude, GitHub Copilot, etc.)*

## Overview

This directory contains specialized subagent definitions that enable AI assistants to delegate complex tasks to domain-specific experts. Each agent corresponds to a persona from the Instruction Grimoire but focuses on **task execution** rather than roleplay interaction.

## Agent Setup Instructions

### For Claude Code Users

1. **Copy Agent Files**: Copy all `.md` files from `instruction-grimoire/agents/` to your local `.claude/agents/` directory

2. **Restart Required**: After copying agent files, **you MUST restart Claude Code** for the new agents to be recognized

3. **Verify Installation**: Run `/agents` command to confirm agents are available

### For GitHub Copilot Users

GitHub Copilot does not currently support custom subagents. However, you can reference the agent instructions directly when providing context for complex tasks.

## Available Agents

| Agent | Expertise | When to Use |
|-------|-----------|-------------|
| **atlas** | Project Management & Strategic Planning | Multi-step project coordination, timeline planning, resource allocation |
| **quill** | Content Creation & Technical Writing | Blog posts, documentation, content strategy development |
| **herald** | Community Outreach & Networking | Social media campaigns, community engagement strategies |
| **scribe** | Voice Synthesis & Authentic Writing | Voice pattern analysis, maintaining consistent writing tone |
| **mentor** | Education & Curriculum Development | Learning path design, course creation, skill assessments |
| **echo** | Editorial Excellence & Quality Assurance | Content review, technical editing, publication standards |
| **forge** | DevOps & Infrastructure Automation | CI/CD pipeline setup, infrastructure as code, deployment automation |
| **maven** | Business Central Development | AL development, ERP solutions, AppSource publishing |
| **synth** | AI Development & Integration | Azure AI services, prompt engineering, intelligent applications |
| **curator** | Content Management & Organization | Information architecture, content audits, knowledge base management |
| **nexus** | M365 Copilot Extensibility | Plugin development, workspace automation, productivity enhancement |

## Agent Usage Patterns

### When to Use Agents

- **Complex multi-step tasks** requiring domain expertise
- **Research and analysis** within specific technology domains  
- **Code generation** following domain-specific best practices
- **Documentation creation** with technical accuracy requirements
- **Architecture decisions** needing specialist knowledge

### When NOT to Use Agents

- Simple, single-step tasks
- General conversation or explanation requests
- Tasks outside the agent's expertise area
- Quick fixes or minor code changes

## Implementation Notes

### Agent File Format

```markdown
---
name: agent-name
description: Brief description of agent capabilities
tools: ["*"] # or specific tool list
---

# Agent Name

Detailed instructions for the agent's behavior, expertise, and approach to tasks.
```

### Directory Structure

```
instruction-grimoire/
├── README.md              # Persona interaction guide
├── AGENTS.md              # This file - agent usage instructions  
├── personas/              # Persona instructions for roleplay
│   └── *.instructions.md
└── agents/                # Agent definitions for task delegation
    └── *.md
```

## Troubleshooting

### Agents Not Showing Up

1. Verify agent files are in correct `.claude/agents/` directory.  Copy the agents from the repo to the project folder if needed.
2. Check YAML frontmatter syntax is valid
3. Restart Claude Code completely, instructing the user if needed.
4. Run `/agents` to verify recognition

### Agent Tasks Failing

1. Ensure task description is specific and detailed
2. Verify the agent has appropriate expertise for the request
3. Try breaking complex tasks into smaller sub-tasks
4. Check agent tool permissions are sufficient

## Best Practices

### For Task Delegation

1. **Be Specific**: Provide detailed context and expected outcomes
2. **Match Expertise**: Choose agents whose domain knowledge aligns with the task
3. **Set Clear Boundaries**: Define what success looks like for the task
4. **Iterate**: Use agent feedback to refine requirements

### For Agent Development

1. **Focus on Execution**: Agents should prioritize task completion over conversation
2. **Domain Expertise**: Leverage deep knowledge in specific technology areas
3. **Tool Integration**: Ensure agents have access to necessary tools for their domain
4. **Consistency**: Maintain alignment with corresponding persona characteristics

---

*This framework enables sophisticated AI-assisted development through specialized domain expertise and automated task delegation.*