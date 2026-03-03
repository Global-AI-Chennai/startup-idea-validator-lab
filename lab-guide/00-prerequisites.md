# Lab 0: Prerequisites & Setup

> **Duration:** 10 minutes

## 🎯 Objective

Ensure you have everything ready before building your multi-agent startup validator.

## ✅ Checklist

### 1. Azure Account

You need an active Azure subscription. Choose one:

| Option | Best For | Link |
|--------|----------|------|
| **Azure for Students** | College students (no credit card) | [Sign up free](https://azure.microsoft.com/free/students/) |
| **Azure Free Account** | Anyone (requires credit card, no charge) | [Sign up free](https://azure.microsoft.com/free/) |
| **Existing subscription** | Already have Azure | [Portal](https://portal.azure.com) |

> 🎓 **Students:** Azure for Students gives you **$100 in credits** with just your .edu email. No credit card required!

### 2. Verify Azure AI Foundry Access

1. Open [https://ai.azure.com](https://ai.azure.com)
2. Sign in with your Azure account
3. You should see the AI Foundry home page
4. If you see an error, ensure your subscription is active

### 3. Check Regional Availability

The models we use (GPT-4o, GPT-4o-mini) are available in specific regions. Recommended regions:

| Region | GPT-4o | GPT-4o-mini |
|--------|--------|-------------|
| **East US** | ✅ | ✅ |
| **East US 2** | ✅ | ✅ |
| **Sweden Central** | ✅ | ✅ |
| **West US 3** | ✅ | ✅ |

> 💡 **Recommendation:** Use **East US** or **Sweden Central** for the best availability.

## 🧠 Understanding the Architecture

Before we build, let's understand what we're creating:

### What Are AI Agents?

An **AI agent** is an AI model (like GPT-4o) configured with:
- **Instructions** — A system prompt that defines its personality and expertise
- **Tools** — Optional capabilities like file search, code execution, or calling other agents
- **Knowledge** — Optional documents the agent can reference

### What Are Connected Agents?

Connected agents are **multiple agents that work together** in a workflow. In our setup:

1. **Orchestrator Agent** — The "boss" that coordinates the workflow
2. **Specialist Agents** — Experts in specific tasks (market research, investor simulation, etc.)
3. **Agent-as-Tool** — Specialist agents are added as tools to the orchestrator, so it can call them

### Our Pipeline

```
User submits startup idea
        │
        ▼
┌─ IDEA INTAKE AGENT (Orchestrator) ────────────────────┐
│                                                        │
│   1. Clarifies the idea                                │
│   2. Calls → Market Research Agent                     │
│   3. Calls → Shark Tank Simulator Agent                │
│   4. Calls → Pitch Deck Generator Agent                │
│   5. Compiles final report                             │
│                                                        │
└────────────────────────────────────────────────────────┘
        │
        ▼
  Final startup validation report
```

## 🎯 What Success Looks Like

By the end of this lab, you'll be able to:

1. ✅ Type a startup idea into the chat
2. ✅ Watch the orchestrator activate each specialist agent
3. ✅ Receive a comprehensive validation report including:
   - Structured idea summary
   - Market analysis with TAM/SAM/SOM
   - Shark Tank-style investor feedback
   - 10-slide pitch deck outline

## ➡️ Next Step

Ready? Let's create your AI Foundry project!

**Next: [Lab 1 — Create AI Foundry Project](01-create-foundry-project.md)** →
