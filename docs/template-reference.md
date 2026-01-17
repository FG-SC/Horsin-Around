# Template Reference

Complete documentation for all Swarm Commander templates.

## Overview

| Template | Purpose | When to Use |
|----------|---------|-------------|
| [Order Template](#order-template) | Assign tasks to a chat | Starting each round |
| [Answer Template](#answer-template) | Report task completion | When finishing tasks |
| [Command Center](#command-center) | Track all progress | Throughout execution |
| [Question Template](#question-template) | Ask for clarification | When blocked or unclear |
| [Alert Template](#alert-template) | Report problems | Timeouts, blockers, critical issues |

---

## Order Template

**File:** `templates/order_template.md`
**Location:** `coordination/orders/order_chat_[LETTER]_[ROUND].md`

### Purpose
Provides clear instructions for what a chat should accomplish in a round.

### Key Sections

| Section | Required | Purpose |
|---------|----------|---------|
| Header | Yes | Identifies chat, round, priority, timing |
| Mission | Yes | One-sentence goal |
| Context | Yes | Background and dependencies |
| Tasks | Yes | Numbered list with estimates |
| Deliverables | Yes | What to produce |
| Time Tracking | Yes | Template for tracking |
| Success Criteria | Yes | How to know if done |
| If You Get Stuck | Recommended | Guidance for common issues |
| Related Work | Recommended | What other chats are doing |

### Naming Convention
```
order_chat_A_1.md   # Chat A, Round 1
order_chat_B_2.md   # Chat B, Round 2
order_chat_C_1.md   # Chat C, Round 1
```

### Tips
- Keep missions to one sentence
- Break tasks into 10-30 minute chunks
- Include specific success criteria
- Reference related chats to aid coordination

---

## Answer Template

**File:** `templates/answer_template.md`
**Location:** `coordination/answers/answer_chat_[LETTER]_[ROUND].md`

### Purpose
Documents what was accomplished, how long it took, and what comes next.

### Key Sections

| Section | Required | Purpose |
|---------|----------|---------|
| Header | Yes | Task, status, date |
| Summary | Yes | 2-3 sentence overview |
| Time Tracking | Yes | Estimated vs actual |
| Completed Tasks | Yes | What was done |
| Deliverables | Yes | Files/artifacts created |
| Issues Encountered | If any | Problems and solutions |
| Success Criteria Check | Yes | Which criteria were met |
| Lessons Learned | Recommended | For future estimation |
| Next Steps | Yes | Recommendations |

### Status Values
- **Complete** - All tasks finished, all criteria met
- **Partial** - Some tasks finished, can continue in next round
- **Blocked** - Cannot proceed without external input

### Naming Convention
```
answer_chat_A_1.md   # Response to order_chat_A_1.md
answer_chat_B_2.md   # Response to order_chat_B_2.md
```

### Tips
- Be honest about what wasn't completed
- Include specific time breakdowns
- Note lessons for future estimates
- Clearly state what's needed next

---

## Command Center

**File:** `templates/COMMAND_CENTER_template.md`
**Location:** `coordination/COMMAND_CENTER.md`

### Purpose
Single source of truth for project status. The commander's main dashboard.

### Key Sections

| Section | Required | Purpose |
|---------|----------|---------|
| Header | Yes | Last update, round, overall status |
| Active Chats | Yes | Status table for all chats |
| Recent Updates | Yes | Timeline of events |
| Blockers & Alerts | Yes | Current problems |
| Pending Questions | Yes | Unanswered questions |
| Completed This Round | Yes | Finished work |
| Dependencies Map | Recommended | Visual task flow |
| Next Actions | Recommended | Commander to-do list |
| Metrics | Optional | Time tracking rollup |

### Chat Status Values
- `Pending` - Order given, not started
- `Active` - Currently working
- `Complete` - Finished this round
- `Blocked` - Waiting on something
- `Timeout` - Exceeded time limit
- `Standby` - Not active this round

### Update Frequency
- Every 15 minutes during active execution
- After each answer file received
- Immediately when blockers arise

### Tips
- Keep updates brief and scannable
- Use the status table as your primary view
- Link to relevant files, don't copy content
- Archive old updates at end of each round

---

## Question Template

**File:** `templates/question_template.md`
**Location:** `coordination/questions/question_[FROM]_to_[TO]_[N].md`

### Purpose
Formal way for chats to request information from commander or other chats.

### Key Sections

| Section | Required | Purpose |
|---------|----------|---------|
| Header | Yes | Subject, priority, blocking status |
| Question | Yes | Clear, specific ask |
| Context | Yes | Why this is needed |
| What I Need | Yes | Preferred answer format |
| Impact | Yes | What happens if not answered |

### Priority Values
- **High** - Blocking current work
- **Medium** - Blocking upcoming work
- **Low** - Nice to have

### Naming Convention
```
question_A_to_commander_1.md   # Chat A asking commander
question_B_to_A_1.md           # Chat B asking Chat A
question_C_to_commander_2.md   # Second question from Chat C
```

### Tips
- Be specific about what you need
- Include what you've already tried
- State urgency clearly
- One question per file

---

## Alert Template

**File:** `templates/alert_template.md`
**Location:** `coordination/alerts/alert_[CHAT]_[TYPE].md`

### Purpose
Formal notification of problems that require commander attention.

### Alert Types

| Type | When to Use |
|------|-------------|
| **Timeout** | Task exceeded estimate by 10%+ |
| **Blocked** | Cannot proceed without external input |
| **Critical** | Unexpected error or failure |

### Key Sections

| Section | Required | Purpose |
|---------|----------|---------|
| Header | Yes | Chat, task, time, severity |
| Alert Type | Yes | Timeout/blocked/critical |
| Situation | Yes | What happened |
| Current Progress | Yes | What's done, what's remaining |
| Root Cause | Yes | Why this happened |
| What I've Tried | Yes | Approaches attempted |
| Options | Yes | Possible paths forward |
| Impact Assessment | Yes | Effect on project |
| Request to Commander | Yes | What decision is needed |

### Severity Values
- **Critical** - Project at risk, immediate attention
- **High** - Significant delay, needs quick response
- **Medium** - Manageable delay, can wait briefly

### Naming Convention
```
alert_A_timeout.md    # Chat A hit timeout
alert_B_blocked.md    # Chat B is blocked
alert_C_critical.md   # Chat C hit critical error
```

### Tips
- Stop working when you create an alert
- Include all options you've considered
- Make a clear recommendation
- State exactly what you need from commander

---

## File Organization

### Recommended Structure

```
coordination/
├── COMMAND_CENTER.md
│
├── orders/
│   ├── order_chat_A_1.md
│   ├── order_chat_A_2.md
│   ├── order_chat_B_1.md
│   └── ...
│
├── answers/
│   ├── answer_chat_A_1.md
│   ├── answer_chat_B_1.md
│   └── ...
│
├── questions/
│   ├── question_A_to_commander_1.md
│   ├── question_B_to_A_1.md
│   └── ...
│
├── alerts/
│   ├── alert_A_timeout.md
│   └── ...
│
├── logs/
│   ├── 2025-01-15/
│   │   ├── 09-00_round_1_start.md
│   │   ├── 09-45_chat_A_complete.md
│   │   └── ...
│   └── ...
│
└── templates/
    ├── order_template.md
    ├── answer_template.md
    └── ...
```

### Archiving

After project completion, consider:
```
coordination/
├── archive/
│   ├── round_1/
│   │   ├── orders/
│   │   └── answers/
│   └── round_2/
│       └── ...
└── ...
```

---

## Customization

### Adding Custom Sections

All templates can be extended. Common additions:

**For orders:**
- Risk assessment
- Rollback instructions
- Approval checkpoints

**For answers:**
- Code review notes
- Test coverage report
- Performance metrics

**For Command Center:**
- Team availability
- External dependencies
- Stakeholder updates

### Simplifying

For quick projects, remove:
- Detailed time tracking
- Metrics sections
- Lessons learned

Keep only:
- Mission/tasks
- Status
- Deliverables
- Blockers
