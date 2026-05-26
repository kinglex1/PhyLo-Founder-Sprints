---
Agent ID: AGENT-001
Agent Role: Orchestrator / Research
Created: 2026-05-26
Type: Research Report
Topic: Multi-Agent Team Templates — Best Practices & Industry Standards
---

# Multi-Agent Team Templates Report

**Research Date:** 2026-05-26
**Prepared for:** Lex TheKing — PhyLo Startup
**Status:** Complete

---

## Executive Summary

Multi-agent AI teams are evolving rapidly. Gartner reports a **1,445% surge** in multi-agent system inquiries between Q1 2024 and Q2 2025. Enterprises achieve **40-60% efficiency gains** by replacing single-model AI with coordinated, specialized agent ecosystems.

This report analyzes the **top frameworks, real company examples, and best practices** to help you build the optimal agent team structure for PhyLo.

**Key Insight:** For a startup like PhyLo, the best template combines:
1. **Orchestrator** (strategic oversight, task routing)
2. **Specialists** (Researcher, Developer, QA)
3. **Shared knowledge base** (GitHub-synced workspace)
4. **Clear handoff protocols** between agents

---

## Part 1: Top Multi-Agent Frameworks

### 1.1 Microsoft AutoGen

**Overview:** Open-source framework for building LLM applications via multi-agent conversation.

**Key Patterns:**
| Pattern | Description | Best For |
|---------|-------------|----------|
| **Two-Agent Coding Pair** | Assistant + User Proxy for pair programming | Code development |
| **Group Chat** | Multiple agents conversing in a shared chat | Complex problem-solving |
| **Human-in-Loop** | Human approval at key decision points | High-stakes decisions |

**Architecture:**
```
[User] → [User Proxy] ↔ [Assistant Agent]
                        ↔ [Critic Agent]
                        ↔ [Executor Agent]
```

**Enterprise Use:** Azure deployment for production-grade, scalable multi-agent systems.

**Strengths:** Microsoft's backing, robust tooling, production-ready.
**Weaknesses:** Complex setup, requires coding knowledge.

---

### 1.2 CrewAI

**Overview:** Framework for orchestrating role-playing AI agents with true autonomy.

**Core Components:**
1. **Agents** — Autonomous units with specific skills
2. **Tasks** — Defined work items
3. **Tools** — Capabilities (web search, file ops, code execution)
4. **Crew** — Orchestrator combining agents and tasks

**Agent Roles (from documentation):**
| Role | Purpose | Example |
|------|---------|---------|
| Researcher | Gather & analyze info | Senior Data Researcher |
| Writer | Create content | Reporting Analyst |
| Code Developer | Write & debug code | Senior Python Developer |
| Data Analyst | Interpret datasets | Market Analyst |
| Security Auditor | Find vulnerabilities | Code Security Auditor |
| Customer Service | Assist users | Support Representative |

**Workflow Modes:**
- **Sequential:** Tasks complete one after another
- **Hierarchical:** Manager agent delegates to workers
- **Parallel:** Multiple tasks run simultaneously

**Strengths:** Role-based design, flexible task routing, memory management built-in.
**Weaknesses:** Requires Python setup, less visual debugging.

---

### 1.3 LangChain Agents

**Overview:** Tool-using agents with ReAct (Reason + Act) pattern.

**Pattern:**
```
Thought → Action → Observation → Thought → ...
```

**Key Features:**
- ReAct agent for reasoning + action
- Tool integration (search, calculators, APIs)
- Memory across conversations
- Chain-of-thought reasoning

**Strengths:** Mature ecosystem, extensive tool integrations.
**Weaknesses:** Verbose, steep learning curve.

---

### 1.4 OpenAI Swarm

**Overview:** Lightweight framework for agent handoffs.

**Key Concept:** Agents hand off conversations to other agents based on context.

**Pattern:**
```
Agent A (greeting) → handoff → Agent B (sales) → handoff → Agent C (support)
```

