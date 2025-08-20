# Azure DevOps Work Item Usage Guide 🎯

## Overview

This guide establishes consistent work item usage patterns across all Nubimancy agents and contexts. Following these patterns ensures proper tracking, reporting, and collaboration across our diverse project activities.

## Work Item Hierarchy & Usage

### **Epic** - Major Business Initiatives
- **Purpose**: Large strategic initiatives spanning months/quarters (Business Value: 75-100)
- **Duration**: 3-12 months
- **Examples**: "Supply Chain AppSource Suite", "Content Marketing & Thought Leadership"
- **Creation Pattern**: Atlas creates during strategic planning sessions
- **Area Path**: `Project Management` (strategic oversight)
- **States**: New → Planning → Active → Review → Closed

### **Feature** - Deliverable Components  
- **Purpose**: Major functional deliverables within an Epic (Business Value: 25-75)
- **Duration**: 2-8 weeks
- **Examples**: "Blog Series Planning", "Workshop Delivery Pipeline", "AppSource App Development"
- **Creation Pattern**: Atlas or agent leads create for multi-part initiatives
- **Area Path**: Matches primary responsible agent
- **Parent**: Epic
- **States**: New → Planning → Active → Review → Closed

### **User Story** - Specific Deliverables
- **Purpose**: Concrete deliverables providing direct business value (Business Value: 5-25)
- **Duration**: 1-4 weeks
- **Examples**: Individual blog posts, workshop responses, documentation pages
- **Creation Pattern**: Any agent can create for their domain
- **Area Path**: Agent's primary area
- **Parent**: Feature (preferred) or Epic (if no Feature exists)
- **States**: New → Planning → Active → Review → Closed

### **Task** - Implementation Work
- **Purpose**: Technical implementation steps for User Stories (no Business Value)
- **Duration**: 1-5 days
- **Examples**: "Write first draft", "Create social media posts", "Set up repository"
- **Creation Pattern**: Agents create as needed for execution
- **Area Path**: Inherits from parent or agent's area
- **Parent**: User Story (required)
- **States**: To Do → Doing → Done

### **Bug** - Issue Resolution
- **Purpose**: Problems, corrections, or process improvements (no Business Value)
- **Duration**: 1-3 days
- **Examples**: "Fix area path violations", "Correct agent voice patterns"
- **Creation Pattern**: Any agent when issues discovered
- **Area Path**: Where the issue was found
- **Parent**: Any level where bug affects
- **States**: New → Active → Resolved → Closed

## Universal State Definitions

### **For Epic, Feature, User Story:**
- **New**: Item created but planning not yet started
- **Planning**: Requirements gathering, breakdown, research phase
- **Active**: Primary work in progress (drafting, implementing, engaging)
- **Review**: Quality assurance, feedback gathering, refinement phase
- **Closed**: Delivered, functional, and measuring outcomes/feedback

### **For Tasks:** 
- **To Do**: Task identified but not started
- **Doing**: Task actively being worked on
- **Done**: Task completed and verified

### **For Bugs:**
- **New**: Issue identified but not investigated
- **Active**: Investigation and fix in progress  
- **Resolved**: Fix implemented, awaiting verification
- **Closed**: Issue verified as resolved

## Agent-Specific Creation Patterns

### **Workflow Stage Tracking with Tags**

Since we use universal states across all work types, use **tags** to track specific workflow stages:

**Content Creation Workflow Tags:**
- `idea-stage`, `outline-stage`, `draft-stage`, `edit-stage`, `published`, `measuring-engagement`

**Community Outreach Workflow Tags:**  
- `opportunity-identified`, `outreach-planned`, `engaged`, `follow-up-pending`, `measuring-impact`

**Strategic Planning Workflow Tags:**
- `concept-phase`, `resource-planning`, `coordination-active`, `progress-monitoring`, `measuring-outcomes`

**Technical Development Workflow Tags:**
- `requirements-gathering`, `design-phase`, `implementation`, `testing-phase`, `deployed`, `measuring-performance`

### **Herald** (Community Outreach)
```
Area Path: "Community Outreach"
Typical Pattern: User Story → Tasks
- Workshop responses (User Stories)
- Community engagement activities (User Stories) 
- Follow-up coordination (Tasks)
Tags: Community, High-Priority, [Opportunity-Source]
```

### **Scribe** (Content Creation)  
```
Area Path: "Content Planner"
Typical Pattern: Feature → User Stories → Tasks
- Blog series (Features with multiple User Story posts)
- Individual content pieces (User Stories)
- Content creation tasks (Tasks: outline → draft → review → publish)
Tags: Blog, Content, [Content-Type], [Platform]
```

### **Atlas** (Project Management)
```  
Area Path: "Project Management"
Typical Pattern: Epic → Features → User Stories
- Strategic initiatives (Epics)
- Multi-part projects (Features)
- Process improvements (User Stories)
Tags: Planning, Strategy, Process-Improvement
```

### **Synth** (AI Development)
```
Area Path: "AI Development" 
Typical Pattern: Tasks under other agents' User Stories
- Technical implementation (Tasks)
- Agent context updates (User Stories)
- Process automation (User Stories)
Tags: Technical, Agent-Context, Automation
```

