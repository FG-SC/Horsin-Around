# Order for Chat B - Round 1

**From:** Commander
**To:** Chat B (Frontend Developer)
**Date:** 2025-01-15
**Priority:** High
**Estimated Duration:** 60 minutes

---

## Mission

Set up the React frontend structure and build the core UI component library.

---

## Context

We're building a task management application. You're responsible for the React frontend with TypeScript. Chat A is building the API simultaneously - you'll integrate in Round 2. For now, focus on UI components that can work with mock data.

**Dependencies:**
- None - can start immediately
- API contracts from Chat A will be ready by end of Round 1

---

## Tasks

### Task 1: Project Setup (15 min)

**Goal:** Initialize the React project with proper tooling

**Steps:**
1. Create React app with Vite and TypeScript
2. Set up folder structure:
   ```
   src/
   ├── components/
   │   ├── ui/           # Reusable UI components
   │   └── features/     # Feature-specific components
   ├── hooks/
   ├── services/         # API calls
   ├── types/
   ├── utils/
   └── pages/
   ```
3. Install and configure Tailwind CSS
4. Set up routing (React Router)

**Expected output:** Running React app with routing

---

### Task 2: UI Component Library (30 min)

**Goal:** Build reusable UI components

**Steps:**
1. Create base components:
   - Button (primary, secondary, danger variants)
   - Input (text, password, with validation states)
   - Card (container component)
   - Modal (for dialogs)
   - LoadingSpinner
2. Add proper TypeScript types for all props
3. Include basic styling with Tailwind

**Expected output:**
- 5+ reusable components
- Components work standalone with props

---

### Task 3: Layout & Pages Shell (15 min)

**Goal:** Create the application layout structure

**Steps:**
1. Create layout components:
   - MainLayout (header, sidebar, content area)
   - AuthLayout (for login/register pages)
2. Create page shells (empty but routed):
   - LoginPage
   - RegisterPage
   - DashboardPage
   - TaskListPage
3. Set up routes

**Expected output:**
- Navigation between pages works
- Layouts render correctly

---

## Deliverables

1. `answer_chat_B_1.md` - Your results (required)
2. All source code in appropriate folders
3. `COMPONENT_LIBRARY.md` - Document your components

---

## Time Tracking (Required)

| Task | Estimated | Started | Actual | Status |
|------|-----------|---------|--------|--------|
| Project Setup | 15m | | | Pending |
| UI Components | 30m | | | Pending |
| Layout & Pages | 15m | | | Pending |
| **Total** | **60m** | | | |

**Timeout threshold:** 66 minutes (60 + 10%)

---

## Success Criteria

- [ ] React app runs without errors
- [ ] All 5+ UI components render correctly
- [ ] Components have proper TypeScript types
- [ ] Routing works between all pages
- [ ] Layouts display correctly

---

## If You Get Stuck

- **Styling choices:** Use Tailwind defaults, keep it simple
- **API types:** Create placeholder types, will sync with Chat A in Round 2
- **Unclear requirements:** Create `question_B_to_commander_1.md`

---

## Related Work

- Chat A is creating API - you'll integrate in Round 2
- Chat D will need your app for CI/CD pipeline
- Chat E will test your components in Round 2

---

**Ready? Start your time tracking and go!**
