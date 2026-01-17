# Swarm Commander - Full Guide

The complete reference for parallel AI coordination.

## Table of Contents

1. [Introduction](#introduction)
2. [Core Concepts](#core-concepts)
3. [Getting Started](#getting-started)
4. [The Order-Answer Cycle](#the-order-answer-cycle)
5. [Time Management](#time-management)
6. [Communication Protocol](#communication-protocol)
7. [Monitoring & Tracking](#monitoring--tracking)
8. [Scaling Up](#scaling-up)
9. [Troubleshooting](#troubleshooting)

---

## Introduction

### What is Swarm Commander?

Swarm Commander is a file-based system for coordinating multiple AI assistants working in parallel on complex projects. Instead of one AI doing everything sequentially, you split work across multiple AI chat sessions:

```
Project
├── Chat A: Backend development
├── Chat B: Frontend development
├── Chat C: Database work
├── Chat D: Testing & QA
└── Chat E: Documentation
```

### Benefits

| Benefit | Description |
|---------|-------------|
| **Speed** | 3-5x faster completion through parallel execution |
| **Focus** | Each AI specializes in one domain |
| **Clarity** | Clear accountability per task |
| **Visibility** | Easy to track progress across workstreams |
| **Detection** | Early discovery of issues and blockers |

### When to Use

**Good fit:**
- Projects with 8+ hours of work
- Work that can be split into independent parts
- Complex systems with multiple components
- Research projects with multiple threads

**Not needed:**
- Simple, quick tasks
- Highly sequential work
- Projects with single-point dependencies

---

## Core Concepts

### The Commander Role

You are the **Commander**. Your job is to:
- Break work into parallel tasks
- Create order files for each chat
- Monitor progress across all chats
- Handle blockers and questions
- Review results and plan next rounds

### Chat Agents

Each AI chat session is a **Chat Agent** (A, B, C, etc.). Agents:
- Receive orders from the Commander
- Execute tasks within time limits
- Report progress and results
- Ask questions when stuck
- Create alerts when blocked

### Rounds

Work is organized into **Rounds**. Each round:
- Has a set of parallel tasks
- Produces deliverables for the next round
- Ends when all chats complete or need reassignment

```
Round 1: Foundation work (all parallel)
    ↓
Round 2: Integration work (may have dependencies)
    ↓
Round 3: Final assembly and testing
```

### The 10% Rule

The cornerstone of time management:

> If any task exceeds its estimate by 10%, STOP and report.

**Example:**
- Estimated: 30 minutes
- Timeout threshold: 33 minutes
- At 33 minutes: Stop, create alert, wait for guidance

This prevents:
- Wasted time on stuck tasks
- Late discovery of problems
- Cascading delays across chats

---

## Getting Started

### Step 1: Create Your Folder Structure

```
your-project/
└── coordination/
    ├── COMMAND_CENTER.md
    ├── orders/
    ├── answers/
    ├── questions/
    ├── alerts/
    └── logs/
```

### Step 2: Plan Your Work

**Identify all major tasks:**

```markdown
## Project Tasks

1. Backend API - 2 hours
2. Frontend UI - 2 hours
3. Database setup - 1 hour
4. Testing - 1.5 hours
5. Documentation - 1 hour
```

**Map dependencies:**

```markdown
## Dependencies

- Backend (A): No dependencies
- Frontend (B): No dependencies initially, needs API in Round 2
- Database (C): No dependencies
- Testing (D): Needs A, B, C complete
- Documentation (E): Can start anytime
```

**Assign to chats:**

```markdown
## Assignments

- Chat A: Backend API
- Chat B: Frontend UI
- Chat C: Database
- Chat D: Testing (starts Round 2)
- Chat E: Documentation
```

### Step 3: Create Order Files

For each chat, create an order file using the template.

Key elements:
- Clear mission (one sentence)
- Numbered tasks with time estimates
- Success criteria
- Time tracking template

### Step 4: Set Up Command Center

Create `COMMAND_CENTER.md` with:
- Status table for all chats
- Updates section (empty initially)
- Blockers section (empty initially)
- Next actions checklist

### Step 5: Launch Chats

Open separate AI chat sessions. For each:

1. Send the launch message:
   ```
   You are Chat [A/B/C/etc] in a parallel coordination system.
   Please read the attached order and execute the tasks.
   Follow the 10% timeout rule.
   Create answer_chat_[X]_[N].md when complete.
   ```

2. Attach or paste the order file

3. Note the start time in Command Center

---

## The Order-Answer Cycle

### Order Files

Location: `coordination/orders/order_chat_[LETTER]_[ROUND].md`

**Required sections:**
- Mission: One sentence goal
- Context: Background and dependencies
- Tasks: Numbered with estimates
- Deliverables: What to produce
- Time tracking: Template to fill out
- Success criteria: How to verify completion

**Optional sections:**
- If stuck guidance
- Related work info
- FAQ for common issues

### Answer Files

Location: `coordination/answers/answer_chat_[LETTER]_[ROUND].md`

**Required sections:**
- Summary: What was accomplished
- Time tracking: Estimated vs actual
- Completed tasks: Details on each
- Deliverables: Files created
- Issues: Problems encountered
- Success criteria: Which were met
- Next steps: Recommendations

### Cycle Flow

```
1. Commander creates order_chat_A_1.md
              ↓
2. Chat A reads order, starts work
              ↓
3. Chat A tracks time, updates progress
              ↓
4. Chat A creates answer_chat_A_1.md
              ↓
5. Commander reviews answer
              ↓
6. Commander creates order_chat_A_2.md (next round)
```

---

## Time Management

### Setting Estimates

**Guidelines by task type:**

| Task Type | Typical Duration |
|-----------|------------------|
| Setup/config | 10-15 min |
| Simple feature | 15-30 min |
| Complex feature | 30-45 min |
| Integration work | 20-40 min |
| Testing | 15-30 min |
| Documentation | 15-30 min |

**First-time buffer:** Add 20% for unfamiliar tasks

### The Time Tracking Block

Every chat starts work with:

```markdown
## Time Tracking

| Task | Estimated | Started | Actual | Status |
|------|-----------|---------|--------|--------|
| Task 1 | 15m | 09:00 | - | Active |
| Task 2 | 20m | - | - | Pending |
| Task 3 | 10m | - | - | Pending |
| **Total** | **45m** | | | |

**Start time:** 09:00
**Expected end:** 09:45
**Timeout threshold:** 09:50 (45 + 10%)
```

### Progress Updates

Every 15 minutes, chats note status:

```markdown
### Update 09:15
- Task 1: 80% complete
- On track for 09:45
- No blockers
```

### Timeout Protocol

When timeout threshold is reached:

1. **Stop working** immediately
2. **Create alert file** with current status
3. **Document** what's blocking progress
4. **Propose options** for path forward
5. **Wait** for Commander guidance

---

## Communication Protocol

### Questions

When a chat needs clarification:

1. Create `question_[FROM]_to_[TO]_[N].md`
2. Include what you've tried
3. State urgency clearly
4. Continue with unblocked work if possible

**Question priority:**
- **High:** Blocking current task
- **Medium:** Blocking next task
- **Low:** Nice to have

### Alerts

Three types:

| Type | When to Use |
|------|-------------|
| **Timeout** | Task exceeded estimate by 10%+ |
| **Blocked** | Cannot proceed without external input |
| **Critical** | Unexpected error or failure |

Alerts require Commander response before continuing.

### Inter-Chat Communication

When chats need to coordinate:

```
Chat A → question_A_to_B_1.md → Chat B
Chat B → answer_B_to_A_1.md → Chat A
```

Commander should monitor inter-chat questions and intervene if responses are slow.

---

## Monitoring & Tracking

### Command Center Updates

Update the Command Center:
- Every 15 minutes during active execution
- After each answer file received
- Immediately when blockers arise

### Status Tracking

Chat statuses:
- `Pending` - Order given, not started
- `Active` - Currently working
- `Complete` - Finished this round
- `Blocked` - Waiting on something
- `Timeout` - Exceeded time limit

### Metrics

**Track these:**

| Metric | Formula | Target |
|--------|---------|--------|
| Estimation accuracy | Estimated / Actual × 100 | 80-120% |
| On-time rate | On-time tasks / Total × 100 | 90%+ |
| Blocker resolution | Time to answer question | <10 min |

### Logs (Optional)

For complex projects, maintain logs:

```
logs/
├── 2025-01-15/
│   ├── 09-00_round_1_start.md
│   ├── 09-30_chat_A_update.md
│   ├── 10-00_blocker_resolved.md
│   └── 10-30_round_1_complete.md
```

---

## Scaling Up

### 2-3 Chats

- Simple coordination
- Commander can manage casually
- Good for learning the system

### 4-5 Chats

- Sweet spot for most projects
- Requires dedicated Commander attention
- 15-minute check-ins essential

### 6+ Chats

- Consider sub-groups with leads
- Automated monitoring helps
- Clear escalation paths needed

### Swim Lanes

Organize chats by specialty:

| Lane | Focus | Example Chats |
|------|-------|---------------|
| **Build** | New features | A, B |
| **Ops** | Infrastructure, monitoring | C |
| **Investigation** | Bug fixes, research | D |
| **Data** | Database, analytics | E |

---

## Troubleshooting

### Chat Isn't Following Protocol

**Symptom:** No time tracking, no answer file

**Solution:**
1. Remind about key rules
2. Provide template to copy
3. Be specific about requirements

### Too Many Blockers

**Symptom:** Chats constantly waiting

**Solution:**
1. Review dependency mapping
2. Reduce parallelism
3. Create mock data for early rounds
4. Break tasks smaller

### Estimates Are Always Wrong

**Symptom:** Most tasks timeout

**Solution:**
1. Add 30-50% buffer initially
2. Track actuals religiously
3. Build estimate database by task type
4. Ask for chat input on estimates

### Quality Issues

**Symptom:** Work doesn't meet expectations

**Solution:**
1. Add explicit success criteria
2. Include examples in orders
3. Add review checkpoint mid-task
4. Reduce scope per round

### Commander Overwhelmed

**Symptom:** Can't keep up with all chats

**Solution:**
1. Reduce parallel chats
2. Increase round duration
3. Batch similar decisions
4. Delegate to lead chats

---

## Next Steps

1. **Start small:** Try with 2-3 chats on a real project
2. **Track metrics:** Learn what estimates work for your projects
3. **Customize:** Adapt templates to your workflow
4. **Share:** Contribute your learnings back to the community

---

*For template details, see the [Template Reference](template-reference.md).*
*For tips and patterns, see [Best Practices](best-practices.md).*