**Strengths:** Simple, lightweight, easy to understand.
**Weaknesses:** Newer, less battle-tested.

---

### 1.5 Azure AI Agent Patterns

**Official Microsoft patterns for enterprise deployment:**

| Pattern | Description | Use Case |
|---------|-------------|----------|
| **Sequential** | Tasks complete in order | Document processing pipeline |
| **Concurrent** | Parallel task execution | Independent research tasks |
| **Group Chat** | All agents discuss together | Collaborative problem-solving |
| **Handoff** | Context passed between agents | Customer service routing |
| **Magentic** | Central orchestrator + satellite agents | Complex workflows |

**For Startups:** Sequential + Handoff patterns work best for lean operations.

---

## Part 2: Real Company Examples & Templates

### 2.1 Spiral Scout — 3 Proven Templates

These are battle-tested templates from real deployments:

#### Template 1: CodeMind (Legacy Code Translator)
**Role:** Parses codebase, answers questions, suggests refactors

**Responsibilities:**
- Answer questions about codebase
- Suggest refactors
- Validate impact of changes
- Execute structural changes
- Visualize architectural patterns
- Warn when patterns are violated

**Works With:** GitHub repos, documentation

#### Template 2: TestForge (Self-Healing Test Suite)
**Role:** Auto-generates and maintains test suite

**Responsibilities:**
- Auto-generate tests
- Detect and correct broken tests
- Run vulnerability scans
- Create fuzz tests
- Prioritize high-impact areas

**Works With:** CI/CD pipelines, code repositories

#### Template 3: DevCompanion (AI Pair Programmer)
**Role:** Personalized coding assistance

**Responsibilities:**
- Learn coding style
- Suggest code snippets
- Integrate with issue trackers
- Automate routine tasks

**Works With:** IDE, Slack, issue trackers

---

### 2.2 Enterprise Multi-Agent Patterns (Built 10+ Systems)

**Lessons from building 10+ enterprise systems at scale:**

| Lesson | Description |
|--------|-------------|
| **Centralized State** | Use shared knowledge base, not just message history |
| **Clear Handoff Protocols** | Define exactly when one agent passes to another |
| **Cost Management** | Agents can make expensive calls — set limits |
| **Error Boundaries** | One agent fails → system fails. Build recovery paths |
| **Observability** | Log all agent actions for debugging |

---

### 2.3 Developer Team Templates (Reddit Community)

**Most popular multi-agent setups:**

```
Option A: Traditional Dev Team
┌─────────────┐
│ Orchestrator│
└──────┬──────┘
       │
  ┌────┴────┬────────┐
  ▼         ▼        ▼
Researcher  Dev     QA
```

```
Option B: Full-Stack Startup
┌─────────────┐
│ Orchestrator│
└──────┬──────┘
       │
  ┌────┴────┬────────┬────────┐
  ▼         ▼        ▼        ▼
Researcher  Dev     QA      Writer
```

---

## Part 3: Best Practices

### 3.1 Optimal Team Size

| Company Stage | Recommended Agents |
|--------------|-------------------|
| Solo Founder | 2-3 (Orchestrator + 1-2 specialists) |
| Early Startup | 3-5 (Full team) |
| Growing Startup | 5-7 (With specialists) |
| Enterprise | 10+ (Multiple crews) |

**For PhyLo:** 3-4 agents (Orchestrator + Dev + QA + Researcher/Writer)

---

### 3.2 Role Definitions

Each agent needs:
1. **Role Name** — What they do
2. **Goals** — What success looks like
3. **Backstory** — Why they exist
4. **Tools** — What they can access
5. **Boundaries** — What they shouldn't do

**Example: Dev Agent**
```
Role: Senior Python Developer
Goal: Write clean, tested code that solves the user's problem
Backstory: "You are an experienced developer who has shipped 
            production systems. You value clean code and thorough testing."
Tools: terminal, file_operations, web_search
Boundaries: Don't touch billing code without approval
```

