---
name: reviewing-plans
description: Use when receiving a plan before executing it, or when asked to review a plan - evaluates plans against four criteria (feasibility, scope, completeness, cohesiveness) to catch issues before implementation begins
---

# Reviewing Plans

## Overview

Review plans systematically before execution to catch structural issues early.

**Core principle:** A plan that fails review criteria will fail during execution. Catch it now.

**Announce at start:** "I'm using the reviewing-plans skill to evaluate this plan."

## The Four Criteria

Every plan must pass all four:

| Criterion | Question | Fail Signal |
|-----------|----------|-------------|
| **Feasibility** | Can each step actually be done? | Vague instructions, missing decisions, unclear dependencies |
| **Scope** | Is each task appropriately sized? | Tasks with 5+ steps, multiple features bundled, "also add..." patterns |
| **Completeness** | Is the plan ready for production? | TODOs, placeholder code, "figure out later", missing error handling |
| **Cohesiveness** | Does the plan flow logically? | Disconnected tasks, unclear ordering, missing glue between components |

## Review Checklist

**Feasibility:**
- [ ] Each step has a specific action (not "set up X" or "add Y")
- [ ] File paths are exact, not "various files" or "relevant files"
- [ ] Technical decisions are made (libraries, patterns, schemas)
- [ ] Dependencies between tasks are explicit
- [ ] Each step can be verified as complete

**Scope:**
- [ ] Tasks are 2-5 minute chunks (one action each)
- [ ] No task bundles multiple independent features
- [ ] Nice-to-haves are separated from core requirements
- [ ] Each task has a single clear outcome

**Completeness:**
- [ ] No TODO comments in code examples
- [ ] No placeholder implementations ("// implement this")
- [ ] No deferred decisions ("figure out later")
- [ ] Error handling is specified
- [ ] Validation logic is defined (not "add appropriate checks")

**Cohesiveness:**
- [ ] Tasks have logical ordering (dependencies before dependents)
- [ ] Data flows clearly between components
- [ ] No orphan tasks (tasks that don't connect to others)
- [ ] Testing is interleaved, not deferred to end

## Red Flags by Criterion

**Feasibility:**
- "Modify: various files"
- "Add appropriate X"
- "Set up the module"
- Missing library/tool specifications

**Scope:**
- Task lists with 7+ steps
- "Also implement..." mid-task
- OAuth, 2FA, admin panels bundled with basic auth
- "Write all tests" as single task

**Completeness:**
- `// TODO:` in code blocks
- "Figure out what fields we need"
- Functions with only comments, no implementation
- "Handle errors appropriately"

**Cohesiveness:**
- Database migrations after code that uses them
- Frontend before API it calls
- Testing as final task instead of with each feature

## Review Output Format

```markdown
## Plan Review: [Plan Name]

### Feasibility: PASS | NEEDS WORK
[Specific issues or "All steps are actionable"]

### Scope: PASS | NEEDS WORK
[Specific issues or "Tasks appropriately sized"]

### Completeness: PASS | NEEDS WORK
[Specific issues or "No placeholders or deferred decisions"]

### Cohesiveness: PASS | NEEDS WORK
[Specific issues or "Logical flow established"]

### Verdict: READY | NOT READY

### Required Changes (if NOT READY):
1. [Specific change needed]
2. [Specific change needed]
```

## When To Use

**Before executing any plan:**
- Plans from superpowers:writing-plans
- Plans from your partner
- Plans you wrote yourself

**Don't skip because:**
- "I wrote it, so it's fine"
- "Partner is experienced"
- "It looks complete"

## After Review

**If READY:** Proceed with superpowers:executing-plans

**If NOT READY:**
1. Report specific issues to plan author
2. Wait for revised plan
3. Re-review before executing

**Never execute a plan that fails review.** Time spent fixing a bad plan is always less than time wasted executing one.
