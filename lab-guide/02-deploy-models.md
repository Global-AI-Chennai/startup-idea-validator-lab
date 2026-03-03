# Lab 2: Deploy AI Models

> **Duration:** 10 minutes

## 🎯 Objective

Deploy the AI models that will power your agents. We'll deploy two models:

| Model | Used By | Why |
|-------|---------|-----|
| **GPT-4o** | Idea Intake, Market Research, Shark Tank agents | Best reasoning for complex analysis |
| **GPT-4o-mini** | Pitch Deck Generator agent | Cost-effective for structured content generation |

## 📝 Steps

### Step 1: Navigate to Models + Endpoints

1. In your AI Foundry project, click **"Models + endpoints"** in the left sidebar
2. Click **"+ Deploy model"**
3. Select **"Deploy base model"**

### Step 2: Deploy GPT-4o

1. In the model catalog, search for **"gpt-4o"**
2. Select **gpt-4o** from the results
3. Click **"Confirm"**
4. Configure the deployment:

   | Field | Value |
   |-------|-------|
   | **Deployment name** | `gpt-4o` |
   | **Model version** | Latest available (auto-selected) |
   | **Deployment type** | Global Standard (recommended) |
   | **Tokens per minute rate limit** | `30K` (or higher if available) |

5. Click **"Deploy"**
6. Wait for the deployment status to show **Succeeded** ✅

### Step 3: Deploy GPT-4o-mini

1. Go back to **Models + endpoints** → **"+ Deploy model"** → **"Deploy base model"**
2. Search for **"gpt-4o-mini"**
3. Select **gpt-4o-mini** and click **"Confirm"**
4. Configure:

   | Field | Value |
   |-------|-------|
   | **Deployment name** | `gpt-4o-mini` |
   | **Model version** | Latest available |
   | **Deployment type** | Global Standard |
   | **Tokens per minute rate limit** | `30K` |

5. Click **"Deploy"**
6. Wait for **Succeeded** status ✅

### Step 4: Verify Deployments

Go to **Models + endpoints** and confirm you see both deployments:

| Deployment Name | Model | Status |
|----------------|-------|--------|
| `gpt-4o` | gpt-4o | ✅ Succeeded |
| `gpt-4o-mini` | gpt-4o-mini | ✅ Succeeded |

## 💡 Understanding Model Choices

### Why Two Models?

| Aspect | GPT-4o | GPT-4o-mini |
|--------|--------|-------------|
| **Reasoning** | Excellent — complex analysis | Good — structured tasks |
| **Speed** | Fast | Faster |
| **Cost** | ~$2.50/1M input tokens | ~$0.15/1M input tokens |
| **Best for** | Market analysis, investor simulation | Content generation, formatting |

Using GPT-4o-mini for simpler tasks saves **94% on cost** compared to using GPT-4o for everything!

### Tokens Per Minute (TPM)

- **30K TPM** is sufficient for this lab
- Connected agents consume tokens in sequence (Orchestrator → Agent 1 → Agent 2 → ...)
- If you experience rate limiting, increase TPM in the deployment settings

## ❓ Troubleshooting

| Issue | Solution |
|-------|----------|
| "Model not available in this region" | Switch to East US or Sweden Central (requires new hub) |
| "Insufficient quota" | Request quota increase in Azure Portal → Subscriptions → Usage + quotas |
| Deployment stuck in "Deploying" | Wait 5 minutes; if still stuck, delete and redeploy |
| "Authorization failed" | Ensure you have Contributor or Cognitive Services Contributor role |

## 💰 Cost Note

> **Relax!** For this lab, you'll use approximately:
> - ~$0.05–$0.15 in total tokens
> - Well within the $100 Azure for Students credits
> - Models only cost money **when you use them** (per-token billing)

## ✅ Checkpoint

Before moving on, confirm:
- [ ] `gpt-4o` deployment shows **Succeeded**
- [ ] `gpt-4o-mini` deployment shows **Succeeded**
- [ ] Both appear in your Models + endpoints list

## ➡️ Next Step

Now let's build the agents!

**Next: [Lab 3 — Create the Agents](03-create-agents.md)** →