---

### 3.3 Communication Patterns

| Pattern | When to Use |
|---------|-------------|
| **Direct Handoff** | Simple task routing (Agent A → Agent B) |
| **Group Chat** | Collaborative problem-solving |
| **Sequential Pipeline** | Document processing, multi-stage tasks |
| **Concurrent Workers** | Independent parallel tasks |
| **Supervisor Pattern** | Manager delegates, workers execute |

---

### 3.4 Quality Control

| Method | Description |
|--------|-------------|
| **Human-in-Loop** | Key decisions require human approval |
| **Peer Review** | One agent checks another's work |
| **Automated Tests** | QA agent runs test suite |
| **Output Validation** | Orchestrator reviews final output |

---

### 3.5 Error Handling

```
Agent Fails
    │
    ├─→ Log error to shared knowledge base
    ├─→ Notify orchestrator
    ├─→ Retry with exponential backoff (3 attempts)
    └─→ Escalate to human if persistent
```

---

## Part 4: Recommended Template for PhyLo

### 4.1 Your Agent Team Structure

```
┌─────────────────────────────────────────────────────────┐
│                    ORCHESTRATOR                         │
│                      (You/AGENT-001)                    │
│  • Strategic oversight                                    │
│  • Task routing                                          │
│  • Quality gate                                          │
│  • User communication                                    │
└─────────────────────┬───────────────────────────────────┘
                      │
        ┌─────────────┼─────────────┐
        │             │             │
        ▼             ▼             ▼
┌───────────────┐ ┌──────────┐ ┌──────────────┐
│  RESEARCHER   │ │   DEV    │ │     QA      │
│  (AGENT-002)  │ │ (Future) │ │  (Future)   │
│               │ │          │ │              │
│ • Web search  │ │ • Code   │ │ • Testing   │
│ • Data gather │ │ • Build  │ │ • Review    │
│ • Analysis    │ │ • Deploy │ │ • Validate  │
└───────────────┘ └──────────┘ └──────────────┘
        │
        ▼
┌───────────────┐
│   WRITER/     │
│  PRODUCER    │
│  (AGENT-003) │
│               │
│ • Content     │
│ • Reports     │
│ • Pitch deck  │
└───────────────┘
```

---

### 4.2 Agent Specifications

#### AGENT-001: Orchestrator (Currently Active)
```
Role: Orchestrator / Primary Agent
Tools: All (memory, skills, delegate, web, terminal, file)
Responsibilities:
  • Understand user goals
  • Break tasks into subtasks
  • Delegate to specialists
  • Synthesize results
  • Quality control final output
  • Manage GitHub sync
  • User communication
```

#### AGENT-002: Researcher (Recommended Next)
```
Role: Research & Discovery Specialist
Tools: web_search, web, extract_content, file_write
Responsibilities:
  • Market research
  • Competitor analysis
  • Data gathering
  • Information synthesis
  • Source validation
  • Save findings to CHAT_A/
```
**Trigger:** "Research [topic]" or when I need data to make decisions

#### AGENT-003: Writer/Producer (Recommended Next)
```
Role: Writing & Content Production Specialist
Tools: file_write, terminal, upload_to_cdn
Responsibilities:
  • Pitch deck creation
  • Report writing
  • Content drafting
  • Presentation building
  • Save outputs to CHAT_C/
```
**Trigger:** "Write [document]" or when research needs to become content

#### Future: Dev Agent
```
Role: Developer
Tools: terminal, file_write, execute_code, deploy
Responsibilities:
  • Code implementation
  • Feature building
  • API integrations
  • Deployment
  • Save code to appropriate folders
```

#### Future: QA Agent
```
Role: Quality Assurance
Tools: terminal, execute_code, file_read
Responsibilities:
  • Test execution
  • Code review
  • Bug detection
  • Output validation
  • Save test reports to CHAT_B/
```

