# Azure DevOps Work Item Usage Guide 🎯

## Overview

This guide establishes consistent work item usage patterns across all Nubimancy agents and contexts. Following these patterns ensures proper tracking, reporting, and collaboration across our diverse project activities.

## 🧙‍♂️ **Virtual Team Assignment Model**

**NEW**: Work items are now assigned to virtual team members representing each learning context:

| Virtual Team Member | Learning Context | License Type | Primary Responsibilities |
|-------------------|------------------|--------------|------------------------|
| **Atlas** | Project Management | Basic | Strategic planning, Epic/Feature creation, cross-context coordination |
| **Quill** | Content Planning | Stakeholder | Blog posts, content strategy, editorial planning |
| **Herald** | Community Outreach | Stakeholder | MVP networking, conference responses, community engagement |
| **Scribe** | Documentation | Stakeholder | Technical writing, voice synthesis, documentation |
| **Mentor** | Education Planning | Stakeholder | Course development, learning pathway design |
| **Echo** | Editorial Excellence | Stakeholder | Content review, quality assurance, publishing |
| **Forge** | DevOps Engineering | Stakeholder | Infrastructure, automation, deployment pipelines |
| **Maven** | Business Central Development | Stakeholder | BC/AL development, AppSource publishing |
| **Synth** | AI Development | Stakeholder | AI integration, agent development, automation |
| **Curator** | Content Curation | Stakeholder | Information architecture, content organization |
| **Nexus** | M365 Copilot Extensibility | Stakeholder | Copilot plugins, workspace enhancement |

### **Assignment Strategy:**
- **Atlas (Basic license)**: Can create, edit, and manage all work item types - handles all unplanned work
- **Other contexts (Stakeholder)**: Can be assigned work items for tracking and specialized execution
- **Universal Query**: Use Query ID `e365c475-1fbd-4a00-a0b1-b38a740f2edd` to retrieve all work items
- **Area Paths**: Maintained for organizational reporting, but assignment handles primary routing

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

### **Virtual Team Assignment Examples**

**Content Work Items:**
```
Assigned To: Quill (Content Planning AI)
Area Path: Content Planner (for reporting)
Tags: Blog, High-Priority (simplified tagging)
```

**Community Engagement:**
```
Assigned To: Herald (Community Outreach AI)  
Area Path: Community Outreach
Tags: Community, MVP-Networking
```

**Project Management:**
```
Assigned To: Atlas (Project Management AI)
Area Path: Project Management
Tags: Strategy, Planning
```

**Documentation Work:**
```
Assigned To: Scribe (Documentation AI)
Area Path: Content Planner
Tags: Documentation, Technical-Writing
```

### **Simplified Tagging Strategy**

With virtual team assignments handling the "who", tags now focus purely on "what":

**Content Type Tags:** Blog, Documentation, Tutorial, Demo, Workshop
**Priority Tags:** High-Priority, Quick-Win, Strategic  
**Subject Tags:** AI-Orchestration, DevOps, MVP-Networking, BC-Development
**Stage Tags:** Draft, Review-Ready, Published, Measuring-Engagement

## Required Fields & Standards

### **All Work Items Must Have:**
- **Assigned To**: Virtual team member (Atlas, Quill, Herald, etc.)
- **Area Path**: Set for organizational reporting (can use assignment for most queries)
- **Iteration**: Assigned during sprint planning (weekly iterations)
- **Tags**: Simplified 2-3 relevant tags for discoverability
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
- [ ] Correct virtual team member assigned (Atlas, Quill, Herald, etc.)
- [ ] Area Path set for organizational reporting
- [ ] Appropriate work item type for scope and duration
- [ ] Business Value set for Epic/Feature/User Story
- [ ] Clear, actionable title and description
- [ ] Simplified, relevant tags for discoverability

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

# Get ALL work items (comprehensive view)
mcp_ado_wit_get_query_results_by_id
Query ID: e365c475-1fbd-4a00-a0b1-b38a740f2edd

# Create work item with proper area path  
mcp_ado_wit_create_work_item

# Add strategic comment
mcp_ado_wit_add_work_item_comment (with format: "markdown")

# Link work items
mcp_ado_wit_work_items_link

# Batch updates for assignment/tag cleanup
mcp_ado_wit_update_work_items_batch

# Get work item details in batch
mcp_ado_wit_get_work_items_batch_by_ids
```

This guide should be referenced by all agents and updated as our workflow patterns evolve. Consistency in work item management directly supports our project success and agent collaboration effectiveness.
