# 🚀 Startup Idea Validator — Multi-Agent Lab

> **Build a Shark Tank-style AI startup validator using connected agents in Microsoft AI Foundry**

[![Microsoft AI Foundry](https://img.shields.io/badge/Microsoft%20AI-Foundry-blue?logo=microsoft-azure)](https://ai.azure.com)
[![Level](https://img.shields.io/badge/Level-Beginner--Intermediate-green)]()
[![Duration](https://img.shields.io/badge/Duration-60--90%20min-orange)]()
[![No Code](https://img.shields.io/badge/Code-Not%20Required-brightgreen)]()

## 🎯 What You'll Build

A **multi-agent AI system** where four specialized AI agents work together to validate your startup idea — just like pitching to investors, but powered by AI!

```
  💡 Your Idea
       │
       ▼
┌──────────────┐     ┌─────────────────┐     ┌─────────────────┐     ┌───────────────┐
│  IDEA INTAKE │────▶│ MARKET RESEARCH │────▶│  SHARK TANK     │────▶│  PITCH DECK   │
│  AGENT       │     │ AGENT           │     │  SIMULATOR      │     │  GENERATOR    │
│              │     │                 │     │                 │     │               │
│  Clarifies & │     │  Analyzes       │     │  3 Investors    │     │  Creates a    │
│  structures  │     │  market fit     │     │  grill your     │     │  10-slide     │
│  your idea   │     │  & competition  │     │  idea!          │     │  pitch deck   │
└──────────────┘     └─────────────────┘     └─────────────────┘     └───────────────┘
       🧠                   📊                      🦈                      📑
```

## 📚 What You'll Learn

- How to create AI agents in Microsoft AI Foundry
- How to write effective agent instructions (system prompts)
- How to connect multiple agents into a workflow
- How agent-to-agent communication works (agents as tools)
- How to test and iterate on multi-agent systems
- Real-world concepts: market sizing, competitive analysis, pitching

## 🧑‍🎓 Who Is This For?

- College students exploring AI and entrepreneurship
- Anyone learning Microsoft AI Foundry for the first time
- Hackathon participants looking for a fun project
- No coding experience required!

## 📋 Prerequisites

Before starting, make sure you have:

| Requirement | Details |
|-------------|---------|
| **Azure Account** | [Free student account](https://azure.microsoft.com/free/students/) — no credit card required |
| **Microsoft AI Foundry Access** | Available at [ai.azure.com](https://ai.azure.com) |
| **Web Browser** | Chrome, Edge, Firefox, or Safari |
| **Time** | 60–90 minutes |

> 💡 **Tip:** With an Azure for Students account, you get $100 free credits — more than enough for this lab!

## 🗂️ Lab Structure

| Module | Title | Duration | Description |
|--------|-------|----------|-------------|
| **Lab 0** | [Prerequisites & Setup](lab-guide/00-prerequisites.md) | 10 min | Verify Azure access and understand the architecture |
| **Lab 1** | [Create AI Foundry Project](lab-guide/01-create-foundry-project.md) | 10 min | Set up your workspace in Microsoft AI Foundry |
| **Lab 2** | [Deploy AI Models](lab-guide/02-deploy-models.md) | 10 min | Deploy GPT-4o and GPT-4o-mini models |
| **Lab 3** | [Create the Agents](lab-guide/03-create-agents.md) | 20 min | Build all 4 agents with instructions |
| **Lab 4** | [Connect Agents as Workflow](lab-guide/04-connect-agents.md) | 10 min | Link agents together via the orchestrator |
| **Lab 5** | [Test in Playground](lab-guide/05-test-playground.md) | 15 min | Run test scenarios and observe the pipeline |
| **Lab 6** | [Challenge Exercises](lab-guide/06-challenge-exercises.md) | 15 min | Extend and customize your agents |
| **Lab 7** | [Cleanup](lab-guide/07-cleanup.md) | 5 min | Delete resources to avoid charges |

## 🏗️ Architecture Overview

This lab builds a **connected agent workflow** using Microsoft AI Foundry's Agent Playground:

- **Orchestrator Pattern** — The Idea Intake Agent acts as the coordinator, calling other agents as tools
- **Sequential Pipeline** — Each agent processes the output of the previous one
- **Specialized Roles** — Each agent has a focused purpose with tailored instructions

See the full [Architecture Diagram](assets/architecture.md) for details.

## ⚡ Quick Start

If you're already familiar with Microsoft AI Foundry and just want the agent instructions:

- [Idea Intake Agent Instructions](agent-instructions/idea-intake-agent.md)
- [Market Research Agent Instructions](agent-instructions/market-research-agent.md)
- [Shark Tank Simulator Instructions](agent-instructions/shark-tank-agent.md)
- [Pitch Deck Generator Instructions](agent-instructions/pitch-deck-agent.md)

## 🧪 Sample Test Scenarios

We've prepared [5 ready-to-use test scenarios](sample-inputs/test-scenarios.md) covering different startup ideas to validate your agents.

## 📝 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built for the Microsoft AI Foundry ecosystem
- Inspired by real-world startup accelerator processes
- Designed for college students and first-time AI explorers

---

**Ready to start? Head to [Lab 0: Prerequisites & Setup](lab-guide/00-prerequisites.md)** →
