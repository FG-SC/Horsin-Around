# Best Practices

Lessons learned from real-world parallel AI coordination projects.

## For Commanders (You)

### Planning

**Break work into truly parallel tasks**
- Tasks in the same round should have no dependencies on each other
- If Task B needs Task A's output, put them in different rounds
- Aim for 3-5 parallel chats for optimal coordination overhead

**Set realistic time estimates**
- Add 20% buffer for first-time tasks
- Track actuals and adjust future estimates
- Complex tasks take longer than they seem

**Create clear boundaries**
- Each chat should have ONE clear focus area
- Overlap causes confusion and duplicate work
- When in doubt, make boundaries narrower

### During Execution

**Check in every 15 minutes**
- Quick scan of progress updates
- Address questions promptly
- Update Command Center status

**Respond to blockers fast**
- A blocked chat = wasted parallel capacity
- Aim for <10 minute response to blocker alerts
- If you can't respond, give the chat a workaround

**Don't micro-manage**
- Let chats work through normal challenges
- Only intervene on blockers and timeouts
- Trust the process

### After Each Round

**Review all answer files**
- Check for quality issues before next round
- Look for cross-chat coordination problems
- Note estimation accuracy for improvement

**Update estimates for next round**
- If Chat A took 45 min on a "30 min" task, similar tasks need adjustment
- Share learnings across chats

**Celebrate wins**
- Acknowledge good work in Command Center
- Note what went well for future reference

---

## For Chat Agents

### Starting a Task

**Read the entire order first**
- Understand the full scope before starting
- Note dependencies and related work
- Clarify questions BEFORE starting work

**Set up time tracking immediately**
- Copy the time tracking template
- Fill in start time
- Set a timer for the timeout threshold

### During Execution

**Update progress regularly**
- Every 15 minutes, note your status
- Don't wait until you're stuck to communicate
- Brief updates are fine: "Task 1 done, starting Task 2"

**Follow the 10% rule strictly**
- If you hit timeout, STOP
- Don't push through hoping to finish
- Create an alert and wait

**Ask questions early**
- If something is unclear, ask immediately
- Don't guess and build on wrong assumptions
- Questions are cheaper than rework

### Completing a Task

**Fill out the full answer template**
- Time tracking summary
- What was done
- What issues came up
- Lessons learned

**Be honest about problems**
- Partial completion is fine if documented
- Hidden issues cause bigger problems later
- Note what you'd do differently

---

## Coordination Patterns

### The Handoff Pattern

When Chat A produces something Chat B needs:

```
Round 1:
├── Chat A: Create API contracts ──► outputs API_SPEC.md
└── Chat B: Create UI components (independent)

Round 2:
├── Chat A: Implement API endpoints
└── Chat B: Integrate with API ◄── reads API_SPEC.md
```

**Key:** Chat A must explicitly create the handoff artifact.

### The Mirror Pattern

Pair a builder with a validator:

```
Chat A: Build feature
Chat B: Test feature (in parallel or immediately after)
```

**Key:** Chat B can start testing as soon as Chat A has testable output.

### The Specialist Pattern

Assign by expertise, not by feature:

```
Instead of:
├── Chat A: Feature 1 (frontend + backend + tests)
└── Chat B: Feature 2 (frontend + backend + tests)

Do:
├── Chat A: All backend work
├── Chat B: All frontend work
└── Chat C: All testing
```

**Key:** Specialists work faster and produce more consistent output.

---

## Common Pitfalls

### 1. Too Many Dependencies

**Symptom:** Chats constantly waiting on each other

**Solution:**
- Redesign round structure
- Create mock data for Round 1
- Reduce parallel count

### 2. Vague Orders

**Symptom:** Questions flood in, output doesn't match expectations

**Solution:**
- Add specific examples to orders
- Include success criteria
- Reference similar past work

### 3. Ignoring Timeouts

**Symptom:** Tasks run 2-3x over estimate, blocking other work

**Solution:**
- Enforce the 10% rule strictly
- Review why estimates were wrong
- Break large tasks smaller

### 4. Scope Creep

**Symptom:** "While I was doing X, I also did Y and Z"

**Solution:**
- Clear boundaries in orders
- Explicit "out of scope" list
- Review answer files for unauthorized changes

### 5. Communication Overload

**Symptom:** More time coordinating than working

**Solution:**
- Reduce parallel chat count
- Increase round duration
- Create clearer upfront plans

---

## Scaling Guidelines

### 2-3 Chats
- Simple coordination
- Commander can manage casually
- Good for small projects or learning the system

### 4-5 Chats
- Sweet spot for most projects
- Requires dedicated commander attention
- 15-minute check-ins essential

### 6+ Chats
- Consider adding a deputy commander
- Group chats into "squads" with sub-commanders
- Use automated monitoring if possible

---

## Metrics That Matter

### Estimation Accuracy
```
Accuracy = Estimated Time / Actual Time × 100%
```
- Target: 80-120%
- Track per chat and task type
- Use to improve future estimates

### On-Time Rate
```
On-Time Rate = Tasks Completed Within Timeout / Total Tasks × 100%
```
- Target: 90%+
- Low rate = estimates too aggressive

### Blocker Resolution Time
```
Resolution Time = Time Question Answered - Time Question Asked
```
- Target: <10 minutes
- Long resolution = commander bottleneck

### Parallel Efficiency
```
Efficiency = Sum of All Task Durations / (Elapsed Wall Time × Number of Chats) × 100%
```
- Target: 70%+
- Low efficiency = too many dependencies

---

## Template Customization

Feel free to adapt templates to your needs:

### Simplify for quick projects
- Remove metrics sections
- Shorter answer templates
- Skip time tracking for <15 min tasks

### Expand for complex projects
- Add risk assessment to orders
- Include rollback plans
- Add approval checkpoints

### Add domain-specific sections
- Code review checklist for dev projects
- Citation requirements for research
- Brand guidelines for content
