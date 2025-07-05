# Context Patterns: Common Problems and Solutions

*Recognizing and fixing typical AI workflow issues*

## The Four Context Failure Modes

Through experimentation, I've identified four main ways AI workflows break down. Learning to recognize these patterns helps you fix problems quickly.

## 1. Context Poisoning

**What it looks like:**
- AI confidently repeats incorrect information
- Mistakes persist even when you try to correct them
- AI builds on wrong assumptions throughout the conversation

**Example:**
```
You: "Create a user registration form for our React app"
AI: "I'll create a registration form using Vue.js components..."
You: "No, we're using React"
AI: "Sure, here's the React version with Vue.js syntax..."
```

**Why it happens:**
Wrong information gets "stuck" in the AI's context and influences all subsequent responses.

**Solutions:**
- **Reset context**: Start a fresh conversation
- **Be explicit**: "Stop. We are using React, not Vue. Confirm you understand before proceeding."
- **Validate early**: Check understanding before the AI does significant work

## 2. Context Distraction

**What it looks like:**
- AI focuses on irrelevant details from earlier in the conversation
- Responses reference old context instead of current needs
- AI seems to "remember" things that aren't important anymore

**Example:**
```
[Earlier: Discussion about database optimization]
You: "Now help me write a user interface for login"
AI: "For the login UI, we should consider database indexing strategies..."
```

**Why it happens:**
AI gives too much weight to conversation history vs. current task requirements.

**Solutions:**
- **Clear transitions**: "Now moving to a different topic: user interface design"
- **Restate context**: Explicitly provide current task context
- **Use phases**: Break work into distinct phases with clear boundaries

## 3. Context Confusion

**What it looks like:**
- AI makes poor choices about tools or approaches
- Selects irrelevant information from available context
- Seems to misunderstand what's important for the current task

**Example:**
```
You: "Debug this JavaScript error" [provides error message]
AI: "Let me help you set up a new project structure instead..."
```

**Why it happens:**
Too much irrelevant information in context, AI can't filter effectively.

**Solutions:**
- **Focused context**: Provide only information relevant to current task
- **Clear priorities**: "The most important thing right now is..."
- **Explicit guidance**: "Focus on the error message, ignore other code for now"

## 4. Context Clash

**What it looks like:**
- AI gives contradictory responses
- Recommendations conflict with earlier advice
- AI seems uncertain or changes approach mid-task

**Example:**
```
AI: "Use async/await for this API call"
[Later in same conversation]
AI: "Actually, promises are better here, avoid async/await"
```

**Why it happens:**
Conflicting information in context creates uncertainty about best approach.

**Solutions:**
- **Resolve conflicts explicitly**: "Which approach do you recommend and why?"
- **Prioritize sources**: "Follow the official documentation over blog posts"
- **Single source of truth**: Establish clear guidelines for the task

## Prevention Strategies

### 1. Structure Your Context
Instead of one long conversation, break into phases:
- **Setup phase**: Establish context and approach
- **Execution phase**: Do the work
- **Validation phase**: Check results

### 2. Use Validation Checkpoints
Regular check-ins prevent problems from compounding:
- "Do you understand what I'm asking for?"
- "Is this approach still on track?"
- "Does this result match what we discussed?"

### 3. Manage Information Flow
- **Just-in-time loading**: Provide information when needed, not all upfront
- **Relevance filtering**: Include only context relevant to current task
- **Clear boundaries**: Separate different workstreams or topics

### 4. Monitor for Warning Signs
Watch for these early indicators:
- AI asks for information you already provided
- Responses seem off-topic or irrelevant
- AI suggests approaches that don't fit your constraints
- Quality degrades as conversation continues

## Quick Fixes

When you notice context problems:

**Immediate reset:**
```
"Stop. Let me clarify the current task:
- Goal: [clear objective]
- Context: [essential information only]
- Approach: [preferred method]
Please confirm you understand before proceeding."
```

**Context refresh:**
```
"Let's start fresh on this specific task. Here's what matters:
[Provide only relevant context for current work]"
```

**Validation checkpoint:**
```
"Before continuing, please explain:
1. What you're trying to accomplish
2. Why you chose this approach
3. How confident you are (1-10)"
```

## Advanced Patterns

### Agent Delegation
For complex tasks, use specialized "agents" for different parts:
- **Research agent**: Gather information
- **Planning agent**: Design approach
- **Execution agent**: Implement solution
- **Validation agent**: Check quality

This prevents context pollution between different types of work.

### Context Budgeting
Actively manage how much information you provide:
- **Essential**: Must-have context for the task
- **Helpful**: Nice-to-have background information
- **Reference**: Available if needed, but not actively processed

### Dynamic Loading
Instead of front-loading all context, provide information as needed:
- Start with minimal essential context
- Add details when AI asks or when needed for current step
- Remove irrelevant information as task evolves

## Measuring Success

You'll know these patterns are working when:
- **Fewer corrections**: Less time spent fixing AI mistakes
- **Better consistency**: Similar tasks produce similar quality results
- **Improved focus**: AI stays on track for complex, multi-step work
- **Predictable quality**: You can rely on AI for important tasks

The goal isn't perfect AI responses, but predictably useful ones that you can build workflows around.