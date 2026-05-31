# Awesome Claude Code & Cursor Configs

> Battle-tested `CLAUDE.md` and `.cursorrules` configs that make your AI coding agent stop guessing and start acting like a senior engineer.

Most people install Claude Code or Cursor and never configure them. Then they wonder why the
agent ignores their conventions, edits the wrong files, and invents structure that doesn't exist.

**The fix is a good config file.** This repo gives you real, working ones — free.

---

## 🆓 What's in this repo (free, MIT)

| File | What it does |
|------|--------------|
| [`templates/CLAUDE.nextjs.md`](templates/CLAUDE.nextjs.md) | Drop-in `CLAUDE.md` for Next.js (App Router) + TypeScript |
| [`templates/CLAUDE.python-fastapi.md`](templates/CLAUDE.python-fastapi.md) | Drop-in `CLAUDE.md` for Python + FastAPI |
| [`agents/code-reviewer.md`](agents/code-reviewer.md) | A subagent that reviews your diff like a senior engineer |

### How to use

1. Copy the template that matches your stack to your repo root as `CLAUDE.md`.
2. Edit the 3 lines marked `<<FILL IN>>`.
3. (Optional) drop `code-reviewer.md` into `.claude/agents/`.
4. Restart your agent. It now knows your conventions.

Each file has a header comment explaining exactly what it does.

---

## 🚀 Want the full kit?

This free repo is a taste. The complete **[Agentic Coding Starter Kit](https://alphaletgo.gumroad.com/l/agentic-coding-kit)** has everything:

- **6 stacks** — Next.js, Python/FastAPI, **Go, Rust, monorepo** (+ matching `.cursorrules`)
- **4 subagents** — code-reviewer, **test-writer, debugger, doc-writer**
- **Slash commands** — `/review`, `/ship`, `/test`, `/explain`
- **Hook recipes** — auto-format on edit, block committed secrets, run tests on stop
- **MCP setups** — Postgres, GitHub, filesystem, web fetch

👉 **[Get the full kit on Gumroad](https://alphaletgo.gumroad.com/l/agentic-coding-kit)** — launch-week price, free updates for life.

---

## ⭐ Found this useful?

Star the repo — it helps other developers find it. Contributions and stack requests welcome via issues.

*Maintained by [DevLoadout](https://alphaletgo.gumroad.com/l/agentic-coding-kit).*
