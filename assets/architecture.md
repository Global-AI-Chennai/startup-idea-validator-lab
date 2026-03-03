# Architecture Diagram

## High-Level Architecture

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        MICROSOFT AI FOUNDRY PROJECT                         │
│                        (startup-validator-lab)                               │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────┐        │
│  │                     MODEL DEPLOYMENTS                           │        │
│  │                                                                 │        │
│  │    ┌──────────────────┐        ┌──────────────────┐            │        │
│  │    │    GPT-4o         │        │   GPT-4o-mini    │            │        │
│  │    │  (Complex tasks)  │        │  (Simple tasks)  │            │        │
│  │    └──────────────────┘        └──────────────────┘            │        │
│  └─────────────────────────────────────────────────────────────────┘        │
│                                                                             │
│  ┌─────────────────────────────────────────────────────────────────┐        │
│  │                      AGENT PIPELINE                             │        │
│  │                                                                 │        │
│  │   👤 User                                                       │        │
│  │    │                                                            │        │
│  │    │  "I want to build an app that..."                          │        │
│  │    │                                                            │        │
│  │    ▼                                                            │        │
│  │   ┌──────────────────────────────────────────────┐              │        │
│  │   │  ⭐ IDEA INTAKE AGENT (Orchestrator)         │              │        │
│  │   │     Model: GPT-4o                            │              │        │
│  │   │     Role: Coordinates the full pipeline      │              │        │
│  │   │                                              │              │        │
│  │   │  Tools:                                      │              │        │
│  │   │  ├── 🔧 Market Research Agent                │              │        │
│  │   │  ├── 🔧 Shark Tank Simulator Agent           │              │        │
│  │   │  └── 🔧 Pitch Deck Generator Agent           │              │        │
│  │   └──────────────────┬───────────────────────────┘              │        │
│  │                      │                                          │        │
│  │          ┌───────────┼───────────────┐                          │        │
│  │          │           │               │                          │        │
│  │          ▼           ▼               ▼                          │        │
│  │   ┌────────────┐ ┌────────────┐ ┌────────────┐                 │        │
│  │   │  MARKET    │ │ SHARK TANK │ │ PITCH DECK │                 │        │
│  │   │  RESEARCH  │ │ SIMULATOR  │ │ GENERATOR  │                 │        │
│  │   │  AGENT     │ │ AGENT      │ │ AGENT      │                 │        │
│  │   │            │ │            │ │            │                  │        │
│  │   │  GPT-4o    │ │  GPT-4o    │ │ GPT-4o-mini│                 │        │
│  │   │            │ │            │ │            │                  │        │
│  │   │ • TAM/SAM  │ │ • 3 Shark  │ │ • 10-slide │                 │        │
│  │   │ • Competi- │ │   Investors│ │   pitch    │                 │        │
│  │   │   tors     │ │ • Q&A      │ │   deck     │                 │        │
│  │   │ • Risks    │ │ • Verdicts │ │ • Strategy │                 │        │
│  │   └─────┬──────┘ └─────┬──────┘ └──────┬─────┘                 │        │
│  │         │              │               │                        │        │
│  │         └──────────────┼───────────────┘                        │        │
│  │                        │                                        │        │
│  │                        ▼                                        │        │
│  │              ┌──────────────────┐                               │        │
│  │              │  FINAL REPORT    │                               │        │
│  │              │  • Idea Summary  │                               │        │
│  │              │  • Market Rating │                               │        │
│  │              │  • Investor Score│                               │        │
│  │              │  • Pitch Deck    │                               │        │
│  │              │  • Action Items  │                               │        │
│  │              └────────┬─────────┘                               │        │
│  │                       │                                         │        │
│  │                       ▼                                         │        │
│  │                    👤 User                                      │        │
│  └─────────────────────────────────────────────────────────────────┘        │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

## Data Flow

```
Step 1                Step 2                Step 3                Step 4
──────────           ──────────           ──────────           ──────────

User Input     ──▶   Orchestrator   ──▶   Orchestrator   ──▶   Orchestrator
"My startup          structures            sends idea           sends idea +
idea is..."          the idea              summary to           market data +
                     into:                 Market Research      investor feedback
                     • Problem             Agent                to Pitch Deck
                     • Solution                                 Agent
                     • Market         ──▶  Orchestrator
                     • Revenue             sends idea +
                       Model               market data to
                                           Shark Tank Agent


Step 5
──────────

Orchestrator
compiles all
outputs into
Final Report
     │
     ▼
👤 User sees
complete
validation
```

## Agent Communication Pattern

This lab uses the **Orchestrator Pattern**:

```
                    ┌─────────────────────┐
                    │                     │
              ┌────▶│  Specialist Agent 1 │────┐
              │     │                     │    │
              │     └─────────────────────┘    │
              │                                │
┌──────────┐  │     ┌─────────────────────┐    │    ┌──────────┐
│          │──┼────▶│  Specialist Agent 2 │────┼───▶│          │
│  User    │  │     │                     │    │    │  User    │
│  Input   │  │     └─────────────────────┘    │    │  Output  │
│          │──┤                                ├───▶│          │
└──────────┘  │     ┌─────────────────────┐    │    └──────────┘
              │     │                     │    │
              └────▶│  Specialist Agent 3 │────┘
                    │                     │
                    └─────────────────────┘
                    
              ▲                                ▲
              │     ORCHESTRATOR AGENT          │
              │     controls the flow           │
              └────────────────────────────────┘
```

**Key:** The user ONLY interacts with the Orchestrator. The Orchestrator calls specialists as tools and compiles their outputs.

## Azure Resource Hierarchy

```
Azure Subscription
 └── Resource Group (rg-startup-validator)
      └── AI Foundry Hub (ai-foundry-hub-lab)
           ├── AI Services Resource
           │    ├── gpt-4o deployment
           │    └── gpt-4o-mini deployment
           ├── Storage Account (auto-created)
           └── AI Foundry Project (startup-validator-lab)
                ├── Idea Intake Agent ⭐
                ├── Market Research Agent
                ├── Shark Tank Simulator Agent
                └── Pitch Deck Generator Agent
```
