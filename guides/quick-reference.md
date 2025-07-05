# Context Engineering Quick Reference

*5-minute guide to better AI workflows*

## The Core Idea

Context Engineering is about managing information flow to AI agents systematically. Instead of throwing everything at the AI and hoping for the best, you structure how information gets loaded, processed, and maintained.

## When to Use This

- **Your AI workflows are inconsistent** - sometimes great, sometimes frustrating
- **Complex tasks often go off track** - AI gets confused or distracted
- **You're doing the same types of tasks repeatedly** - and want more predictable results

## Essential Patterns

### 1. Structure Your Requests
Instead of: "Build me a user authentication system"

Try this approach:
```
Context: Building auth for a web app, need JWT tokens, user registration/login
Success: Users can register, login, logout, with secure token handling
Constraints: Must integrate with existing database, 2-day timeline
Approach: Break into phases - database setup, auth endpoints, frontend integration
```

### 2. Break Complex Tasks Into Phases
- **Phase 1**: Setup and planning
- **Phase 2**: Core implementation  
- **Phase 3**: Integration and testing

Each phase should have clear success criteria.

### 3. Use Validation Checkpoints
Before moving forward, ask:
- "Do I understand what I'm supposed to do?" (confidence >8/10)
- "Are the current results on track?"
- "What could go wrong from here?"

### 4. Watch for Context Problems
**Red flags that indicate issues:**
- AI repeats incorrect information confidently
- Gets distracted by irrelevant details
- Makes poor tool/approach choices
- Gives contradictory responses

**Quick fix:** Reset context, reload only essential information.

## The Planning Template

Use the [planning template](../templates/planning-template.json) for complex tasks. Key sections:

- **Execution Context**: What the AI needs to know upfront
- **Phases**: Break work into manageable chunks
- **Validation**: How to check progress and quality
- **Agent Strategy**: When to use multiple approaches

## Common Mistakes to Avoid

❌ **Loading everything upfront** - causes information overload  
✅ **Load information just-in-time** - as you need it

❌ **No validation checkpoints** - problems compound  
✅ **Regular check-ins** - catch issues early

❌ **Mixing different workstreams** - causes confusion  
✅ **Keep different tasks separate** - use clear boundaries

## Quick Start

1. **Pick a frustrating AI workflow** you deal with regularly
2. **Try the planning template** on your next instance
3. **Pay attention to validation checkpoints** - don't skip them
4. **Note what works differently** compared to your usual approach

## When It's Working

You'll notice:
- More consistent results across similar tasks
- Fewer "wait, that's not what I wanted" moments
- Better handling of complex, multi-step work
- Less time spent fixing AI mistakes

The goal isn't perfect AI - it's predictably good AI that you can rely on for real work.