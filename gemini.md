# Gemini Usage Guide – Backend Repository

This repository contains the Node.js backend and APIs.
Gemini must be used strictly according to the workflow defined below.

---

## 1. Repository Scope

This repo owns:
- Business logic
- API behavior
- Authentication and validation
- Database access

This repo does NOT own:
- UI logic
- UX decisions
- Client-side state

---

## 2. Tech Stack

- Node.js (LTS)
- Express or Fastify
- MongoDB
- Mongoose
- Jest / Supertest

---

## 3. Allowed AI Agents

Only the following agents are allowed in this repo:

- Generic Feature Planner
- System Orchestrator
- Backend Node Agent
- Database MongoDB Agent
- Test & Quality Agent
- Review Agent
- Documentation Agent

❌ Frontend React Agent is NOT allowed

---

## 4. Mandatory Workflow (DO NOT SKIP)

### STEP 1 — PLAN (NO CODE)

Use Generic Feature Planner.
Discuss API behavior, authentication, and data flow.
STOP if requirements are unclear.

---

### STEP 2 — BREAKDOWN

Use System Orchestrator.
Confirm backend and database tasks.

---

### STEP 3 — IMPLEMENT

Use Backend Node Agent.
Implement API and business logic.

Use Database MongoDB Agent.
Implement schema and query changes.

---

### STEP 4 — TEST

Use Test & Quality Agent.
Add or update backend tests.

---

### STEP 5 — REVIEW

Use Review Agent.
Review backend code and database impact.

---

### STEP 6 — DOCUMENT

Use Documentation Agent.
Update API docs, schema docs, and README.

---

## 5. Definition of Done

A change is considered complete only if:
- Planning is approved
- Tests are added or updated
- Review is approved
- Documentation is updated
