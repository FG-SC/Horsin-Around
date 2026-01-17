# Example: Software Development Project

This example shows how to use Swarm Commander for a typical software development project - building a REST API with a frontend.

## Project Overview

**Goal:** Build a task management application with:
- REST API backend
- React frontend
- PostgreSQL database
- Authentication system

**Timeline:** 1 day with parallel execution

## Chat Assignment

| Chat | Role | Focus |
|------|------|-------|
| A | Backend Developer | REST API endpoints |
| B | Frontend Developer | React components |
| C | Database Engineer | Schema & migrations |
| D | DevOps | CI/CD & deployment |
| E | QA Engineer | Testing & validation |

## Dependency Map

```
Round 1 (Parallel):
├── Chat A: API structure + auth endpoints
├── Chat B: Component library + layouts
├── Chat C: Database schema + migrations
└── Chat D: CI/CD pipeline setup

Round 2 (Parallel after Round 1):
├── Chat A: CRUD endpoints (needs C)
├── Chat B: Feature components (needs A)
├── Chat C: Seed data + indexes
└── Chat E: Test suite setup

Round 3 (Integration):
├── Chat B: API integration
├── Chat D: Staging deployment
└── Chat E: E2E testing
```

## Files in This Example

```
software-development/
├── README.md                    # This file
├── COMMAND_CENTER.md            # Live status tracker
├── orders/
│   ├── order_chat_A_1.md       # Backend Round 1
│   ├── order_chat_B_1.md       # Frontend Round 1
│   ├── order_chat_C_1.md       # Database Round 1
│   └── order_chat_D_1.md       # DevOps Round 1
└── answers/
    └── (created by chats)
```

## How to Use This Example

1. **Copy this folder** to your project
2. **Customize the orders** for your specific requirements
3. **Update COMMAND_CENTER.md** with your project name
4. **Launch chats** with the order files
5. **Monitor and coordinate** from Command Center

## Tips for Software Development

### Minimize Dependencies
- Have Chat C (Database) finish schema early so A and B can build against it
- Use API contracts/interfaces so frontend can mock while backend builds

### Time Estimates
- API endpoints: 15-30 min each
- React components: 20-45 min each
- Database migrations: 10-20 min each
- CI/CD pipeline: 45-60 min

### Common Blockers
- Database schema changes mid-development
- API contract mismatches
- Environment configuration issues

### Mitigation
- Lock schema after Round 1
- Share API types/contracts between A and B early
- Have D set up environments in Round 1
