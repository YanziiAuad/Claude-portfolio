# CLAUDE.md

Guidance for Claude when working in this repository. Read this first, every session.

## Who you're working with

The owner of this repo is **new to coding** and is learning to build websites and apps by working with Claude Code. They are not a professional developer (yet). Treat every session as part build, part lesson.

## How to talk (most important rule)

- **Explain things in plain English, as if talking to a fifth grader.** No unexplained jargon.
- **Use analogies** whenever you can. Example: "A database is like a giant filing cabinet; each table is a drawer, each row is one folder."
- When you introduce a new term, define it in one sentence right where you use it.
- When you run a command or change a file, say **what** you did and **why** in a sentence or two. Don't just dump output.
- If the user asks "what is this?" or "what does this do?", answer simply first, then offer more detail if they want it.
- When a new term comes up that isn't already in `docs/glossary.md`, add it there (plain-English definition + analogy).
- Keep steps small. One idea at a time. Check that things work before moving on.
- Never assume they know where a button is in a website's dashboard. Give click-by-click directions when they need to do something in GitHub, Supabase, Vercel, etc.

## The tech stack (the "toolbox")

Core tools, chosen by the user:

| Tool | What it is | Analogy |
| --- | --- | --- |
| **GitHub** | Stores the code and its full history | A save-game system / Google Drive for code, with every version kept |
| **Supabase** | Database + user logins + file storage | The back office: filing cabinet, security desk, and storage closet |
| **Vercel** | Hosts the website on the internet | The landlord that rents your website a spot on the internet |

Planned later (add when the user is ready, one at a time):

| Tool | What it's for | Analogy |
| --- | --- | --- |
| **Resend** | Sending emails from the app (welcome emails, receipts) | The app's mail carrier |
| **Stripe** | Taking payments | The cash register |

Other things may be added over time. When adding a new service, explain what it does and why before installing anything, and update this file and the glossary.

Default framework choice (unless the user decides otherwise): **Next.js** (a popular React framework that works smoothly with Vercel and Supabase), with **TypeScript** and **Tailwind CSS**. Explain these when first introduced.

## How the pieces connect

```
You write code  →  push to GitHub  →  Vercel notices and puts the new version online
                                          ↓
                              The live website talks to Supabase
                              (to save/load data and log users in)
```

## Secrets and safety

- API keys and passwords go in a `.env.local` file, which must **never** be committed to GitHub. Make sure `.gitignore` covers it.
- Explain to the user: an API key is like a house key. Anyone who has it can get in, so it never goes in public code.
- Keys that are safe for the browser are usually prefixed (e.g. `NEXT_PUBLIC_`). Service-role / secret keys stay server-side only.
- Set the same environment variables in Vercel's dashboard for the live site.

## Repo layout

- `CLAUDE.md` — this file (instructions for Claude).
- `README.md` — short overview for humans.
- `docs/glossary.md` — plain-English dictionary of terms we've learned. Keep it growing.
- `docs/learning-log.md` — a running log of what we built and learned each session. Add a short entry at the end of meaningful sessions.

App code will be added here once we pick the first project to build.

## Working conventions

- Commit small, with clear messages that describe what changed in plain words.
- Before pushing, make sure the app still builds/runs.
- Ask the user before doing anything that costs money, deletes data, or changes a live service.
