<div align="center">

<img src="https://img.shields.io/badge/RR-SKILLVERSE-4F46E5?style=for-the-badge&labelColor=1E1B4B&color=4F46E5" alt="RR Skillverse" height="32"/>

# 🗜️ compact-mode — GitHub Copilot

**Cut Copilot token usage 60–75%. Direct answers. Zero filler.**

<br/>

[![RR Skillverse](https://img.shields.io/badge/🌐%20rrskillverse.in-Visit-4F46E5?style=for-the-badge&labelColor=1E1B4B)](https://rrskillverse.in)
[![GitHub](https://img.shields.io/badge/GitHub-raushan1107-4F46E5?style=for-the-badge&logo=github&labelColor=1E1B4B)](https://github.com/raushan1107)
[![License: MIT](https://img.shields.io/badge/License-MIT-4F46E5?style=for-the-badge&labelColor=1E1B4B)](LICENSE)
[![Stars](https://img.shields.io/github/stars/raushan1107/compact-mode-copilot?style=for-the-badge&labelColor=1E1B4B&color=4F46E5)](https://github.com/raushan1107/compact-mode-copilot/stargazers)

<br/>

*Built by **[Raushan Ranjan](https://github.com/raushan1107)** · Senior Trainer & Developer · [RR Skillverse](https://rrskillverse.in)*

</div>

---

> ⭐ **If this saves you tokens, give it a star** — it helps others find it!
>
> 👉 Also using Claude? Check the **[Claude version of this skill](https://github.com/raushan1107/compact-mode-claude-skill)**

---

## Why This Exists

GitHub Copilot injects your `copilot-instructions.md` into **every single chat request** automatically. A bloated file burns tokens before you even ask a question.

This repo gives you a **lean, production-ready** setup — a tight always-on instructions file + a full-featured prompt file loaded only when you need it.

---

## How It Works — 2 Files, 2 Roles

| File | Role | Token cost |
|---|---|---|
| `.github/copilot-instructions.md` | Always-on. Core rules only. Under 30 lines. | Low — injected every session |
| `.github/prompts/compact-mode.prompt.md` | Full instructions. Triggered on demand. | Zero when not active |

This split means you get **always-on filler removal** without burning tokens on the full ruleset every session.

---

## What Gets Dropped

At all levels:
- ❌ Pleasantries: "Sure!", "Certainly!", "Happy to help!", "Great question!"
- ❌ Hedging: "you might want to", "perhaps consider"
- ❌ Filler: "basically", "actually", "simply", "essentially"
- ❌ Restatements: "So what you're asking is..."

Always kept:
- ✅ Full code blocks — never abbreviated
- ✅ Exact error messages
- ✅ Security warnings — always full prose
- ✅ Training/learner content — auto-exits compact mode

---

## Intensity Levels

| Level | Why/Reason included | Style |
|---|---|---|
| `compact lite` | ✅ Always — 1 line before every how | Full sentences, clean prose |
| `compact dev` | ⚡ Only if non-obvious | Fragments OK, stack abbreviations |
| `compact ultra` | ❌ Off — pure output | Max abbreviation, arrows for causality |

---

## Quick Example

**"Why is my Azure OpenAI call returning 429?"**

| Level | Response |
|---|---|
| **lite** | "TPM quota on your deployment is exhausted — Azure throttles when you exceed it. Add exponential backoff or raise TPM quota in AI Foundry." |
| **dev** | "TPM limit hit. Add exponential backoff or raise TPM quota in AI Foundry." |
| **ultra** | "TPM quota hit → 429. Backoff or ↑ TPM in AI Foundry." |

---

## Installation

### Step 1 — Add files to your repo

**Option A — Clone and copy (recommended)**
```bash
git clone https://github.com/raushan1107/compact-mode-copilot.git
cp compact-mode-copilot/.github/copilot-instructions.md YOUR_REPO/.github/
cp -r compact-mode-copilot/.github/prompts YOUR_REPO/.github/
```

**Option B — Download ZIP**
1. Click **`Code` → `Download ZIP`** on this page
2. Extract and copy the `.github/` folder into your repo root
3. Commit and push

### Step 2 — Commit to your repo
```bash
cd YOUR_REPO
git add .github/
git commit -m "feat: add compact-mode Copilot instructions"
git push
```

That's it. Every team member who clones your repo gets compact-mode automatically.

---

## How to Use — VS Code + Copilot Chat

**Always-on (automatic):**
Once installed, Copilot drops filler on every response. No command needed.

**Activate full compact mode:**

In Copilot Chat, type:
```
compact dev
```
or
```
compact ultra
```

**Using the prompt file:**
```
@workspace /compact-mode compact ultra — fix the 422 on my POST route
```

**Switch levels:**
```
compact lite    ← reasons always included
compact dev     ← default, smart compression
compact ultra   ← maximum, pure output
```

**Turn off:**
```
stop compact
normal mode
```

---

## How to Use — GitHub.com Copilot Chat

1. Go to any repo that has these files committed
2. Open **Copilot Chat** on GitHub.com
3. The `copilot-instructions.md` is automatically active
4. Type `compact ultra` to activate full compression

---

## Repo Structure

```
compact-mode-copilot/
├── README.md
├── LICENSE
└── .github/
    ├── copilot-instructions.md      ← always-on, lean rules
    └── prompts/
        └── compact-mode.prompt.md  ← full instructions, on demand
```

---

## Smart Auto-Behaviour

| Context | Behaviour |
|---|---|
| Code debugging / fix | ultra compression |
| Azure / cloud config | dev — portal paths kept |
| API / backend dev | dev — reasons on non-obvious fixes |
| **Training content / labs** | **AUTO-EXIT — full prose** |
| **Documentation writing** | **AUTO-EXIT — full prose** |
| Security warnings | Always full prose |
| Destructive actions | Always full prose |

---

## Why This Over Just "Be Brief"?

| Feature | `"be brief"` | **compact-mode** |
|---|---|---|
| Drops filler / hedging | ✅ | ✅ |
| Level-aware (lite/dev/ultra) | ❌ | ✅ |
| Auto-exits for learner content | ❌ | ✅ |
| Always-on via instructions file | ❌ | ✅ |
| Full rules on demand via prompt | ❌ | ✅ |
| Security warnings always full | ❌ | ✅ |
| Zero token cost when not active | ❌ | ✅ |

---

## Also Using Claude?

This is the Copilot version. The Claude version works via ZIP upload to claude.ai Skills.

👉 **[compact-mode for Claude](https://github.com/raushan1107/compact-mode-claude-skill)**

---

## Support This Project

- ⭐ **Star this repo** — helps others find it
- 🔁 **Share with your team** — one commit, everyone benefits
- 🐛 **Found a bug?** — [open an issue](https://github.com/raushan1107/compact-mode-copilot/issues)
- 🤝 **Want to contribute?** — PRs welcome

---

## About RR Skillverse

[**RR Skillverse**](https://rrskillverse.in) is a trainer-led learning platform by Raushan Ranjan — Microsoft Certified Trainer with 9+ years in IT training and software development, specialising in Azure, Power Platform, .NET, and AI Agent development.

---

<div align="center">

Made with 🧠 by [Raushan Ranjan](https://rrskillverse.in) &nbsp;·&nbsp; [RR Skillverse](https://rrskillverse.in) &nbsp;·&nbsp; [GitHub](https://github.com/raushan1107)

MIT License · v1.0.0

</div>
