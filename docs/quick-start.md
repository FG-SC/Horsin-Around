# Quick Start Guide

Get your first stampede running in 5 minutes. 🐴🐴🐴

## Prerequisites

- Multiple AI chat sessions (Claude, ChatGPT, Gemini, etc.)
- A text editor
- A project to work on
- The courage to release multiple horses at once

**No installation required** - Swarm Commander is just markdown files. True Go Horse style.

## Step 1: Set Up Your Folder Structure (1 minute)

Create this structure in your project:

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

**Quick setup command:**

```bash
mkdir -p coordination/{orders,answers,questions,alerts,logs}
```

## Step 2: Plan Your Work (2 minutes)

### Identify Parallel Tasks

Break your project into tasks that can run simultaneously:

```markdown
# Project: E-commerce Website

## Parallel Tasks (can start together)
- Task A: Backend REST API (Chat A)
- Task B: Frontend React components (Chat B)
- Task C: Database schema design (Chat C)

## Sequential Tasks (must wait)
- Task D: Integration testing (after A, B, C)
- Task E: Deployment (after D)
```

### Map Dependencies

```
A (Backend) ──┐
B (Frontend) ─┼── D (Testing) ── E (Deploy)
C (Database) ─┘
```

## Step 3: Create Your First Order (1 minute)

Create `coordination/orders/order_chat_A_1.md`:

```markdown
# Order for Chat A - Round 1

**From:** Commander
**To:** Chat A
**Priority:** High
**Estimated Duration:** 45 minutes

---

## Mission

Build the REST API for user authentication.

## Tasks

### Task 1: Login Endpoint (15 min)
- Create POST /api/auth/login
- Accept email and password
- Return JWT token on success

### Task 2: Registration Endpoint (15 min)
- Create POST /api/auth/register
- Validate email format and password strength
- Store user in database

### Task 3: Token Validation (15 min)
- Create middleware to validate JWT
- Add /api/auth/me endpoint

## Deliverables

1. Create `answer_chat_A_1.md` with results
2. All code files in `src/api/auth/`

## Time Tracking

Start with this at the top of your work:

| Task | Estimated | Actual | Status |
|------|-----------|--------|--------|
| Login | 15m | - | Pending |
| Register | 15m | - | Pending |
| Token | 15m | - | Pending |

**Timeout threshold:** 50 minutes (45 + 10%)

If you hit timeout and aren't 90% done, STOP and create an alert.
```

## Step 4: Set Up Command Center (30 seconds)

Create `coordination/COMMAND_CENTER.md`:

```markdown
# Command Center - E-commerce Project

**Last Updated:** [Current Time]

## Active Chats

| Chat | Task | Status | Progress | Started | ETA |
|------|------|--------|----------|---------|-----|
| A | Auth API | Not Started | 0% | - | - |
| B | Frontend | Not Started | 0% | - | - |
| C | Database | Not Started | 0% | - | - |

## Updates

*No updates yet*

## Blockers

*None*
```

## Step 5: Launch Your Chats (30 seconds each)

Open separate AI chat windows. For each one, send:

### Chat A Launch Message:

```
You are Chat A in a multi-AI parallel coordination system.

Your role: Backend Development

Please read the attached file: order_chat_A_1.md

Key rules:
1. Start with time tracking
2. Update progress every 15 minutes
3. If you exceed estimated time by 10%, STOP and report
4. Create answer_chat_A_1.md when complete

Your mission: Build the REST API for user authentication

Estimated time: 45 minutes

Let's begin!
```

Then attach or paste the order file content.

## Step 6: Monitor Progress

### Update Command Center regularly:

```markdown
| Chat | Task | Status | Progress | Started | ETA |
|------|------|--------|----------|---------|-----|
| A | Auth API | In Progress | 40% | 14:00 | 14:45 |
| B | Frontend | In Progress | 25% | 14:00 | 15:00 |
| C | Database | Complete | 100% | 14:00 | Done |
```

### Watch for:
- Progress updates from each chat
- Questions in the `questions/` folder
- Alerts in the `alerts/` folder

### Handle blockers quickly:
- Check for `question_A_to_commander.md` files
- Respond within 10-15 minutes to keep momentum

## Step 7: Collect Results

When a chat completes, they create an answer file:

**Example `coordination/answers/answer_chat_A_1.md`:**

```markdown
# Chat A - Round 1 Results

**Status:** Complete
**Duration:** 42 minutes
**Accuracy:** 93% (45 estimated, 42 actual)

## Summary

Successfully created authentication API with login, registration,
and token validation endpoints.

## Completed Tasks

1. POST /api/auth/login - Working
2. POST /api/auth/register - Working
3. JWT middleware - Working
4. GET /api/auth/me - Working

## Files Created

- src/api/auth/login.ts
- src/api/auth/register.ts
- src/api/auth/middleware.ts
- src/api/auth/me.ts

## Issues

None encountered.

## Next Steps

Ready for integration testing with frontend.
```

## What's Next?

### Scale Up
- Add more chats for larger projects
- Use specialized lanes (Build, Ops, Investigation, Data)

### Improve
- Track metrics across rounds
- Refine time estimates based on actual data
- Create custom templates for your workflow

### Go Deeper
- Read the [Full Template Reference](template-reference.md)
- Check out [Best Practices](best-practices.md)
- See [Examples](../examples/) for real-world usage

---

## Troubleshooting

### Chat isn't following the protocol
Send a reminder about the key rules:
- Time tracking is mandatory
- 10% timeout rule must be followed
- Answer file is required

### Chats are conflicting
- Check your dependency mapping
- Add clearer scope boundaries in order files
- Use the questions folder for inter-chat coordination

### Progress is slow
- Check for unreported blockers
- Review time estimates - may be too aggressive
- Consider breaking tasks into smaller pieces

---

## The Parallel Go Horse Manifesto (Quick Version)

1. **"It works on my 5 machines"** - If all horses say it works, it works
2. **"Não há problema que não se resolva com mais cavalos"** - More horses = more solutions
3. **"Timeout exists for a reason"** - Even Go Horse respects the 10% rule
4. **"Documentation is for the weak, but order.md is sacred"** - Files are the law

---

**You're ready!** Release the horses and experience 3-5x faster project completion. 🐴

*"Fui de um cavalo para cinco. Mudou minha vida."* — Um Commander Feliz
