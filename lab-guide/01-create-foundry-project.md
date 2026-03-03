# Lab 1: Create AI Foundry Project

> **Duration:** 10 minutes

## 🎯 Objective

Create an Azure AI Foundry project that will host your agents and model deployments.

## 📝 Steps

### Step 1: Navigate to Azure AI Foundry

1. Open your browser and go to **[https://ai.azure.com](https://ai.azure.com)**
2. Sign in with your Azure account
3. You'll land on the AI Foundry **Home** page

### Step 2: Create a New Project

1. Click **"+ Create project"** (top-left area or center of the page)

2. Fill in the **Project details**:

   | Field | Value | Notes |
   |-------|-------|-------|
   | **Project name** | `startup-validator-lab` | Use lowercase, hyphens OK |
   | **Hub** | Create new or select existing | See Step 3 if creating new |

3. Click **Next** to configure the hub (if creating new)

### Step 3: Create a Hub (if needed)

If you don't have an existing hub, you'll need to create one:

| Field | Value | Notes |
|-------|-------|-------|
| **Hub name** | `ai-foundry-hub-lab` | Any descriptive name |
| **Subscription** | Select your Azure subscription | |
| **Resource group** | **Create new** → `rg-startup-validator` | Keeps resources organized |
| **Region** | `East US` or `Sweden Central` | Must support GPT-4o |

> ⚠️ **Important:** Choose a region that supports GPT-4o and GPT-4o-mini. See [Lab 0](00-prerequisites.md) for the list.

### Step 4: Review and Create

1. Review your settings:
   - Project name: `startup-validator-lab`
   - Region: Your chosen region
   - Resource group: `rg-startup-validator`

2. Click **"Create"**

3. **Wait 2–3 minutes** for provisioning to complete

4. You'll be redirected to your new project dashboard

### Step 5: Verify the Project

Once created, you should see:

- ✅ Project name in the top-left breadcrumb
- ✅ Left sidebar with options: Overview, Models + endpoints, Agents, etc.
- ✅ A project endpoint URL (you'll need this later)

> 📝 **Note your project endpoint** — it looks like:
> `https://<your-resource>.services.ai.azure.com/api/projects/<project-name>`

## 🖼️ What Your Screen Should Look Like

After creation, your AI Foundry project dashboard shows:
- **Overview** — Project details and getting started links
- **Models + endpoints** — Where you'll deploy models (Lab 2)
- **Agents** — Where you'll build agents (Lab 3)
- **Playground** — For testing models directly

## ❓ Troubleshooting

| Issue | Solution |
|-------|----------|
| "Create project" button is grayed out | Ensure your subscription is active and you have Contributor role |
| Region not available | Try East US, East US 2, or Sweden Central |
| Provisioning fails | Check if you have quota in the selected region |
| Can't see the Agents tab | Ensure your project was created successfully; try refreshing |

## ✅ Checkpoint

Before moving on, confirm:
- [ ] Project `startup-validator-lab` is created
- [ ] You can see the project dashboard
- [ ] The **Agents** option is visible in the left sidebar
- [ ] The **Models + endpoints** option is visible

## ➡️ Next Step

**Next: [Lab 2 — Deploy AI Models](02-deploy-models.md)** →