### **Other Agents** (Curator, Editor, etc.)
```
Area Path: Matches their primary domain
Follow same patterns as above based on work type
```

## Required Fields & Standards

### **All Work Items Must Have:**
- **Area Path**: Set according to agent patterns above
- **Iteration**: Assigned during sprint planning (weekly iterations)
- **Tags**: At least 2 relevant tags for discoverability
- **Clear Title**: Descriptive and actionable

### **Business Value Items (Epic/Feature/User Story):**
- **Business Value**: Numeric score based on hierarchy levels above
- **Description**: Clear success criteria and deliverables
- **Acceptance Criteria**: Specific definition of "done"

### **Implementation Items (Task/Bug):**
- **Clear Actions**: Specific steps to complete
- **Parent Link**: Always linked to higher-level work item
- **Time Estimate**: Realistic effort estimate

## MCP Integration Standards

### **Work Item Comments (All Agents)**
```markdown
ALWAYS use: format: "markdown" parameter
Follow shared protocol in grimoire/README.md
Include strategic context and next steps
Link related work items and external resources
```

### **Batch Operations**
```markdown
Use batch APIs when possible:
- mcp_ado_wit_get_work_items_batch_by_ids
- mcp_ado_wit_update_work_items_batch  
- mcp_ado_wit_work_items_link
```

### **Work Item Linking**
```markdown
Link related work items using:
- Parent/Child (hierarchical)
- Related (cross-cutting concerns)
- Successor/Predecessor (sequential dependencies)
```

## Board & Sprint Management

### **Epic Board Usage**
- Strategic overview and quarterly planning
- Business value tracking and ROI analysis
- Cross-functional initiative coordination

### **Feature Board Usage**  
- Medium-term deliverable management
- Resource allocation and capacity planning
- Dependency tracking between teams/agents

### **Sprint Planning**
- Task-level execution in weekly iterations
- Daily standup support and progress tracking
- Velocity measurement and improvement

### **Kanban Boards**
- Continuous flow for content and community work
- Real-time status updates and bottleneck identification
- Flexible priority adjustment as opportunities arise

## Quality Assurance Checklist

### **Before Creating Work Items:**
- [ ] Correct Area Path selected for agent domain
- [ ] Appropriate work item type for scope and duration
- [ ] Business Value set for Epic/Feature/User Story
- [ ] Clear, actionable title and description
- [ ] Relevant tags for discoverability

### **During Work Item Updates:**
- [ ] Comments use `format: "markdown"`
- [ ] Status changes reflect actual progress
- [ ] Links maintained to related work items
- [ ] Iteration assignments updated as needed

### **Work Item Completion:**
- [ ] All child items completed or reassigned
- [ ] Success criteria validated and documented
- [ ] Follow-up items created if needed
- [ ] Lessons learned captured in comments

## Escalation & Exception Handling

### **Area Path Violations**
- Immediate correction required using batch update APIs
- Document pattern in this guide to prevent recurrence
- Update agent instructions if systematic issue

### **Orphaned Work Items**
- All User Stories must have Epic or Feature parent
- All Tasks must have User Story parent
- Create missing hierarchy levels as needed

### **Capacity Overruns**
- Move work items to future iterations
- Reassess business value and priority
- Consider breaking down large items

---

## Implementation Guide: Custom States Setup

### **ADO Process Template Changes Required**
> **Note**: These changes require Project Administrator permissions in Azure DevOps and must be done through the web interface.

**Steps to implement universal states:**

1. **Navigate to Organization Settings → Process**
2. **Select your process template** (likely "Agile" or "Scrum")
3. **For Epic work item type:**
   - Edit states to: New → Planning → Active → Review → Closed
   - Set state categories: New(Proposed) → Planning(Proposed) → Active(InProgress) → Review(InProgress) → Closed(Completed)

4. **For Feature work item type:**
   - Same states as Epic: New → Planning → Active → Review → Closed

5. **For User Story work item type:**  
   - Same states as Epic: New → Planning → Active → Review → Closed

6. **Keep Task states as:** To Do → Doing → Done
7. **Keep Bug states as:** New → Active → Resolved → Closed

### **State Category Mapping**
- **Proposed**: New, Planning
- **InProgress**: Active, Review  
- **Completed**: Closed
- **Removed**: (keep existing Removed state)

### **Validation Steps**
- Test state transitions work correctly
- Verify board columns map to appropriate states
- Confirm reporting and queries still function
- Update team board configurations if needed

---

## Quick Reference Commands

### **Most Common MCP Operations:**
```markdown
# Get my work items
mcp_ado_wit_my_work_items

# Create work item with proper area path  
mcp_ado_wit_create_work_item

# Add strategic comment
mcp_ado_wit_add_work_item_comment (with format: "markdown")

# Link work items
mcp_ado_wit_work_items_link

# Batch updates
mcp_ado_wit_update_work_items_batch
```

This guide should be referenced by all agents and updated as our workflow patterns evolve. Consistency in work item management directly supports our project success and agent collaboration effectiveness.
