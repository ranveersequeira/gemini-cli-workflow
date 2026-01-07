## NOTE: Development in Progress still working on it to optimize.
# 🧠 Gemini CLI Multi-Agent Development Workflow

A disciplined, repo-aware AI development system using **Gemini CLI**, **tmux**, **strict workflows**, and **Git automation**.

### Medium Blog - https://ranveersequeira.medium.com/building-full-stack-applications-with-gemini-cli-tmux-a-repo-first-multi-agent-workflow-27c082ea5d83

## 🎥 Demo Videos

- 🎥 **Demo video:** [DEMO0] https://youtu.be/FPjAs8YO6NY?si=l45VUbCOHhpjf2rK
- 🎥 **Demo video:** [DEMO1] https://youtu.be/UNB4EYiQWMI?si=274ncOjtnikashuP


---


## 🔍 What This Repository Is

This repository documents **how I use Gemini CLI as a multi-agent engineering system**, not as a chat tool.

It explains:
- Named Gemini agents and their responsibilities
- tmux-based orchestration
- Repo-level workflow enforcement (`gemini.md`)
- Automated commit generation
- LazyGit as a verification layer

This setup is designed to scale across **features, repos, and stacks**.

---

## 🧠 High-Level Architecture

```
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
```

---

## 🤖 Gemini Multi-Agent System

Instead of one general AI session, this workflow uses **multiple named Gemini agents**, each with **a single, strict responsibility**.

### 📁 Agent Location

All agents live in:

```
/gemini/agents
```

Each agent is purpose-built and must not exceed its responsibility.

---

## 🧩 Available Agents

| Agent Name | Responsibility |
|-----------|---------------|
| **Generic Feature Planner** | Clarify requirements, no code |
| **System Orchestrator** | Task breakdown & execution order |
| **Backend Node Agent** | APIs, business logic, auth |
| **Frontend React Agent** | UI, state, client logic |
| **Database MongoDB Agent** | Schemas, queries, migrations |
| **Test & Quality Agent** | Unit & integration tests |
| **Review Agent** | Code review & refactoring |
| **Documentation Agent** | README & API docs |
| **Commit Agent** | Automated commit messages |

Each agent typically runs in its **own tmux pane**.

---

## 🧵 tmux as the Orchestrator

tmux manages **parallel execution** and **persistent context**.

```
Session: feature-auth

┌─────────────────────────────┐
│ Backend Node Agent │ Frontend│
├────────────────────┼────────┤
│ Test & Quality     │ LazyGit│
└─────────────────────────────┘
```

Why tmux:
- One session per feature
- One pane per agent
- Keyboard-driven workflow
- No context loss

---

## 📜 Repo-Level Rules (`gemini.md`)

Every **code repository** using this system contains a `gemini.md` file.

This file defines:
- Repository ownership & scope
- Allowed agents
- Mandatory workflow
- Definition of Done

```
Repo rules > user instructions > agent defaults
```

Gemini **must read and obey `gemini.md` first**.

---

## 🔁 Mandatory Workflow (Strict)

All work follows this exact order:

```
PLAN        → Generic Feature Planner
BREAKDOWN   → System Orchestrator
IMPLEMENT   → Backend / Frontend / DB Agents
TEST        → Test & Quality Agent
REVIEW      → Review Agent
DOCUMENT    → Documentation Agent
```

Skipping a step means the work is **not complete**.

---

## 📝 Commit Agent (Automated)

Git commits are handled by a **Gemini-powered Commit Agent**.

```
git add .
     ↓
read recent commits
     ↓
read current diff
     ↓
Gemini generates commit message
     ↓
git commit
```

Example commit:
```
feat(auth): add refresh token rotation
```

This ensures:
- Clean commit history
- Consistent style
- Intent-focused messages

---

## 🔍 LazyGit (Human Verification Layer)

LazyGit is used **only for inspection**, never for writing commits.

```
AI → creates commits
Human → verifies visually
```

Used for:
- Diff inspection
- Branch management
- History review
- Conflict resolution

---

## 🔄 End-to-End Flow

```
Create tmux session
      ↓
Agents read gemini.md
      ↓
Run agents in parallel
      ↓
Inspect changes in LazyGit
      ↓
Run Commit Agent
      ↓
Done ✅
```

---

## 🎯 Why This Workflow Works

- Named agents reduce ambiguity
- Repo rules prevent AI misuse
- tmux enables parallel execution
- Automation removes friction
- Git history stays readable

> **Same AI, different discipline.**

---

## 🧠 Philosophy

> **AI should follow architecture, not invent it.**  
> **Constraints create speed.**  
> **Automation preserves intent.**

---

## 📎 Demo Video

The attached video demonstrates:
- tmux session layout
- Agent execution
- Repo-level rule enforcement
- Commit automation
- LazyGit inspection

---

## 🚀 Future Extensions

- Auto-generate `gemini.md` per repo
- CI enforcement of workflow rules
- Monorepo-aware agent scopes
- Team-wide agent standards
