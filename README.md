# 🎙️ VoR — Voice of Reddit

> Reddit's collective wisdom, structured. In ~30 seconds.

[![Live Demo](https://img.shields.io/badge/Live_Demo-FF4500?style=for-the-badge&logo=netlify&logoColor=white)](https://voice-of-reddit.netlify.app/)
[![Built With](https://img.shields.io/badge/Built_With-Claude_+_Airia_+_Tavily-0A0A0A?style=for-the-badge)](https://voice-of-reddit.netlify.app/)
[![No Code](https://img.shields.io/badge/No_Code-Required-22c55e?style=for-the-badge)](https://voice-of-reddit.netlify.app/)

VoR is an AI agent that scans Reddit discussions on any topic — a brand, product, city, career decision, or comparison — and returns a structured verdict in about 30 seconds. Grade, top praise, top complaints, honest bottom line.

Built end-to-end in under 2 hours over a weekend. Zero code. $0.

🔗 **Live:** [voice-of-reddit.netlify.app](https://voice-of-reddit.netlify.app/)

---

## 🎯 The Problem

People add "reddit" to every Google search because that's where real, unfiltered opinions live. But Reddit is chaotic — you spend 30 minutes scrolling through 12 threads and 300 comments to get a clear answer.

VoR handles the Reddit-reading for you and hands back a structured report.

---

## ✨ Features

- 🔍 **Universal query handling** — products, brands, cities, software, careers, comparisons
- 📊 **Structured output** — grades, top praise points, top complaints, executive summary
- ⚡ **~30-second response time** — fast enough to feel instant
- 🔗 **Source citations** — links to the actual Reddit threads analyzed
- ⚠️ **Transparency layer** — every response flags Reddit's demographic bias
- 💬 **Two response modes** — short verdict by default, full report on request ("tell me more")
- 🎨 **Custom-designed landing page** — built with editorial typography and bento grid layout

---

## 🏗️ Architecture

```
User Query
    ↓
Airia (orchestration)
    ↓
Claude Haiku 4.5 (reasoning)
    ↓
Tavily via MCP (Reddit retrieval)
    ↓
Claude (synthesis)
    ↓
Structured Report → User
```

**Decoupled by design:**
- The agent logic lives on Airia's platform
- The frontend is a static HTML page on Netlify
- The two communicate via Airia's chat widget API

---

## 🛠️ Stack

| Layer | Tool | Why |
|-------|------|-----|
| Orchestration | [Airia](https://airia.ai) | No-code agent canvas, native MCP support |
| Reasoning | [Claude Haiku 4.5](https://anthropic.com) | Fast, structured output, MCP-compatible |
| Retrieval | [Tavily](https://tavily.com) via MCP | Free tier with 1,000 searches/mo, no card required |
| Frontend | Custom HTML/CSS | Editorial design with Fraunces + Geist + JetBrains Mono |
| Hosting | [Netlify](https://netlify.com) | Free, instant deploy, automatic HTTPS |

**Total cost: $0**
**Total build time: under 2 hours**

---

## 🧠 What is MCP?

**Model Context Protocol** is an open standard (created by Anthropic) that lets LLMs connect to external tools through a unified interface — instead of needing custom API integrations for each tool.

Think of it as USB-C for AI tools. Any MCP-compliant tool plugs into any MCP-compliant AI.

That's why adding Tavily to VoR took 2 clicks instead of 2 hours of custom coding.

---

## 📋 How It Works

### 1. User asks anything
A brand, product, city, career, or comparison. From "Tesla Model Y" to "Seattle vs Chicago" — VoR handles it.

### 2. Agent decides whether to search
The system prompt tells Claude when to invoke Tavily. Definitional questions ("what is NAV?") use Claude's training; live opinion questions trigger a Reddit search.

### 3. Tavily retrieves Reddit data
Targeted queries pull from the most relevant subreddits — `r/SameGrassButGreener` for cities, `r/cars` for vehicles, topic-specific subs otherwise.

### 4. Claude synthesizes
Reads search results, clusters themes, scores sentiment, identifies recurring praise/complaints.

### 5. Structured response is returned
Quick verdict + grade + top 3 praise + top 3 complaints + honest bottom line. With a "tell me more" option to expand into the full Report Card.

---

## 🎨 Sample Output

When a user asks: *"Honda Civic or Honda Accord — which is better?"*

VoR returns:

```
⚔️ VoR Face-Off: Honda Civic vs Honda Accord

Reddit Verdict: Civic for daily driving, Accord for family + comfort.

🏆 Civic Wins On:
- Better MPG and lower running cost
- More fun to drive in city traffic
- Lower upfront cost

🏆 Accord Wins On:
- Roomier interior, better for families
- Quieter ride at highway speeds
- More premium feel inside

Pick Civic if: you commute solo, value efficiency, prefer agility.
Pick Accord if: you have a family, do highway driving, want more space.

Bottom line: Civic for one or two drivers. Accord for three or more.

⚡ VoR reflects Reddit's vibe. Use it as one data point, not the whole story.
```

---

## 🎓 Key Takeaways from Building This

### 1. Prompt engineering determines agent quality far more than model choice.
Small wording changes in the system prompt completely changed agent behavior. Getting the decline rules, output structure, and tone right took ~80% of the iteration time.

### 2. MCP is a quiet revolution in how LLMs connect to tools.
Before MCP: custom API wrappers, authentication handling, response parsing for every integration. After MCP: plug and play. Worth the learning curve.

### 3. Structured output beats conversational chat for business use cases.
Users want reports they can screenshot and share — not transcripts they have to re-read. Designing the agent's responses as Markdown-formatted reports made VoR feel like a real product, not a chatbot.

### 4. Transparent limitations build trust.
The Reddit bias disclaimer was tempting to skip ("won't users trust it less?"). Counterintuitively, including it made VoR feel more credible. Honesty about scope > hiding limitations.

---

## 🚀 What's Next (Future Ideas)

- [ ] Add caching to reduce duplicate Tavily calls
- [ ] Integrate Reddit's official API for richer thread metadata
- [ ] Build a Chrome extension that runs VoR on any product page
- [ ] Add a WhatsApp bot interface
- [ ] Support multi-source aggregation (Reddit + Quora + Glassdoor)

---

## 🧪 Try These Queries

- *"iPhone or Samsung — which one to buy in 2026?"*
- *"Is Dyson actually worth the hype?"*
- *"Which AI coding tool is actually good — Cursor, Copilot, or Claude?"*
- *"Most visited places in Seattle in summer?"*
- *"Underrated neighborhoods in Chicago"*
- *"Best AI bootcamps for analysts"*

---

## 👋 About

Built by **Keerthana Bejgama** — a Business Data Analyst with 5 years of experience in BI, reporting, and turning messy data into clear decisions. VoR reflects how I approach problems at work: break them down, define the output, build, iterate.

🔗 **Connect on LinkedIn:** [linkedin.com/in/keerthana19982509](https://www.linkedin.com/in/keerthana19982509/)
🌐 **Live demo:** [voice-of-reddit.netlify.app](https://voice-of-reddit.netlify.app/)

---

⭐ If this project sparked something for you, a star on the repo means a lot.
