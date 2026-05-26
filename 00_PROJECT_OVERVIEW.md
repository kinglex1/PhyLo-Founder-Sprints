# Project Central — Shared Knowledge Base

## Purpose
This directory is the **single source of truth** for all agent work across different chat sessions. All agents working on this project should save their outputs here and read existing work before starting new tasks.

---

## Directory Structure

```
/memories/project_central/
├── 00_PROJECT_OVERVIEW.md    ← Project goals, scope, current state
├── 00_START_HERE.md          ← Instructions for new agents
├── CHAT_A/                   ← Outputs from Chat A (research agent)
│   └── README.md
├── CHAT_B/                   ← Outputs from Chat B (analysis agent)
│   └── README.md
├── CHAT_C/                   ← Outputs from Chat C (writing agent)
│   └── README.md
├── SHARED_RESOURCES/          ← Shared files, data, templates
└── 00_SYNTHESIS.md           ← Merged synthesis of all agent work
```

---

## Usage Protocol

### For Every Agent:
1. **Start here** → Read `00_PROJECT_OVERVIEW.md` and `00_START_HERE.md`
2. **Check for existing work** → Look in relevant CHAT_X/ folders
3. **Save your work** → To your designated chat folder with date/timestamp
4. **Update synthesis** → Add a summary to `00_SYNTHESIS.md`

### Naming Convention for Output Files:
```
[CHAT_NAME]_[YYYY-MM-DD]_[task-name].md
Example: CHAT_A_2026-05-26_research-findings.md
```

---

## Agent IDs (Required for Tracking)

Every chat/agent is assigned a unique ID. **Always include your ID in outputs.**

| Chat | Agent ID | Role | Folder |
|------|----------|------|--------|
| This Chat | `AGENT-001` | (assign based on role) | `CHAT_A/` |
| Chat B | `AGENT-002` | (assign based on role) | `CHAT_B/` |
| Chat C | `AGENT-003` | (assign based on role) | `CHAT_C/` |

**Your current Agent ID:** `AGENT-001`

---

## Last Updated
Created: 2026-05-26
Updated: 2026-05-26 (added Agent IDs)