---

### 4.3 Handoff Protocols

| Situation | Handoff |
|-----------|---------|
| User asks to research | Me → Researcher (AGENT-002) |
| Research complete, needs content | Researcher → Writer (AGENT-003) |
| Content needs technical accuracy | Writer → Dev |
| Need to build/test code | Me → Dev → QA |
| QA finds issues | QA → Dev (loop until fixed) |
| Final review | All → Me (Orchestrator) |

---

### 4.4 Shared Knowledge Base Structure

```
PhyLo-Founder-Sprints/
├── 00_PROJECT_OVERVIEW.md    ← Master reference
├── 00_SYNTHESIS.md          ← Combined work (auto-updated)
├── 00_START_HERE.md         ← Agent instructions
│
├── CHAT_A/                  ← Research outputs
│   ├── AGENT-002_*_research.md
│   └── README.md
│
├── CHAT_B/                  ← Analysis outputs
│   ├── AGENT-002_*_analysis.md
│   └── README.md
│
├── CHAT_C/                  ← Production outputs
│   ├── AGENT-003_*_draft.md
│   └── README.md
│
├── CODE/                    ← Dev agent code (future)
├── TESTS/                   ← QA agent tests (future)
└── SHARED_RESOURCES/        ← Common assets
```

---

## Part 5: Comparison Table

| Framework | Team Size | Setup Complexity | Best For | Enterprise Ready |
|-----------|-----------|------------------|----------|-----------------|
| AutoGen | 2-10+ | High | Code development | ✅ Yes |
| CrewAI | 3-5 | Medium | Role-based teams | ✅ Yes |
| LangChain | 2-5 | Medium | Tool-based agents | ✅ Yes |
| OpenAI Swarm | 2-3 | Low | Simple handoffs | ⚠️ New |
| Custom (Us) | Any | Low-Medium | Full control | ✅ Yes |

**Our Approach:** Custom GitHub-synced multi-agent with role-based specialization.

---

## Part 6: Implementation Roadmap

### Phase 1: Now (Orchestrator Only)
- [x] AGENT-001 active with memory
- [x] GitHub integration established
- [x] Dashboard deployed

### Phase 2: Next (Add Specialists)
- [ ] Create AGENT-002 (Researcher) prompts
- [ ] Create AGENT-003 (Writer) prompts
- [ ] Define handoff protocols
- [ ] Test collaboration flow

### Phase 3: Future (Dev + QA)
- [ ] Add Dev agent for code tasks
- [ ] Add QA agent for testing
- [ ] CI/CD integration
- [ ] Automated deployments

---

## Appendix: Resources

### Frameworks
- AutoGen: https://microsoft.github.io/autogen/
- CrewAI: https://docs.crewai.com/
- LangChain: https://python.langchain.com/docs/concepts/agents/
- OpenAI Swarm: https://github.com/openai/swarm

### Articles
- Azure AI Agent Patterns: https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns
- Enterprise Multi-Agent: https://beam.ai/agentic-insights/multi-agent-orchestration-patterns-production
- Spiral Scout Templates: https://spiralscout.com/blog/3-ai-agent-templates-to-steal

---

*Report compiled by AGENT-001*
*Sources: Microsoft AutoGen docs, CrewAI docs, Azure Architecture Center, Spiral Scout, Reddit r/AI_Agents, Enterprise case studies*

---

## Next Steps for PhyLo

Based on this research, I recommend:

1. **Activate AGENT-002** as Researcher — next time you need market research or data
2. **Activate AGENT-003** as Writer/Producer — for content and pitch deck work
3. **Establish protocols** — define clear handoff rules
4. **Scale to Dev+QA** — when you have code to build

Want me to:
- Create detailed prompts for AGENT-002 and AGENT-003?
- Set up automated handoff workflows?
- Build the next phase of the agent team?

Let me know how you want to proceed!