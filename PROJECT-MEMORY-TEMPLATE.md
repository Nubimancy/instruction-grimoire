# Project Memory Template 🧠

*Standardized context capture for multi-agent collaboration*

## Project Context Block

```yaml
project_memory:
  # Basic Information
  name: "Project Name"
  phase: "discovery|design|implementation|delivery"
  complexity: "simple|moderate|complex|enterprise"
  
  # Architecture Decisions
  architecture_decisions:
    - decision: "Technology choice rationale"
      impact: "What this affects"
      constraints: "Limitations this creates"
  
  # Resource Constraints
  resource_constraints:
    timeline: "Deadline and milestones"
    budget: "Financial limitations"
    team_size: "Available resources"
    technical_debt: "Existing system constraints"
  
  # Integration Patterns
  integration_patterns:
    - system: "External system name"
      method: "API|webhook|batch|realtime"
      constraints: "Rate limits, auth requirements"
  
  # Quality Gates
  quality_gates:
    security: "Security requirements and compliance"
    performance: "Performance targets and SLAs"
    usability: "User experience standards"
    maintainability: "Code quality and documentation standards"
  
  # Agent Handoff History
  agent_handoffs:
    - from: "previous_agent"
      to: "next_agent"
      context_transferred: "What information was passed"
      decisions_made: "Key decisions and rationale"
      deliverables: "What was completed"
```

## Context Transfer Checklist

### Pre-Handoff (Sending Agent)
- [ ] All quality gates met for current phase
- [ ] Key decisions documented with rationale
- [ ] Integration points and constraints identified
- [ ] Risk factors and mitigation strategies noted
- [ ] Next agent requirements clearly specified

### During Handoff (Receiving Agent)
- [ ] Project memory reviewed and understood
- [ ] Questions about context clarified
- [ ] Additional requirements or constraints identified
- [ ] Success criteria for current phase confirmed
- [ ] Communication preferences established

### Post-Handoff (Conductor)
- [ ] Handoff completed successfully
- [ ] Project memory updated with new context
- [ ] Progress tracking updated
- [ ] Next phase/agent identified
- [ ] Risk monitoring established

## Context Categories by Agent Type

### For Technical Agents (forge, maven, synth)
Required: architecture_decisions, integration_patterns, resource_constraints  
Optional: quality_gates, compliance requirements

### For Content Agents (quill, herald, echo)
Required: brand_guidelines, audience_profile, publishing_constraints  
Optional: SEO requirements, distribution channels

### For Planning Agents (atlas, conductor)
Required: business_objectives, resource_constraints, stakeholder_requirements  
Optional: risk_tolerance, success_metrics

## Usage Examples

### Simple Project
```yaml
project_memory:
  name: "Blog Post - Azure AI Integration"
  phase: "implementation"
  complexity: "simple"
  quality_gates:
    editorial: "Technical accuracy, readability"
  agent_handoffs:
    - from: "quill"
      to: "echo"
      context_transferred: "Draft content, target audience"
```

### Complex Project
```yaml
project_memory:
  name: "BC Copilot Community Platform Migration"
  phase: "design"
  complexity: "enterprise"
  architecture_decisions:
    - decision: "GitHub Pages + Jekyll for hosting"
      impact: "Static site generation, limited dynamic features"
      constraints: "No server-side processing, markdown-only content"
  resource_constraints:
    timeline: "Q1 2025 completion"
    team_size: "1 developer + AI agents"
    technical_debt: "Legacy content format conversion needed"
  integration_patterns:
    - system: "Azure DevOps"
      method: "webhook"
      constraints: "API rate limits, authentication tokens"
```