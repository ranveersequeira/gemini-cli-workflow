🧠 Gemini CLI Multi-Agent Development Workflow

A disciplined, repo-aware AI development system using Gemini CLI, tmux, strict workflows, and Git automation.

🎥 Demo video: (attached separately)

🔍 What This Repository Is

This repository documents how I use Gemini CLI as a multi-agent engineering system, not as a chat tool.

It explains:

Named Gemini agents and their responsibilities

tmux-based orchestration

Repo-level workflow enforcement (gemini.md)

Automated commit generation

LazyGit as a verification layer

🧠 High-Level Architecture
                ┌───────────────┐
                │   Gemini CLI  │
                └───────┬───────┘
                        │
        ┌────────────────────────────────┐
        │              tmux              │
        │  (persistent multi-agent grid) │
        │                                │
        │  ┌────────┐ ┌────────┐        │
        │  │Backend │ │Frontend│        │
        │  ├────────┤ ├────────┤        │
        │  │Tests   │ │Review  │        │
        │  ├────────┤ ├────────┤        │
        │  │Commit  │ │LazyGit │        │
        │  └────────┘ └────────┘        │
        └───────────────┬────────────────┘
                        │
                    Git Repos

🤖 Gemini Multi-Agent System

Instead of one general AI session, this workflow uses multiple named Gemini agents, each with a single, strict responsibility.

📁 Agent Location

All agents live in:

/gemini/agents


Each agent has:

A fixed role

Clear boundaries

No cross-responsibility behavior

🧩 Available Agents (With Names)
Agent Name	Responsibility
Generic Feature Planner	Requirement clarification, no code
System Orchestrator	Task breakdown & execution order
Backend Node Agent	APIs, business logic, auth
Frontend React Agent	UI, state, client logic
Database MongoDB Agent	Schemas, queries, migrations
Test & Quality Agent	Unit/integration tests
Review Agent	Code review & refactoring
Documentation Agent	README, API docs
Commit Agent	Automated commit messages

Each agent is invoked intentionally and runs in its own tmux pane.

🧵 tmux as the Orchestrator

tmux is used to run agents in parallel, each with persistent context.

Session: feature-auth

┌─────────────────────────────┐
│ Backend Node Agent │ Frontend│
├────────────────────┼────────┤
│ Test & Quality     │ LazyGit│
└─────────────────────────────┘


Why tmux:

One session per feature

One pane per agent

Keyboard-driven

No context loss

📜 Repo-Level Rules (gemini.md)

Every code repository contains a gemini.md file.

This file defines:

What the repo owns

Which agents are allowed

Mandatory workflow steps

Definition of Done

Repo rules > user instructions > agent defaults


Gemini must read and obey gemini.md first.

🔁 Mandatory Workflow (Strict)

All agents must follow this order:

PLAN        → Generic Feature Planner
BREAKDOWN   → System Orchestrator
IMPLEMENT   → Backend / Frontend / DB Agents
TEST        → Test & Quality Agent
REVIEW      → Review Agent
DOCUMENT    → Documentation Agent


Skipping a step = work is incomplete.

📝 Commit Agent (Fully Automated)

The Commit Agent handles Git commits automatically.

git add .
     ↓
read recent commits
     ↓
read current diff
     ↓
Gemini generates commit message
     ↓
git commit


Example:

feat(auth): add refresh token rotation


This keeps Git history:

Clean

Consistent

Intent-focused

🔍 LazyGit (Human Verification)

LazyGit is used only to inspect, never to author commits.

AI → writes commits
Human → verifies


Used for:

Diffs

Branches

History

Conflicts

🔄 End-to-End Flow
Create tmux session
      ↓
Agents read gemini.md
      ↓
Run agents in parallel
      ↓
Verify in LazyGit
      ↓
Commit Agent runs
      ↓
Done ✅

🎯 Why This Setup Works

Named agents reduce ambiguity

Repo rules prevent AI misuse

tmux enables parallel execution

Automation removes friction

Git history stays readable

Same AI, different discipline.

🧠 Philosophy

AI should follow architecture, not invent it.
Constraints create speed.
Automation preserves intent.

📎 Demo Video

The attached video shows:

tmux agent layout

Agent invocation

Repo-level rule enforcement

Commit automation

LazyGit inspection

🚀 Future Extensions

Auto-generate agents per repo

CI enforcement for gemini.md

Monorepo-aware agent scopes

Team-wide agent standards
