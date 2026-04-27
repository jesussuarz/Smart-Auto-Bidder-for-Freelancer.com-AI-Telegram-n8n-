# Smart Auto Bidder for Freelancer.com AI + Telegram + n8n
Smart Auto-Bidder for Freelancer.com (AI + Telegram Approval + n8n)

![Image Description](https://github.com/jesussuarz/Smart-Auto-Bidder-for-Freelancer.com-AI-Telegram-n8n-/blob/93f297d5a9969ba4a79d730fcaa6c6d97e93bcf6/image.png)

Fully automate your Freelancer.com bidding process using **n8n + AI + Telegram**.

This workflow finds projects, generates smart proposals with AI, and lets you approve bids in real
time via Telegram.

Ideal for technical freelancers (DevOps, SysAdmin, Backend, Infrastructure) who want to scale
without losing control.

✨ **Features**

- 🔍 **Smart Project Search (DevOps & SysAdmin Focus)**
    Automatically searches for relevant projects using advanced queries like:
    linux, devops, docker, kubernetes, nginx, etc.
- 🚫 **Anti-Duplicate Bidding**
    Detects if you’ve already applied to a project and skips it.
- 🤖 **AI Proposal Generator (Context-Aware)**
    Generates professional, customized proposals aligned with your real skillset.
- 📬 **Telegram Approval System**
    Receive each project in Telegram with options to:

```
✅Approve (send bid)
```
```
❌Cancel
```
- ⚡ **1 - Click Auto Bid Submission**
    Once approved → the system submits the bid automatically.
- 🔁**Manual or Scheduled Mode**
    Run it manually or every X hours.

⚙️ **Initial Setup (IMPORTANT)**

**1. Edit the Edit Fields1 node**

This node defines **what projects to search + where to send notifications**.

Example:
```json
{
"query": "linux OR ubuntu OR debian OR sysadmin OR devops OR nginx OR apache OR docker OR
kubernetes OR bash",
"ChatId": 1874265481,
"jobs_limit": 100
}
```

🔹 **Fields:**

- query → Search keywords (customize based on your niche)
- ChatId → Your Telegram chat ID
- jobs_limit → Number of projects per execution

📌 This value is used directly in the Search node of the workflow.

🤖 **Quick Guide: Create Your Telegram Bot**

1. Open Telegram and search for: **@BotFather**
2. Run:
```json
/start
/newbot
```

3. Set:
- Bot name
- Username (example: my_auto_bid_bot)
4. Copy the generated **Bot Token**

🔑 **Get Your Chat ID**

1. Send any message to your bot
2. Open in your browser:
```bash
https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates
```
3. Look for:
```json
"chat": {
"id": 1874265481
}
```
That number is your ChatId

🔐 **Requirements**

- Freelancer API Token
```bash
freelancer-oauth-v1: <oauth_access_token>
```
- Telegram Bot Token
- OpenAI API Key

🧠 **How the Workflow Works**

1.	🔁 Trigger (manual or scheduled) 
2.	🔍 Search projects using your query 
3.	🔄 Iterate through each project 
4.	🚫 Check if already bid 
5.	🤖 Generate AI proposal 
6.	📬 Send summary + proposal to Telegram 
7.	👉 You decide: 

```bash
✅Approve → bid is submitted
```
```
❌Cancel → skipped
```

🧩 **Included Workflows**

- freelancerMain → Entry point (query + config)
- freelancerAgent → Full logic (search + AI + Telegram + bidding)

📎 **Use Cases**

- DevOps / SysAdmin freelancers automating lead generation
- Agencies managing multiple client profiles
- AI-powered sales automation workflows

🧠 **Customize Proposal Style Based on Your Skills**

Edit the **AI Agent / AI Agent 2** node to control how the AI generates proposals based on your core
skills.

Inside the agent prompt, you can define:

- Your areas of expertise
- Proposal tone (technical, consultative, direct, etc.)
- Language behavior
- Type of solutions you typically offer
- Technologies you want to highlight
- Skills or services you want to exclude

Example:

You are an experienced freelancer specialized in Linux, DevOps, Docker, Kubernetes, Nginx,
Apache, Bash automation, cybersecurity and server troubleshooting.

- Generate proposals focused only on projects related to these skills.
- Do not invent experience.
- Keep the proposal professional, direct and customized to the project.

📌 **The more precise your skill definition, the better and more relevant the generated proposals will be.**

🌐 **Optional Spanish Translation**

This workflow includes an additional translation agent: **AI Agent 3 / Translate Spanish**.

You can connect it if you want to receive proposals translated into Spanish before approving them
via Telegram.

**When to use it**
- If you prefer reviewing proposals in Spanish
- If you work with bilingual clients
- If you want an extra validation step before sending

**How to enable it**
Connect the output of the main AI agent to the translation agent, then to the Telegram approval
node.

**Suggested flow:** 
AI Agent → AI Agent 3 / Translate Spanish → Telegram Approval

If you prefer to send proposals in the original project language, simply leave the translation agent
disconnected.

💡 **PRO Tips**

- Adjust the query to match your niche (WordPress, AI, Shopify, etc.)
- Modify the AI prompt to change proposal style
- Add scoring logic (budget, bids, etc.) to filter better opportunities

🔄 **Based on an Existing Workflow (Improved Version)**

👉 This workflow is based on the original template: https://n8n.io/workflows/6048-freelancer-auto-bid-bot-ai-proposals-with-telegram-approval/

However, this version is not just a copy — it has been significantly improved, extended, and production-ready.

🚀 **What’s Improved in This Version**

While the core architecture remains similar, this version includes multiple enhancements that are not included in the original paid template ($25):

🧠 **Smarter AI Proposal Control**
- Fully customizable AI prompts based on your real skillset
- Better alignment with technical niches (DevOps, SysAdmin, etc.)
- More precise and consistent proposal generation

✅ **Enhanced Telegram Approval Flow**
- Improved approval logic
- Cleaner interaction before sending bids
- Better control over what gets submitted

🌐 **Built-in Translation Layer (Optional)**
- Integrated translation agent (Spanish ↔ English)
- Review proposals in your preferred language before sending
- Not available in the original workflow

⚙️ **Simplified Configuration**
- Centralized config via Edit Fields1
- Easy control of:
- Search queries
- Chat ID
- Project limits

📘 **Real Setup Documentation (Missing in Original)**
- Step-by-step Telegram bot setup guide
- Chat ID extraction explained
- Practical configuration examples

💡 **Why This Version?**

The original workflow is a solid base, but:
- ❌ Lacks proper setup guidance
- ❌ Limited AI customization
- ❌ No translation support
- ❌ Minimal control over proposal behavior

This version solves all of that and makes it:
- 👉 Easier to use
- 👉 More flexible
- 👉 More powerful in real-world usage
