# Multi-Agent System Health Check ✅

*Quick validation checklist before starting complex projects*

## Pre-Project Validation

### 1. Agent Installation Check
```bash
# In Claude Code, run:
/agents

# Expected output: 12 agents
# atlas, conductor, curator, echo, forge, herald, maven, mentor, nexus, quill, scribe, synth
```

**✅ Success**: All 12 agents listed  
**❌ Failure**: Missing agents → Copy from `instruction-grimoire/agents/` to `.claude/agents/` and restart

### 2. Agent File Integrity
```powershell
# Quick file count check
Get-ChildItem ".claude\agents\*.md" | Measure-Object | Select-Object Count
Get-ChildItem "instruction-grimoire\agents\*.md" | Measure-Object | Select-Object Count

# Should both return Count: 12
```

### 3. Context Loading Test
Ask Claude Code: **"What agents are available and what are their specializations?"**

**✅ Success**: Claude lists all agents with accurate descriptions  
**❌ Failure**: Missing or incorrect agent info → Check agent file syntax

## Quick Functionality Tests

### Test 1: Simple Agent Task
**Request**: "Help me plan a blog post about Azure AI integration"  
**Expected**: Quill agent should activate and provide content strategy

### Test 2: Multi-Agent Coordination
**Request**: "I need to plan and implement a DevOps pipeline for a Business Central extension"  
**Expected**: Conductor should coordinate between atlas (planning), maven (BC expertise), and forge (DevOps)

### Test 3: Quality Review Chain
**Request**: "Review this technical documentation for publication"  
**Expected**: Echo agent should activate for editorial review

## Common Issues & Fixes

### Agents Not Activating
- **Symptom**: Claude responds generically instead of using specialized agents
- **Fix**: Be more specific about domain (e.g., "DevOps help" → "Design CI/CD pipeline")

### Agent Handoffs Failing
- **Symptom**: Context lost between agents, disconnected responses
- **Fix**: Use conductor for complex projects, provide complete project memory

### Quality Gates Skipped
- **Symptom**: Output lacks domain-specific quality checks
- **Fix**: Explicitly request quality review or include review agents in workflow

### Context Overload
- **Symptom**: Agents confused by too much context
- **Fix**: Break into phases, provide only relevant context per phase

## Performance Benchmarks

### Response Quality Indicators
- **Domain Expertise**: Responses use domain-specific terminology and patterns
- **Practical Focus**: Actionable advice rather than generic guidance
- **Context Awareness**: References project constraints and requirements
- **Handoff Quality**: Smooth transitions between agents with preserved context

### Efficiency Metrics
- **Single-Domain Tasks**: Direct agent activation (no coordinator overhead)
- **Multi-Domain Tasks**: Clear coordination plan with defined handoffs
- **Quality Tasks**: Appropriate review agents included in workflow
- **Documentation**: Project memory updated with key decisions

## Troubleshooting Commands

### Claude Code Diagnostics
```bash
# Check agent availability
/agents

# Test agent activation (try different domains)
"Design a CI/CD pipeline"  # Should activate forge
"Plan a content calendar"  # Should activate quill
"Coordinate a complex project"  # Should activate conductor
```

### File System Validation
```powershell
# Verify agent files exist and have content
Get-ChildItem ".claude\agents\*.md" | ForEach-Object { 
    Write-Host "$($_.Name): $((Get-Content $_.FullName | Measure-Object -Line).Lines) lines" 
}
```

## Ready-to-Test Scenarios

### Scenario 1: Content Pipeline
"Create a comprehensive blog post about Azure AI integration in Business Central, including community promotion strategy"

**Expected Flow**: conductor → quill (strategy) → scribe (voice) → echo (review) → herald (promotion)

### Scenario 2: Development Project
"Plan and implement automated testing for Business Central extensions with Azure DevOps integration"

**Expected Flow**: conductor → atlas (planning) → maven (BC expertise) → forge (DevOps) → curator (documentation)

### Scenario 3: Learning Initiative
"Design a learning path for Business Central developers to adopt AI-assisted development practices"

**Expected Flow**: mentor (curriculum) → synth (AI expertise) → maven (BC context) → echo (quality) → curator (organization)

---

**🎯 System Status**: Ready for complex multi-agent collaboration!