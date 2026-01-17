# Swarm Commander

> **Go Horse, but make it parallel.** 🐴🐴🐴🐴🐴

A lightweight, file-based system for orchestrating multiple AI agents working in parallel on complex projects.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Methodology](https://img.shields.io/badge/methodology-Parallel%20Go%20Horse-orange.svg)](https://gohorse.com.br/extreme-go-horse-xgh)

---

## Philosophy

```
     Traditional Development           Swarm Commander

            🐴                      🐴  🐴  🐴  🐴  🐴
     One task at a time               Organized stampede

      "Let me plan this              "Release the horses,
       for 3 weeks..."                we ship at sunset"
```

We took the pragmatic spirit of [Extreme Go Horse (XGH)](https://gohorse.com.br/extreme-go-horse-xgh) and asked: *what if we ran multiple horses at once, but with just enough coordination to not crash into each other?*

**The result:** Organized chaos that actually ships.

### The Parallel Go Horse Principles

1. **More horses = more speed** - Why use one AI when you can use two, three, or ten?
2. **Files over meetings** - No standups, just `order.md` and `answer.md`
3. **10% rule** - Even Go Horse needs guardrails (timeout at estimate + 10%)
4. **Ship it** - Perfect is the enemy of deployed
5. **Trust the stampede** - Each horse knows its lane
6. **Scale as needed** - 2 horses or 10, the system adapts

---

## Why Swarm Commander?

Modern AI assistants are powerful, but coordinating multiple AI sessions to work on a complex project is challenging. **Swarm Commander** provides a simple, proven system for:

- **Parallel execution**: Run 2, 5, or 10+ AI chats simultaneously on different tasks
- **Clear communication**: File-based orders and answers prevent miscommunication
- **Time management**: Built-in timeout protocols prevent runaway tasks
- **Progress tracking**: Real-time visibility into all parallel workstreams
- **Zero dependencies**: Just markdown files - works with any AI assistant

### Swarm Commander vs BMAD Method

| Feature | Swarm Commander | BMAD Method |
|---------|----------------|-------------|
| **Philosophy** | Parallel Go Horse 🐴 | Comprehensive framework |
| **Setup time** | 5 minutes | 15-30 minutes |
| **Dependencies** | None (just markdown) | Node.js v20+ |
| **Learning curve** | Low - just files | Medium - 21 agents, 50+ workflows |
| **Vibe** | "Release the horses!" | "Let's architect this properly" |
| **Best for** | Fast parallel execution | Full product lifecycle |

**Choose Swarm Commander if**: You want to ship today with multiple AIs working in parallel.

**Choose BMAD if**: You're building a product over weeks/months and want full lifecycle support.

## Quick Start (5 minutes)

### 1. Create your coordination folder

```bash
mkdir my-project/coordination
cd my-project/coordination
```

### 2. Copy the templates

Download or copy these files to your `coordination/` folder:
- `COMMAND_CENTER.md` - Your mission control dashboard
- `templates/order_template.md` - Template for assigning tasks
- `templates/answer_template.md` - Template for reporting results

### 3. Plan your parallel work

Break your project into independent tasks. Use as many chats as you need:

```
Small Project (2 horses)        Medium Project (3-4 horses)       Large Project (5+ horses)

├── Chat A: Code                ├── Chat A: Backend               ├── Chat A: Backend API
└── Chat B: Tests               ├── Chat B: Frontend              ├── Chat B: Frontend UI
                                └── Chat C: Database              ├── Chat C: Database
                                                                  ├── Chat D: Testing
                                                                  └── Chat E: DevOps
```

### 4. Create order files

For each chat, create an order file from the template:

```markdown
# Order for Chat A - Round 1

**Mission:** Build the user authentication API

**Tasks:**
1. Create login endpoint (20 min)
2. Create registration endpoint (15 min)
3. Add JWT token handling (15 min)

**Deliverable:** answer_chat_A_1.md with results
```

### 5. Launch your chats

Open multiple AI chat windows and send:

```
You are Chat A in a parallel coordination system.
Read the attached order_chat_A_1.md and execute the tasks.
Follow the 10% timeout rule. Create answer_chat_A_1.md when done.
```

### 6. Monitor from Command Center

Track all chats in your `COMMAND_CENTER.md`:

| Chat | Task | Status | Progress | ETA |
|------|------|--------|----------|-----|
| A | Auth API | In Progress | 60% | 14:30 |
| B | Frontend | Complete | 100% | Done |
| C | Database | Blocked | 30% | TBD |

## Core Concepts

### The 10% Timeout Rule

If any task exceeds its estimate by 10%, the AI must **stop and report**. This prevents:
- Wasted time on stuck tasks
- Late discovery of blockers
- Cascading delays

**Example**: 30-minute task → timeout at 33 minutes

### File-Based Communication

All coordination happens through files:

```
coordination/
├── COMMAND_CENTER.md      # Status dashboard
├── orders/                # Tasks for each chat
│   ├── order_chat_A_1.md
│   └── order_chat_B_1.md
├── answers/               # Results from each chat
│   ├── answer_chat_A_1.md
│   └── answer_chat_B_1.md
├── questions/             # Inter-chat communication
│   └── question_A_to_B.md
└── alerts/                # Timeout/blocker alerts
    └── alert_A_timeout.md
```

### Swim Lanes

Organize parallel work into specialized lanes:

| Lane | Focus | When to Use |
|------|-------|-------------|
| **Build** | Feature development | Always |
| **Ops** | Monitoring, deployments | Long-running tasks |
| **Investigation** | Bug hunting, root cause | Critical issues |
| **Data** | Migrations, analysis | Data changes |

## Documentation

- **[Quick Start Guide](docs/quick-start.md)** - Get running in 5 minutes
- **[Full Template Reference](docs/template-reference.md)** - Complete template documentation
- **[Best Practices](docs/best-practices.md)** - Tips for effective coordination
- **[Examples](examples/)** - Real-world usage examples

## Templates

| Template | Purpose |
|----------|---------|
| [Order Template](templates/order_template.md) | Assign tasks to a chat |
| [Answer Template](templates/answer_template.md) | Report task completion |
| [Command Center](templates/COMMAND_CENTER_template.md) | Track all progress |
| [Question Template](templates/question_template.md) | Inter-chat questions |
| [Alert Template](templates/alert_template.md) | Report blockers/timeouts |

## Use Cases

Scale your herd based on project size:

**Quick Bug Fix (2 horses)**
```
Chat A: Fix the bug
Chat B: Write/update tests
```

**New Feature (3 horses)**
```
Chat A: Backend implementation
Chat B: Frontend implementation
Chat C: Documentation
```

**Full Product Sprint (5+ horses)**
```
Chat A: Backend API
Chat B: Frontend components
Chat C: Database schema
Chat D: Test suite
Chat E: CI/CD pipeline
```

**Research Project (3-4 horses)**
```
Chat A: Literature review
Chat B: Data analysis
Chat C: Visualization
Chat D: Report writing
```

## Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Ways to contribute:
- Share your use case templates
- Improve documentation
- Report bugs or suggest features
- Translate to other languages

## License

MIT License - free for personal and commercial use.

## Acknowledgments

- Inspired by real-world parallel AI coordination experiences
- Philosophical foundation from [Extreme Go Horse (XGH)](https://gohorse.com.br/extreme-go-horse-xgh)
- Thanks to all contributors and early adopters

---

<p align="center">
  <b>Ready to release the horses?</b> 🐴🐴🐴🐴🐴
  <br><br>
  Start with the <a href="docs/quick-start.md">Quick Start Guide</a> and have your first stampede running in 5 minutes.
  <br><br>
  <i>"I used to mass one horse at a time. Now I mass five. Life changing."</i>
  <br>
  — A Happy Commander
</p>
