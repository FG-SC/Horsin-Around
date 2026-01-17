# Order for Chat A - Round 1

**From:** Commander
**To:** Chat A (Backend Developer)
**Date:** 2025-01-15
**Priority:** High
**Estimated Duration:** 60 minutes

---

## Mission

Set up the backend API structure and implement the authentication system.

---

## Context

We're building a task management application. You're responsible for the REST API using Node.js/Express with TypeScript. Chat C is working on the database schema simultaneously - coordinate on user table structure.

**Dependencies:**
- None - can start immediately
- Note: Database schema from Chat C will be ready by end of Round 1

---

## Tasks

### Task 1: Project Setup (15 min)

**Goal:** Initialize the backend project with proper structure

**Steps:**
1. Initialize Node.js project with TypeScript
2. Set up Express with middleware (cors, helmet, body-parser)
3. Create folder structure:
   ```
   src/
   ├── controllers/
   ├── routes/
   ├── middleware/
   ├── services/
   ├── types/
   └── utils/
   ```
4. Configure environment variables

**Expected output:** Working Express server on port 3000

---

### Task 2: Authentication Endpoints (30 min)

**Goal:** Implement user authentication with JWT

**Steps:**
1. Create auth controller with:
   - POST /api/auth/register
   - POST /api/auth/login
   - POST /api/auth/logout
   - GET /api/auth/me
2. Implement JWT token generation and validation
3. Create auth middleware for protected routes
4. Add input validation

**Expected output:**
- Working auth endpoints (can test with Postman/curl)
- JWT middleware ready for use

---

### Task 3: API Documentation (15 min)

**Goal:** Document the API for Chat B (Frontend)

**Steps:**
1. Create API_CONTRACTS.md with endpoint specifications
2. Include request/response types
3. Document error codes and formats

**Expected output:** API documentation that Chat B can use

---

## Deliverables

1. `answer_chat_A_1.md` - Your results (required)
2. All source code in appropriate folders
3. `API_CONTRACTS.md` - For Chat B to use
4. `.env.example` file

---

## Time Tracking (Required)

| Task | Estimated | Started | Actual | Status |
|------|-----------|---------|--------|--------|
| Project Setup | 15m | | | Pending |
| Auth Endpoints | 30m | | | Pending |
| API Documentation | 15m | | | Pending |
| **Total** | **60m** | | | |

**Timeout threshold:** 66 minutes (60 + 10%)

---

## Success Criteria

- [ ] Express server runs without errors
- [ ] All 4 auth endpoints respond correctly
- [ ] JWT tokens are generated and validated
- [ ] Auth middleware protects routes
- [ ] API documentation is complete and clear

---

## If You Get Stuck

- **Database connection:** Use in-memory store for now, Chat C will provide schema
- **JWT secret:** Use environment variable, document in .env.example
- **Unclear requirements:** Create `question_A_to_commander_1.md`

---

## Related Work

- Chat B needs your API_CONTRACTS.md to build frontend
- Chat C is creating user table - coordinate on field names
- Chat D will need your app for CI/CD pipeline

---

**Ready? Start your time tracking and go!**
