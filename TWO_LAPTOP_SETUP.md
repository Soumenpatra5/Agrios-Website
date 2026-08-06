# Working on AgriOS from two laptops (office + home)

The goal: both laptops always have the same, latest version. GitHub is the single
source of truth — the "real" copy lives there, and each laptop syncs to it.

You already use GitHub with Claude Code, so this will feel familiar. You can either run
the git commands yourself, or just tell Claude Code to do each step (both shown).

---

## ONE TIME — set up the repo (do this on ONE laptop only)

Start on whichever laptop currently has the newest AgriOS files.

1. Unzip the deploy folder somewhere permanent (e.g. `C:\Users\saika\agrios-website\`).
   Do NOT keep it in Downloads — pick a proper project folder.

2. Open Claude Code in that folder and say:

   > "Set up git in this folder, create a `.gitignore` for a static site, then create a
   > new PRIVATE GitHub repo called `agrios-website` and push everything to it."

   (Or do it by hand:)
   ```
   git init
   git add .
   git commit -m "AgriOS website — initial commit"
   gh repo create agrios-website --private --source=. --push
   ```

3. Done. The project now lives on GitHub. This is your source of truth.

---

## ONE TIME — connect the SECOND laptop

On the other laptop, you don't copy files by hand — you clone from GitHub:

1. Pick a project folder (e.g. `C:\Users\saika\agrios-website\`).

2. Open Claude Code there (or a terminal) and say:

   > "Clone my GitHub repo `agrios-website` into this folder."

   (Or by hand — replace `USERNAME` with your GitHub username:)
   ```
   git clone https://github.com/USERNAME/agrios-website.git .
   ```

3. Both laptops are now linked to the same repo.

---

## EVERY DAY — the rhythm (both laptops)

This is the whole discipline. Two habits:

**When you SIT DOWN to work** — pull the latest first:
```
git pull
```
> Tell Claude Code: "Pull the latest changes from GitHub."

**When you FINISH working** — push your work back:
```
git add .
git commit -m "short note on what I changed"
git push
```
> Tell Claude Code: "Commit my changes with a message and push to GitHub."

That's it. Pull at the start, push at the end. Both laptops stay in sync automatically.

---

## The golden rule (avoids 99% of problems)

**Always `git pull` BEFORE you start, and `git push` AFTER you finish.**

The only way things go wrong is if you edit on both laptops without pushing/pulling in
between — then git has two versions to reconcile (a "merge conflict"). If that ever
happens, don't panic: tell Claude Code "I have a merge conflict, help me resolve it" and
it will walk you through it. But if you keep the pull-first / push-after habit, it won't
happen.

---

## Bonus: auto-deploy to Vercel (highly recommended)

Once the repo is on GitHub, connect it to Vercel ONCE:

1. Go to vercel.com → New Project → Import `agrios-website` from GitHub.
2. It's a static site — no build settings needed. Deploy.

After that, **every `git push` automatically updates your live website.** You never
manually deploy again. Edit on either laptop → push → the live site updates itself.

---

## Quick reference card

| When | Command | Or tell Claude Code |
|---|---|---|
| Start of session | `git pull` | "Pull the latest from GitHub" |
| End of session | `git add . && git commit -m "..." && git push` | "Commit and push my changes" |
| Check what changed | `git status` | "What's changed since last commit?" |
| See history | `git log --oneline` | "Show me the recent commits" |
| Merge conflict | — | "Help me resolve this merge conflict" |

---

## What NOT to do

- ❌ Don't email the files to yourself or copy via pen-drive — that's how versions drift.
- ❌ Don't edit on laptop B without first pulling laptop A's pushed changes.
- ❌ Don't keep the project in Downloads or a temp folder.
- ✅ Do treat GitHub as the truth: pull before, push after, every time.
