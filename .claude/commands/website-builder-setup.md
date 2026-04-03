---
name: website-builder-setup
description: "Install the full AI website builder stack — UI/UX Pro Max, Framer Motion animations, and 21st.dev components. One skill, three tools, zero coding experience needed."
---

# Website Builder Setup

This skill walks you through installing everything you need to build professional, animated websites with Claude Code. No coding experience required.

## What Gets Installed

| Tool | What it does |
|------|-------------|
| **UI/UX Pro Max** | Gives Claude access to 50+ design styles, 161 color palettes, 57 font pairings. Your sites look designed, not generated. |
| **Framer Motion** | Adds smooth animations — page transitions, hover effects, scroll reveals. Makes sites feel alive. |
| **21st.dev Magic** | A library of 100+ polished React components Claude can pull from. Production-quality building blocks. |

## Workflow

When this skill is triggered, walk the user through each step one at a time. Be encouraging and clear — assume they have zero coding experience. If any step fails, don't stop. Acknowledge it, give them the manual command, and keep moving.

---

### Step 1: Check Prerequisites

> Before we start, let me make sure you have what we need.

Run this silently:
```bash
node --version 2>&1 && npm --version 2>&1
```

- If Node.js is installed → say "You're good — Node.js is installed. Let's go."
- If NOT installed → say:

> You need Node.js first. Go to https://nodejs.org and download the LTS version. Install it, restart your terminal, then come back and run `/website-builder-setup` again. Takes 2 minutes.

Stop here if Node is missing.

---

### Step 2: Install UI/UX Pro Max

> **Step 1 of 3: UI/UX Pro Max**
>
> This gives me access to 50+ design styles, 161 color palettes, and 57 font pairings. Your sites will actually look designed.

Run:
```bash
npm install -g uipro-cli 2>&1
```

Then:
```bash
uipro init --ai claude 2>&1
```

- If both succeed → say "UI/UX Pro Max is installed. Your sites just got a serious upgrade."
- If either fails → say "Ran into a snag. Try running this manually: `npm install -g uipro-cli && uipro init --ai claude`. Then let me know when it's done."

Move to Step 3 regardless.

---

### Step 3: Install Framer Motion Skill

> **Step 2 of 3: Framer Motion**
>
> This adds smooth animations to everything — page transitions, hover effects, scroll reveals. Makes sites feel alive instead of static.

Run:
```bash
npm install framer-motion 2>&1
```

- If success → say "Framer Motion installed. Your sites are about to move."
- If fails → say "No worries. Run this manually: `npm install framer-motion`. Come back when it's done."

Move to Step 4 regardless.

---

### Step 4: Set Up 21st.dev Magic

> **Step 3 of 3: 21st.dev Magic**
>
> This connects you to 100+ production-ready React components — buttons, navbars, hero sections, cards, footers. All polished, all ready to use.

Say:

> You'll need a free API key from 21st.dev. Go to https://21st.dev, create a free account, and grab your API key. Paste it here when you have it.

Wait for the user to provide their API key. When they do:

```bash
npx @21st-dev/magic@latest init 2>&1
```

When prompted for the API key during init, use the key they provided.

- If success → say "21st.dev Magic is connected. You've got a whole component library at your fingertips."
- If fails → say "Ran into an issue. Try: `npx @21st-dev/magic@latest init` and enter your API key when prompted."

---

### Step 5: Done

> You're all set. Here's what's now installed:
>
> - **UI/UX Pro Max** — 50+ styles, 161 palettes, 57 font pairings
> - **Framer Motion** — Smooth animations throughout
> - **21st.dev Magic** — 100+ polished components
>
> Now let's build something. Describe what you want and I'll handle the design, layout, animations, and everything else.
>
> Try something like: *"Build me a landing page for my consulting business targeting small business owners."*

---

## Rules

- Walk through each step ONE AT A TIME
- Never dump all instructions at once
- If any install fails, don't stop — acknowledge, give manual command, keep moving
- Be encouraging and casual throughout
- Assume zero coding experience
- After everything is installed, prompt them to build their first site
