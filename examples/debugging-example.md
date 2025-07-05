# Debugging Example: Performance Issue Investigation

*How structured context prevents debugging sessions from going in circles*

## The Problem

Web application suddenly became slow. Users complaining about 5-10 second page loads that used to be instant.

## Before: Typical Debugging Chaos

**My approach:**
```
"My web app is really slow all of a sudden. Can you help me figure out what's wrong?"
```

**What happened:**
- AI started suggesting generic performance optimizations
- Went down rabbit holes checking frontend bundle sizes
- Suggested database indexing without understanding our setup
- Spent 2 hours checking things that weren't the problem
- AI kept forgetting what we'd already ruled out
- Eventually found the issue (new N+1 query) but wasted lots of time

**Time to resolution:** 3 hours of frustration

## After: Structured Debugging Approach

### Context Setup
```
Problem: Web app page loads increased from <1s to 5-10s starting yesterday
Environment: Node.js/Express backend, React frontend, PostgreSQL database
Recent changes: Deployed new user profile feature 2 days ago
Symptoms: 
- All pages affected, not just new feature
- Database CPU usage normal
- Frontend bundle size unchanged
- No error logs

Success criteria: Identify root cause and restore <2s page loads
Constraints: Production system, need to minimize investigation impact

Debugging strategy:
- Phase 1: Isolate the bottleneck (frontend vs backend vs database)
- Phase 2: Deep dive into the identified layer
- Phase 3: Implement and validate fix
```

### Phase 1: Bottleneck Isolation

**AI Response:** 
- Confirmed understanding of the systematic approach
- Suggested specific tools for each layer (browser dev tools, server monitoring, database query logs)
- Provided step-by-step isolation plan

**Execution:**
- Browser network tab: Backend API calls taking 4-8 seconds ✅ **Backend issue identified**
- Frontend rendering: Normal performance ❌ **Not the problem**
- Database monitoring: Query times normal ❌ **Not the database**

**Validation checkpoint:** "Backend API calls are the bottleneck. Should we focus there?"
**AI Confidence:** 9/10 ✅

### Phase 2: Backend Investigation

**Context inheritance:** Backend APIs slow, database queries normal
**New focus:** Application code, middleware, external API calls

**Systematic investigation:**
```
Check 1: Recent code changes in API endpoints
- Found new user profile data loading in middleware
- Middleware runs on EVERY request (not just profile pages)

Check 2: Profile data loading implementation
- Making API call to external service for each request
- No caching implemented
- External service response time: 3-5 seconds

Root cause identified: New middleware making uncached external API calls
```

**Validation:** "The new profile middleware is making slow external API calls on every request. This explains the universal slowdown."

### Phase 3: Fix Implementation

**Context:** Root cause confirmed, need caching solution
**Constraints:** Quick fix needed, minimal risk

**Solution:**
- Implement Redis caching for profile data (5-minute TTL)
- Move profile loading from middleware to specific endpoints that need it
- Add fallback for external service failures

**Validation:**
- Local testing: Page loads back to <1s ✅
- Staging deployment: Performance restored ✅
- Production deployment: Issue resolved ✅

## Key Differences

### Systematic vs. Random
- **Before:** Jumped between different theories randomly
- **After:** Methodically isolated the problem layer by layer

### Context Preservation
- **Before:** AI forgot what we'd already checked
- **After:** Each phase built on validated findings from previous phases

### Focused Investigation
- **Before:** Checked everything at once, got overwhelmed
- **After:** Clear boundaries between investigation phases

### Validation Checkpoints
- **Before:** Kept investigating without confirming findings
- **After:** Validated each discovery before proceeding

## Debugging Anti-Patterns Avoided

### ❌ Context Pollution
**Problem:** Mixing different theories and investigations  
**Solution:** Clear phase boundaries with specific focus areas

### ❌ Assumption Stacking
**Problem:** Building theories on unvalidated assumptions  
**Solution:** Validation checkpoints before proceeding

### ❌ Tool Overload
**Problem:** Using every debugging tool at once  
**Solution:** Systematic tool selection based on current hypothesis

### ❌ Forgetting Previous Work
**Problem:** Re-investigating things already ruled out  
**Solution:** Context inheritance between phases

## When This Pattern Saves Time

**Essential for:**
- Complex systems with multiple potential failure points
- Intermittent or hard-to-reproduce issues
- Performance problems with unclear causes
- Any debugging that's taken >30 minutes without progress

**Time investment:** 10 minutes of structure saves hours of circular investigation

## Debugging Template

```
Problem: [Specific symptoms and timeline]
Environment: [Tech stack and recent changes]
Success criteria: [How you'll know it's fixed]

Phase 1: Isolate the layer (frontend/backend/database/network)
Phase 2: Deep dive into identified layer
Phase 3: Implement and validate fix

Validation: Confirm findings before moving to next phase
```

The structured approach turned debugging from a frustrating guessing game into a systematic investigation with predictable progress.