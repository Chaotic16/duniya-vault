---
{"dg-publish":true,"permalink":"/publishing-my-digital-garden/","dgShowInlineTitle":true,"created":"2026-03-22T17:22:31.852+05:30","updated":"2026-03-24T19:42:02.713+05:30","dg-note-properties":{"draft":true}}
---

Great — this is a solid long-term setup, and doing it via **Quartz + GitHub Pages** is exactly the right call for a proper digital garden.

I’ll walk you through this like a clean system build — no assumptions, no fluff.

---

# 🧠 What You’re Building (Mental Model)

You will have:

- **Obsidian vault** → where you write notes
    
- **Quartz (v4)** → converts notes → website
    
- **GitHub repo** → hosts your site
    
- **GitHub Pages** → makes it live on the internet
    

Flow:

```
Obsidian → Quartz build → GitHub → Live Website
```

---

# ⚙️ STEP 0 — Install Required Tools

You need 3 things:

### 1. Install Git

- Download: [https://git-scm.com](https://git-scm.com/)
    
- Install with default settings
    

### 2. Install Node.js (VERY IMPORTANT)

- Download LTS version: [https://nodejs.org](https://nodejs.org/)
    
- This powers Quartz
    

### 3. GitHub Account

- Create if you don’t have one
    

---

# 📁 STEP 1 — Prepare Your Obsidian Vault

Inside your vault:

**Recommended structure**

```
/content
  notes.md
  ideas.md
```

Later Quartz will read from `/content`

👉 If your vault is already messy → we can restructure later, don’t worry.

---

# 🚀 STEP 2 — Install Quartz

Open **Command Prompt (CMD)** and run:

```bash
git clone https://github.com/jackyzha0/quartz.git my-garden
cd my-garden
npm install
```

Now you have a Quartz project.

---

# 🔗 STEP 3 — Connect Quartz to Your Obsidian Vault

Inside `my-garden` folder:

Find:

```
/content
```

👉 Replace it with your Obsidian notes:

### Option A (BEST)

Move your vault inside Quartz:

```
my-garden/content = your vault notes
```

### Option B

Keep vault separate → sync via copy (less ideal)

---

# ▶️ STEP 4 — Test Locally

Run:

```bash
npx quartz build --serve
```

Open browser:

```
http://localhost:8080
```

👉 You should see your notes as a website.

---

# 🎨 STEP 5 — Customize (Important Early Step)

Edit:

```
quartz.config.ts
```

Change:

```ts
title: "Your Digital Garden",
baseUrl: "yourusername.github.io",
```

You can also:

- Enable graph view
    
- Change theme
    
- Add backlinks
    

---

# ☁️ STEP 6 — Push to GitHub

### Create repo:

Go to GitHub → New repo:

```
yourusername.github.io
```

Then in CMD:

```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/yourusername/yourusername.github.io.git
git push -u origin main
```

---

# 🌍 STEP 7 — Enable GitHub Pages

Go to repo → Settings → Pages

Set:

```
Source → GitHub Actions
```

Quartz already includes deployment workflow.

---

# ⚡ STEP 8 — Deploy

Run:

```bash
npx quartz build
```

Push changes:

```bash
git add .
git commit -m "deploy"
git push
```

👉 After ~1–2 minutes your site will be live at:

```
https://yourusername.github.io
```

---

# 🔁 STEP 9 — Your Daily Workflow

Whenever you write notes:

```bash
npx quartz build
git add .
git commit -m "update notes"
git push
```

---

# 🧠 IMPORTANT BEST PRACTICES (From Experience)

### 1. Use Obsidian links heavily

```
[[note name]]
```

Quartz thrives on this.

---

### 2. Keep notes atomic

One idea = one note

---

### 3. Avoid folders initially

Use links instead → better graph

---

### 4. Use frontmatter (later upgrade)

```yaml
---
title: My Note
tags: [idea, learning]
---
```

---

# ⚠️ Common Problems (You WILL face these)

### ❌ "npm not recognized"

→ Node not installed properly

### ❌ Blank site

→ content folder empty or wrong path

### ❌ Git push error

→ auth issue → use GitHub token instead of password

---

# 🧭 Where This Can Go Next

Once this is working, we can upgrade:

- Auto-deploy on note save
    
- Custom domain
    
- Search bar improvements
    
- Tag pages
    
- RSS feed
    
- Analytics
    

---

# 👍 What I Need From You Next

Tell me:

1. Do you already have an Obsidian vault with notes?
    
2. Or are we starting from scratch?
    
3. Are you comfortable using CMD or want GUI-based Git help?
    

Based on that, I’ll refine this into a **clean, minimal, no-friction workflow tailored for you**.