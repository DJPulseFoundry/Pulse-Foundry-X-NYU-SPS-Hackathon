# NYU SPS X Pulse Foundry Hackathon

**Build an AI growth agent that helps a real restaurant get recommended by AI assistants.**

A one-day hackathon hosted by NYU SPS and [Pulse Foundry](#about-pulse-foundry). About 100 NYU graduate students, working in roughly 20 teams, each build a working solution to a real-world challenge and present it to a panel of judges.

| | |
|---|---|
| **Date** | Friday, October 23, 2026 |
| **Time** | 9:00 AM – 7:00 PM |
| **Location** | NYU SPS MTC, Rooms 1026 & 1027 |
| **Contact** | See [Questions](#questions) |

---

## The Challenge: AI Search Optimization (AISO)

Search is changing. Instead of typing "best Italian restaurant NYU" into Google and scrolling through ten blue links, people now ask ChatGPT, Gemini, Perplexity, and Claude directly, and they expect a confident, specific answer.

That shift creates a new, mostly invisible battlefield: **AI Search Optimization (AISO)**. Traditional SEO tells you how to rank on Google. Almost nothing tells a small business how to get recommended when an AI assistant is asked, "Where should I eat?"

**Your challenge is to build an agent that helps a real restaurant win that battle.**

### Problem Statement

Given a restaurant's name, website, or location, build an agent that can answer five questions for the owner:

1. Where do I currently rank in AI search?
2. Why are competitors beating me?
3. What should I change?
4. Can the agent make those changes for me?
5. Did my visibility improve?

These map to a four-stage loop:

```
Discovery → Analysis → Action → Measurement
    ↑                                  │
    └──────────────────────────────────┘
```

---

## What You'll Build

### 1. Discovery: Simulate the customer

- Generate a realistic bank of queries a customer might actually ask an AI assistant, such as "best Greek food in Pacific Beach," "quiet date-night spot in San Diego," or "happy hour with small plates near the beach." Vary intent, distance, price, cuisine, and occasion.
- Run these queries against one or more AI platforms, either via API where available (Claude, GPT, Gemini) or via structured prompting that simulates how a retrieval-augmented assistant would answer.
- For every query, log whether the target restaurant was mentioned, at what position, and which competitors appeared and how often.

### 2. Analysis: Explain the gap

- Build a **visibility scorecard** for the restaurant across the query set: mention rate, average rank, and competitor share-of-voice.
- Analyze the inputs AI models likely draw on: the restaurant's own website copy, structured data (schema.org / JSON-LD), Google Business Profile, Yelp and TripAdvisor listings, press coverage, blog mentions, and Reddit or forum discussion.
- Diagnose why competitors win. Examples include richer menu descriptions, more third-party reviews, dedicated blog content answering "best of" questions, structured FAQ data, and more recent press mentions.
- Surface concrete, prioritized gaps, not just a single "AI SEO score."

### 3. Action: Close the gap

- Generate AI-search-friendly content: optimized "About" copy, menu descriptions, FAQ pages, schema markup (`Restaurant`, `Menu`, `FAQPage`, `Review`), and locally relevant landing content (for example, "Best Mediterranean food in Pacific Beach" written to plausibly earn a citation).
- **Bonus:** don't just recommend, act. For example, draft and (with permission) publish updated website copy, submit or update structured data, draft outreach emails to local blogs or press, or auto-generate content ready to paste into a CMS.

### 4. Measurement: Prove it worked

- Re-run the same query bank on a schedule (daily or weekly) and track mention rate and rank over time.
- Present before/after visibility trends so the restaurant can see impact, not just effort.

---

## Target Restaurant: Café Athena

Build and demo your agent against a real restaurant: **[Café Athena](https://cafeathena.com/)**. The winning team will get to test its solution with Café Athena after the hackathon.

| | |
|---|---|
| **Website** | [cafeathena.com](https://cafeathena.com/) |
| **Cuisine** | Greek and Mediterranean restaurant and bar |
| **Location** | 1846 Garnet Ave, San Diego, CA 92109 (Pacific Beach) |
| **Open since** | 1990 |
| **Hours** | Sun–Thu 11:00 AM – 9:00 PM; Fri–Sat 11:00 AM – 9:30 PM |
| **Highlights** | Daily happy hour (3–6 PM) with tapas-style small plates; vegan, vegetarian, and gluten-free options; full bar with Greek-mythology-themed cocktails; catering, group dining, and private events |

Café Athena is in San Diego, so your query bank should reflect how people there search, not how NYU students search. Example queries to start from:

- "best Greek food in Pacific Beach"
- "Mediterranean restaurant with gluten-free options in San Diego"
- "happy hour with good food near Garnet Ave"
- "where to host a rehearsal dinner in Pacific Beach"
- "date night spot in PB with good cocktails"

---

## Technical Building Blocks

These are suggestions, not requirements.

| Layer | Ideas |
|---|---|
| Query generation | LLM-generated query variants across intent, cuisine, occasion, and location; can be templated and expanded |
| AI platform testing | Claude, GPT, and Gemini APIs; Perplexity API; where no API exists, simulate via RAG-style prompting with real web context |
| Web & data analysis | Website scraping, schema.org/JSON-LD parsing, Google Business Profile and Yelp data, Reddit/forum search, press mention search |
| Competitive diagnostics | Structured comparison of the target vs. top-appearing competitors across content, reviews, structured data, and mentions |
| Content generation | LLM-generated FAQ, menu copy, schema markup, and locally relevant blog content |
| Action layer (bonus) | CMS/webhook integration, auto-generated PRs to a website repo, email drafts, scheduled re-testing |
| Measurement | Time-series tracking of mention rate and rank per query bank; simple dashboard |

---

## Deliverables

- [ ] **Working demo** using [Café Athena](#target-restaurant-café-athena) as the target restaurant.
- [ ] **Visibility report** showing current AI-search performance vs. named competitors, with specific reasons for the gap.
- [ ] **Generated artifacts** the restaurant could actually use, such as website copy, FAQ content, and structured data snippets.
- [ ] **Measurement mechanism.** Even a simple "re-run this and compare" loop counts.
- [ ] **(Bonus)** Evidence of the agent taking a real action autonomously (publishing content, submitting data, sending outreach, etc.), with human-in-the-loop confirmation where appropriate.

---

## How to Submit

Projects are submitted on Pulse, not DevPost.

1. Go to the [hackathon page on Pulse](https://pulsefoundry.ai/hackathons/6ada7c5ed712f06a00f14548).
2. Log in with the email address you used to register for this hackathon.
3. Check that inbox for a one-time passcode, and enter it to finish logging in.
4. Fill in your project details and submit.

---

## Judging Criteria

| Criterion | What judges are looking for |
|---|---|
| Discovery depth | Realistic, varied query simulation across real AI platforms |
| Analytical rigor | Clear, evidence-based explanation of why competitors win, not just a score |
| Actionability | Specific, usable recommendations and generated content |
| Autonomy (bonus) | Agent takes real action, not just advice |
| Measurability | A credible way to track improvement over time |
| Polish & demo quality | Can you show a judge, in 3 minutes, "here's what's broken, here's what we fixed, here's proof it worked"? |

---

## Constraints & Notes for Teams

- You don't need access to every AI platform's API. Build for the ones you can reach, and clearly explain how the approach generalizes to others.
- Be thoughtful about scraping etiquette and rate limits when pulling review and listing data.
- If your agent takes autonomous actions (publishing, emailing), build in a clear human-approval step for the demo. Reversible, transparent actions win more trust than a black box.
- A great submission tells a **before → diagnosis → fix → after** story, not just a technical pipeline.

Think of what you're building as an AI growth agent for the new era of search: not a report generator, but a system that keeps working for the restaurant after the hackathon ends.

---

## About Pulse Foundry

Pulse Foundry is an AI consultancy, incubation lab, and builder community based in New York City.

- **Consulting:** Pulse Foundry embeds small teams of engineers, data scientists, and solution architects in mid-market companies and helps them ship AI systems that run in production, including automations, internal tools, pricing and search work, and more.
- **Lab:** Pulse Foundry takes promising ideas and early teams and helps turn them into real products.
- **Community:** The community grew out of meeting sharp people who wanted somewhere to build and compare notes. It's now one of the city's larger technical communities, running hackathons, talks, demos, and working sessions.

Strong work at Pulse Foundry events has led to roles, contract opportunities, and professional introductions.

---

## Questions

Dr. Steven Goss led an information session covering the program, application process, and event expectations; the Zoom recording is available through the official hackathon announcement. For other questions, reach out to any of the contacts below.

| Name | Organization | Email |
|---|---|---|
| Dr. Steven Goss | NYU SPS | [swg3@nyu.edu](mailto:swg3@nyu.edu) |
| Mitchell Itkin | Pulse Foundry | [mitchell@pulsefoundry.ai](mailto:mitchell@pulsefoundry.ai) |
| Mark Bakshiyev | Pulse Foundry | [mark@pulsefoundry.ai](mailto:mark@pulsefoundry.ai) |
| DJ Lee | Pulse Foundry | [dj@pulsefoundry.ai](mailto:dj@pulsefoundry.ai) |
