# Lab 7: Cleanup

> **Duration:** 5 minutes

## 🎯 Objective

Delete resources to avoid ongoing charges. Azure AI Foundry resources are billed per-use (tokens), but the underlying Azure resources (AI Services, Storage) may have minor standing charges.

## ⚠️ Important

> **Only clean up if you're completely done with the lab.** If you want to keep experimenting, you can leave resources running — the token-based billing means you only pay when you use the agents.

## 📝 Cleanup Steps

### Option A: Delete Everything (Recommended)

The easiest way — delete the entire resource group, which removes all resources at once.

1. Go to the **[Azure Portal](https://portal.azure.com)**
2. Search for **"Resource groups"** in the top search bar
3. Find and click on **`rg-startup-validator`** (or whatever you named your resource group)
4. Click **"Delete resource group"** at the top
5. Type the resource group name to confirm
6. Click **"Delete"**
7. Wait 2–3 minutes for deletion to complete

### Option B: Delete Only the Agents (Keep Project)

If you want to keep the project for future labs:

1. Go to [ai.azure.com](https://ai.azure.com)
2. Open your project
3. Go to **Agents**
4. For each agent:
   - Click on the agent name
   - Click **"Delete"** (or the trash icon)
   - Confirm deletion
5. Delete all 4 agents:
   - [ ] Idea Intake Agent
   - [ ] Market Research Agent
   - [ ] Shark Tank Simulator Agent
   - [ ] Pitch Deck Generator Agent

### Option C: Delete Model Deployments Only

If you want to stop token billing but keep agents (they won't work without models):

1. Go to **Models + endpoints**
2. For each deployment, click **"..."** → **"Delete deployment"**
3. Delete both:
   - [ ] `gpt-4o`
   - [ ] `gpt-4o-mini`

## 💰 Cost Summary

Here's what the lab likely cost:

| Resource | Estimated Cost |
|----------|---------------|
| Model tokens (all tests) | $0.05 – $0.20 |
| AI Foundry project (standing) | ~$0.00 (free) |
| AI Services resource | ~$0.00 (pay-per-use) |
| Storage (if knowledge used) | < $0.01 |
| **Total** | **< $0.25** |

> 🎓 If you're using Azure for Students ($100 credit), this lab used less than 0.25% of your total credits.

## ✅ Verification

After cleanup:
- [ ] Resource group `rg-startup-validator` no longer appears in Azure Portal (Option A)
- [ ] Or: No agents listed in AI Foundry Agents tab (Option B)
- [ ] Or: No deployments listed in Models + endpoints (Option C)

## 🎉 Congratulations!

You've completed the **Startup Idea Validator Multi-Agent Lab**! 

### What You Built
- ✅ A 4-agent AI pipeline using Azure AI Foundry
- ✅ An orchestrator pattern with agents-as-tools
- ✅ A practical startup validation system

### What You Learned
- ✅ Creating and configuring AI agents
- ✅ Writing effective system prompts / instructions
- ✅ Connecting agents in multi-agent workflows
- ✅ Testing and iterating on AI systems
- ✅ Azure AI Foundry fundamentals

### What's Next?
- 🔗 Try building more multi-agent systems (Pizza Bot, Assignment Helper, etc.)
- 📖 Explore [Azure AI Foundry documentation](https://learn.microsoft.com/azure/ai-foundry/)
- 💻 Try the [SDK approach](https://learn.microsoft.com/azure/ai-foundry/agents/) to build agents with code
- 🚀 Enter a hackathon with your AI agent skills!

---

**Thank you for completing this lab!** ⭐
