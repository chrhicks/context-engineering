# Context Engineering Planning Template v2.0

**Version**: 2.0 (Updated July 5, 2025)  
**Based on**: Latest Context Engineering research findings  
**Incorporates**: Master/child delegation, failure mode prevention, dynamic context loading

## Task Overview

### Primary Objective
**What**: [Clear, specific description of what needs to be built]  
**Why**: [Business/user value this delivers]  
**Success Criteria**: [Measurable outcomes that define completion]

### Context Engineering Strategy

#### Context Management
- **Context Budget**: [Maximum complexity/tokens allocated to this task]
- **Loading Strategy**: Dynamic (just-in-time) vs. Front-loaded
- **Failure Prevention**: 
  - ✅ Poisoning Check: Validate all generated content for accuracy
  - ✅ Distraction Mitigation: Focus on current task over historical context  
  - ✅ Confusion Reduction: Filter irrelevant information
  - ✅ Clash Resolution: Handle contradictory requirements explicitly

#### Agent Strategy
- **Delegation Pattern**: 
  - [ ] Single Agent (simple, isolated task)
  - [ ] Master/Child (complex task requiring sub-specialization)
  - [ ] Multi-Agent (parallel, independent work streams)
- **Context Isolation**: [How to prevent context pollution between agents]
- **Coordination Method**: [How agents communicate results without polluting context]

## Chain-of-Thought Planning

### Problem Analysis
**Current State**: [What exists now]  
**Desired State**: [What we want to achieve]  
**Gap Analysis**: [What needs to change]

### Approach Reasoning
**Primary Approach**: [Chosen implementation strategy]  
**Why This Approach**: [Reasoning for selection]  
**Alternatives Considered**: [Other options and why they were rejected]  
**Risk Assessment**: [What could go wrong and mitigation strategies]

### Implementation Strategy
**Step 1**: [First concrete action]  
- **Input Required**: [What information/resources needed]
- **Output Produced**: [What this step delivers]
- **Validation**: [How to verify this step succeeded]

**Step 2**: [Second concrete action]  
- **Input Required**: [Dependencies from previous steps]
- **Output Produced**: [Deliverables from this step]
- **Validation**: [Success criteria]

**Step N**: [Continue for all major steps]

## Context Flow Management

### Information Dependencies
**Inputs Required**:
- [Information needed from previous work]
- [External dependencies]
- [Assumptions that must be validated]

**Outputs Produced**:
- [What this task provides to future work]
- [Knowledge/artifacts generated]
- [Decisions made that affect downstream work]

### Context Inheritance
**From Previous Tasks**: [What context carries forward]  
**To Future Tasks**: [What context this task will provide]  
**Side Effects**: [What else this task affects]

## Validation Framework

### Pre-Execution Validation
- [ ] **Understanding Check**: Agent confirms task comprehension (>8/10 confidence)
- [ ] **Context Readiness**: All required information available and conflict-free
- [ ] **Resource Allocation**: Sufficient context budget for task complexity
- [ ] **Approach Validation**: Implementation strategy reviewed and approved

### Execution Checkpoints
- [ ] **25% Checkpoint**: [Specific milestone and validation criteria]
- [ ] **50% Checkpoint**: [Mid-point validation and course correction opportunity]
- [ ] **75% Checkpoint**: [Near-completion validation and final adjustments]

### Post-Execution Validation
- [ ] **Deliverable Check**: All specified outputs created and meet criteria
- [ ] **Integration Test**: New work integrates properly with existing system
- [ ] **Quality Validation**: Code/output meets established standards
- [ ] **Documentation Update**: All relevant documentation updated
- [ ] **Context Cleanup**: Temporary information removed, essentials preserved

## Error Recovery Procedures

### Context Failure Detection
**If Context Poisoning Detected**: [Steps to quarantine and correct false information]  
**If Context Distraction Occurs**: [How to refocus on current task]  
**If Context Confusion Arises**: [Process to clarify and filter information]  
**If Context Clash Identified**: [Procedure to resolve contradictions]

### Rollback Triggers
- Confidence drops below 7/10 during execution
- Validation checkpoint fails
- Context failure mode detected
- Resource budget exceeded by >50%

### Recovery Actions
1. **Pause Execution**: Stop current work immediately
2. **Diagnose Issue**: Identify specific failure mode or problem
3. **Context Reset**: Clear problematic context, reload essentials
4. **Approach Adjustment**: Modify strategy based on learnings
5. **Resume with Monitoring**: Continue with increased validation frequency

## Implementation Notes

### Agent Coordination (if using Master/Child pattern)
**Master Agent Responsibilities**:
- Overall progress coordination
- Context boundary management
- Result integration and validation
- Quality assurance across all work

**Child Agent Responsibilities**:
- Focused execution of delegated sub-tasks
- Isolated context management
- Clear result communication to master
- No cross-contamination with other child contexts

### Dynamic Context Loading
**Load on Demand**: [Specify what information to load at each checkpoint]  
**Pruning Strategy**: [What to remove when approaching context limits]  
**Essential Preservation**: [Information that must never be lost]

---

## Execution Log

### Planning Phase
- **Start Time**: [Timestamp]
- **Planning Duration**: [Time spent on planning]
- **Confidence Level**: [1-10 rating of plan quality]
- **Questions/Clarifications**: [Any unclear aspects]

### Implementation Phase
- **Execution Start**: [Timestamp]
- **Checkpoints Completed**: [List with timestamps]
- **Issues Encountered**: [Problems and resolutions]
- **Final Completion**: [Timestamp and success confirmation]

### Retrospective
- **What Worked Well**: [Successful aspects of approach]
- **What Could Improve**: [Areas for enhancement]
- **Context Engineering Effectiveness**: [How well did the framework help]
- **Lessons for Future Tasks**: [Insights to carry forward]

---

**Template Version**: 2.0  
**Last Updated**: July 5, 2025  
**Research Basis**: Context Engineering production-validated patterns (9.8/10)