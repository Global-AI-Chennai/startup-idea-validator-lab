# Lab 5: Test in Playground

> **Duration:** 15 minutes

## 🎯 Objective

Test your multi-agent startup validator pipeline with real startup ideas and observe how the agents collaborate.

## 📝 Steps

### Step 1: Open the Agent Playground

1. Go to **Agents** in the left sidebar
2. Click on **"Idea Intake Agent"** (the orchestrator)
3. The **chat playground** panel should appear on the right side
4. If not visible, click the **"Test in playground"** or **chat icon** button

### Step 2: Run Your First Test

Type (or copy-paste) this startup idea into the chat:

```
I want to build an app where college students can share their leftover meal plan 
swipes with students who can't afford food. Think of it like Uber, but for 
unused meal swipes.
```

Press **Enter/Send** and watch the magic happen! 🎬

### Step 3: Observe the Pipeline

As the orchestrator processes your request, watch for these stages:

| Stage | What You'll See | Approx. Time |
|-------|----------------|--------------|
| 1. Idea Intake | Orchestrator structures your idea | ~5 seconds |
| 2. Market Research | Calling Market Research Agent... | ~10 seconds |
| 3. Shark Tank | Calling Shark Tank Simulator Agent... | ~15 seconds |
| 4. Pitch Deck | Calling Pitch Deck Generator Agent... | ~10 seconds |
| 5. Final Report | Compiled validation report | ~5 seconds |

> 💡 **Look for the tool calls!** In the playground, you should see indicators showing when the orchestrator calls each specialist agent. You might see expandable sections showing the agent-to-agent communication.

### Step 4: Review the Output

Your output should include all of these sections:

- [ ] **Structured idea summary** (Problem, Solution, Target Market, Revenue Model)
- [ ] **Market analysis** with TAM/SAM/SOM and competitor analysis
- [ ] **Shark Tank simulation** with 3 investors and their verdicts
- [ ] **10-slide pitch deck** outline
- [ ] **Final validation report** with action items

### Step 5: Run More Test Scenarios

Try these additional ideas to see how the agents handle different types of startups:

---

#### 🧪 Test 2: Tech Startup
```
An AI-powered study buddy app that reads your class notes and generates 
practice questions, flashcards, and mini-quizzes. It learns what you're 
weak at and focuses on those topics.
```

---

#### 🧪 Test 3: Social Good Startup
```
A platform where students can rent textbooks from each other instead of 
buying them new. Like a peer-to-peer library for college textbooks with 
built-in payments and review system.
```

---

#### 🧪 Test 4: Fun / Lifestyle Startup
```
A food truck tracking app for college towns. Students get real-time 
locations of food trucks near campus, see menus, wait times, and can 
pre-order pickup. Food trucks get a free marketing channel.
```

---

#### 🧪 Test 5: Vague Idea (Tests Clarification)
```
I want to do something with AI and fitness
```

> 💡 For Test 5, the orchestrator should **ask clarifying questions** before starting the pipeline. This tests the intake quality!

## 🔍 What to Look For

### Signs of a Well-Working Pipeline ✅

| Signal | What It Means |
|--------|--------------|
| Orchestrator asks questions for vague ideas | Intake instructions working |
| Market research uses TAM/SAM/SOM | Market agent following format |
| 3 distinct investor personalities | Shark Tank agent is role-playing correctly |
| Pitch deck has exactly 10 slides | Pitch agent following structure |
| Final report has action items | Orchestrator compiling correctly |
| Each section has unique content | Agents not just copying each other |

### Common Issues and Fixes 🔧

| Issue | Cause | Fix |
|-------|-------|-----|
| Orchestrator doesn't call agents | Instructions unclear | Add "You MUST call all 3 agents" to instructions |
| Only 1 or 2 agents called | Agent skipping | Add "NEVER skip any agent" to orchestrator instructions |
| Agents repeat each other's content | Too much context bleed | Make each agent's instructions more specific about its unique role |
| Output is too long | No length constraints | Add "Keep your output under 500 words" to agent instructions |
| Output is too short | Model being lazy | Add "Be thorough and detailed" to agent instructions |
| Shark Tank feels generic | Need more personality | Make investor characters more distinct in instructions |

## 🎮 Interactive Experiment

Try modifying the conversation **mid-flow**:

1. After getting the full report, ask: *"What if I pivoted to target high school students instead?"*
2. See if the orchestrator re-runs the pipeline with the new angle
3. Ask: *"Can you make the Shark Tank investors tougher?"*
4. This tests conversational flexibility

## 📊 Compare Results

If you ran multiple test scenarios, compare:

| Metric | Test 1 (Meals) | Test 2 (AI Study) | Test 3 (Textbooks) | Test 4 (Food Trucks) |
|--------|----------------|--------------------|--------------------|---------------------|
| Market Rating | ? | ? | ? | ? |
| Investors In | ?/3 | ?/3 | ?/3 | ?/3 |
| Strongest Slide | ? | ? | ? | ? |
| Top Risk | ? | ? | ? | ? |

Fill this in as you test — it's a great way to see how the agents evaluate different ideas!

## ✅ Checkpoint

Before moving on, confirm:
- [ ] Successfully ran at least **2 test scenarios**
- [ ] Output includes all 4 sections (Intake, Market, Shark Tank, Pitch Deck)
- [ ] Agents are communicating (not just the orchestrator answering alone)
- [ ] Final report includes action items
- [ ] Vague ideas trigger clarification questions

## ➡️ Next Step

Ready for some challenges? Let's customize and extend your agents!

**Next: [Lab 6 — Challenge Exercises](06-challenge-exercises.md)** →
