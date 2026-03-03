# Lab 6: Challenge Exercises

> **Duration:** 15+ minutes (optional, choose what interests you)

## 🎯 Objective

Extend and customize your multi-agent system with these bonus challenges. Each exercise builds on what you've created.

---

## 🏆 Challenge 1: Add a 5th Agent — "Customer Interview Simulator"

**Difficulty:** ⭐⭐ Medium

Create a new agent that simulates interviews with potential customers.

### Instructions to Use

```
You are a customer interview simulator. You role-play as 3 different potential 
customers for the startup idea.

For each customer persona:
- Name, age, occupation, and background (make them diverse)
- Their reaction to hearing about this product (excited / skeptical / confused)
- Would they pay for it? How much?
- What feature would they want most?
- What would make them NOT use it?

End with a "Customer Verdict" summary:
- Enthusiasm Score: X/10
- Willingness to Pay: High / Medium / Low
- Must-Have Feature: [the top requested feature]
```

### Steps
1. Create the agent with the instructions above
2. Add it as a tool to the Idea Intake Agent
3. Update the orchestrator instructions to call it between Market Research and Shark Tank
4. Test it!

---

## 🏆 Challenge 2: Add Knowledge Base to Market Research

**Difficulty:** ⭐ Easy

Give the Market Research Agent real data to work with.

### Steps
1. Create a text file with real startup statistics:
   ```
   - Global startup market size: $4.9 trillion (2025)
   - 90% of startups fail within the first year
   - Top failure reasons: No market need (42%), ran out of cash (29%), wrong team (23%)
   - Average seed round: $1-3 million
   - College-founded startups: 25% of all US startups
   - EdTech market: $340B by 2025
   - FoodTech market: $342B by 2027
   - Average college student spending: $2,150/month
   ```
2. Open Market Research Agent → **Knowledge** → **Upload files**
3. Upload the text file
4. Test again — the agent should now reference real statistics!

---

## 🏆 Challenge 3: Make Shark Tank Investors Regional

**Difficulty:** ⭐⭐ Medium

Customize the Shark Tank agent for your region/country.

### Ideas
- Replace investor personas with local business personalities
- Add regional market context (Indian market, Southeast Asian market, etc.)
- Include local startup ecosystem references (YC India, NASSCOM, local incubators)
- Add questions about local regulations and compliance

### Example for India
Add to the Shark Tank agent instructions:
```
Additional investor: "The Desi Shark" — focused on India-specific market dynamics.
Asks about: UPI integration, tier-2/3 city expansion, Aadhaar compliance, 
local competition from Flipkart/Swiggy/Zerodha ecosystem.
```

---

## 🏆 Challenge 4: Add Function Tool — "Startup Name Generator"

**Difficulty:** ⭐⭐⭐ Hard

Add a custom function tool that generates creative startup names.

### Steps
1. Open the **Pitch Deck Generator Agent**
2. Go to **Tools** → **+ Add tool** → **Function**
3. Define this function schema:

```json
{
  "name": "generate_startup_names",
  "description": "Generates 5 creative startup name suggestions based on the business description",
  "parameters": {
    "type": "object",
    "properties": {
      "business_description": {
        "type": "string",
        "description": "A brief description of what the startup does"
      },
      "style": {
        "type": "string",
        "enum": ["techy", "fun", "professional", "minimal"],
        "description": "The naming style preference"
      }
    },
    "required": ["business_description"]
  }
}
```

4. Update the Pitch Deck instructions to use this function for Slide 1

> 💡 **Note:** The function won't execute real code in the playground, but the agent will simulate calling it, demonstrating how function tools work!

---

## 🏆 Challenge 5: Build a Feedback Loop

**Difficulty:** ⭐⭐⭐ Hard

Make the system iterative — let students refine their idea based on feedback.

### How
1. Update the orchestrator instructions to add:
```
After presenting the final report, ask the student:
"Based on this analysis, would you like to:
1. 🔄 Pivot — Change your target market or business model and re-run
2. 🔧 Refine — Improve a specific aspect (e.g., pricing, features)  
3. ✅ Accept — This looks good, give me final recommendations
4. 🆚 Compare — Test a different idea and compare results"

If they choose Pivot or Refine, re-run the ENTIRE pipeline with the updated idea.
If they choose Compare, save the current results and run a fresh pipeline.
```

2. Test by asking for a pivot after the first run

---

## 🏆 Challenge 6: Create an Industry-Specific Variant

**Difficulty:** ⭐⭐ Medium

Create a copy of the entire pipeline but specialized for a specific industry.

### Suggested Variants

| Variant | Changes |
|---------|---------|
| **SaaS Validator** | Market agent focuses on MRR, churn, LTV/CAC ratios |
| **Social Impact** | Shark Tank becomes "Impact Investors" focused on SDG goals |
| **Hardware/IoT** | Add manufacturing cost analysis, supply chain considerations |
| **Creator Economy** | Focus on creator monetization, audience building, brand deals |

Pick one and modify all 4 agent instructions to match!

---

## 🎯 Bonus: Present Your Work

Create a 5-minute presentation for your class:

1. **Demo** — Show the pipeline processing a live idea
2. **Architecture** — Explain the multi-agent design pattern
3. **Insights** — Share what you learned about agent instructions
4. **Future** — What would you add next?

Great for class presentations, hackathon demos, or portfolio pieces!

## ✅ Checkpoint

Track your challenges:
- [ ] Challenge 1: Customer Interview Agent
- [ ] Challenge 2: Knowledge Base
- [ ] Challenge 3: Regional Investors
- [ ] Challenge 4: Function Tool
- [ ] Challenge 5: Feedback Loop
- [ ] Challenge 6: Industry Variant

## ➡️ Next Step

Don't forget to clean up when you're done!

**Next: [Lab 7 — Cleanup](07-cleanup.md)** →
