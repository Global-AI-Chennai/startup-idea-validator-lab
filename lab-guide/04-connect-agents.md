# Lab 4: Connect Agents as Workflow

> **Duration:** 10 minutes

## 🎯 Objective

Connect the three specialist agents to the Idea Intake Agent (orchestrator) so they work as a unified pipeline.

## 🧠 How It Works

In Microsoft AI Foundry, you can add **other agents as tools** to an orchestrator agent. When the orchestrator decides it needs a specialist's help, it "calls" that agent like a function — sending input and receiving output.

```
┌──────────────────────────────────────────────────────────┐
│              IDEA INTAKE AGENT (Orchestrator)             │
│                                                          │
│  Tools:                                                  │
│  ┌────────────────────┐                                  │
│  │ 🔧 Market Research │ ← Agent as Tool                  │
│  │    Agent           │                                  │
│  └────────────────────┘                                  │
│  ┌────────────────────┐                                  │
│  │ 🔧 Shark Tank      │ ← Agent as Tool                  │
│  │    Simulator Agent │                                  │
│  └────────────────────┘                                  │
│  ┌────────────────────┐                                  │
│  │ 🔧 Pitch Deck      │ ← Agent as Tool                  │
│  │    Generator Agent │                                  │
│  └────────────────────┘                                  │
└──────────────────────────────────────────────────────────┘
```

## 📝 Steps

### Step 1: Open the Orchestrator Agent

1. Go to **Agents** in the left sidebar
2. Click on **"Idea Intake Agent"** to open its configuration

### Step 2: Add Market Research Agent as a Tool

1. Scroll down to the **"Tools"** section in the agent configuration
2. Click **"+ Add tool"**
3. Select **"Agent"** from the tool type options
4. You'll see a list of agents in your project
5. Select **"Market Research Agent"**
6. Click **"Add"**

You should now see "Market Research Agent" listed under Tools.

### Step 3: Add Shark Tank Simulator Agent as a Tool

1. Click **"+ Add tool"** again
2. Select **"Agent"**
3. Select **"Shark Tank Simulator Agent"**
4. Click **"Add"**

### Step 4: Add Pitch Deck Generator Agent as a Tool

1. Click **"+ Add tool"** one more time
2. Select **"Agent"**
3. Select **"Pitch Deck Generator Agent"**
4. Click **"Add"**

### Step 5: Verify Tool Configuration

Your Idea Intake Agent's Tools section should now show:

| Tool Type | Tool Name |
|-----------|-----------|
| 🤖 Agent | Market Research Agent |
| 🤖 Agent | Shark Tank Simulator Agent |
| 🤖 Agent | Pitch Deck Generator Agent |

### Step 6: Save the Configuration

Click **"Save"** to save the orchestrator configuration with all connected tools.

## 🧪 Quick Verification

To verify the connection:
1. The orchestrator should show **3 tools** in its configuration
2. Each tool should be labeled as an "Agent" type
3. The agent names should match exactly

## 💡 Understanding Agent-as-Tool

When the Idea Intake Agent runs, here's what happens behind the scenes:

| Step | What Happens | Tokens Used By |
|------|-------------|---------------|
| 1 | User sends message | Idea Intake Agent |
| 2 | Orchestrator processes and calls Market Research | Market Research Agent |
| 3 | Market Research returns analysis | Idea Intake Agent |
| 4 | Orchestrator calls Shark Tank with combined context | Shark Tank Agent |
| 5 | Shark Tank returns simulation | Idea Intake Agent |
| 6 | Orchestrator calls Pitch Deck with all context | Pitch Deck Agent |
| 7 | Pitch Deck returns outline | Idea Intake Agent |
| 8 | Orchestrator compiles final report | Idea Intake Agent |

> 📊 **Token Note:** A full pipeline run uses tokens across all 4 agents. For a typical idea, expect ~4,000–8,000 total tokens (~$0.01–0.03).

## ❓ Troubleshooting

| Issue | Solution |
|-------|----------|
| Can't see other agents in the tool list | Make sure all agents were created in the **same project** |
| Agent tool not responding | Check that the agent's model deployment is active |
| "Tool call failed" error | Verify the specialist agent works independently first (test it directly) |
| Orchestrator skips an agent | Update the orchestrator's instructions to emphasize "ALWAYS call ALL 3 agents" |

## ✅ Checkpoint

Before testing, verify:
- [ ] Idea Intake Agent has **3 agent tools** configured
- [ ] Tools are: Market Research, Shark Tank, Pitch Deck
- [ ] Configuration is **saved**
- [ ] All model deployments are still in **Succeeded** status

## ➡️ Next Step

Time to test your creation!

**Next: [Lab 5 — Test in Playground](05-test-playground.md)** →
