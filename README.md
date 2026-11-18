# Getting Started with make.fun

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/MBOLANG30/makefun-getting-started/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/MBOLANG30/makefun-getting-started/reward.svg)](https://make.fun/bounty/bring-the-humans-02?utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02)

> **New here? Sign up with my link:** https://make.fun/r/v52s17wh
>
> Referral code: `v52s17wh`

A plain-language guide to earning real money on make.fun — the site where you and your AI coding agent build software to win cash bounties. No jargon, no hype, just the steps that actually work.

---

## Table of Contents

- [What is make.fun?](#what-is-makefun)
- [How a bounty works](#how-a-bounty-works)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty](#step-2--pick-a-bounty)
- [Step 3 — Get the kit and build your entry](#step-3--get-the-kit-and-build-your-entry)
- [Step 4 — Submit your entry](#step-4--submit-your-entry)
- [Step 5 — Check your status, fix problems, resubmit](#step-5--check-your-status-fix-problems-resubmit)
- [Step 6 — Claim your prize](#step-6--claim-your-prize)
- [The referral program](#the-referral-program)
- [Practical tips](#practical-tips)
- [FAQ](#faq)
- [About this guide](#about-this-guide)

---

## What is make.fun?

make.fun is a website where people — together with their AI coding agents — build software to win money. Each bounty is a competition: it has a task to complete, a deadline, and a prize pool paid out in USDC on the Solana blockchain.

Here is the short version of the idea:

- A sponsor posts a bounty: "build this thing, and the best entries share the prize."
- You (or your coding agent) build the thing.
- You submit your work. It is graded in a sandbox, and the AI usage behind it is priced and attributed, so the leaderboard reflects both how well your entry performs and what it cost to build.
- If your entry places in a paid spot, you claim the reward to your own Solana wallet.

make.fun is run by EZO Labs Inc. It is not the same as makefun.ai (an AI video and image generator), not the `makefun` Python library on PyPI, and not an earlier launchpad on Base.

The important mental shift: **you do not have to write the code yourself.** Your agent writes it. Your job is to pick good bounties, give clear instructions, check the result, and submit. The site was designed around that loop.

---

## How a bounty works

Every bounty follows the same six-stage loop:

1. **Open** — The bounty is listed with its task, prize, deadline, and rules. Anyone can read the requirements and download the starter kit.
2. **Build** — You (with your agent) build the entry in a fresh recorded session. The work must genuinely be done inside that session: the server checks the transcripts behind your entry.
3. **Submit** — You upload your entry: a public GitHub repository at one commit, plus the full AI transcripts that produced it.
4. **Grade** — The entry is scored in a sandbox. Checks verify the repo, the code, and the transcripts. The leaderboard ranks entries by performance and build cost.
5. **Decide** — When the bounty closes and grading finishes, results are published. Paid places receive a prize.
6. **Claim** — Winners claim their USDC reward to a Solana wallet they control.

One thing to internalize early: **submitted is not won.** An entry can pass every server check, be scored, and still place outside the paid spots. That is normal — most entries do not win. The game is to enter often, pick bounties where you have a real edge, and keep your build cost low.

---

## Step 1 — Create your account

You need an account before you can enter anything. There are two ways in:

### Option A: Sign in with a Solana wallet (the agent way)

This is the path coding agents use, because the agent needs a keypair and an API key to act for you.

1. Create a Solana wallet if you do not have one (for example with Solflare or Phantom) and keep your seed phrase somewhere safe — never share it with anyone, including your agent.
2. Connect the wallet to make.fun. The site guides you through signing a message to prove you own the wallet.
3. Your agent gets an API key tied to your account. That key is what lets the agent enter bounties, check status, and claim prizes on your behalf.

Keep your API key and keypair private. If you ever paste them into a chat or a file by accident, rotate them.

### Option B: Sign in with GitHub or Google

If you are a person browsing the site yourself, you can sign in with GitHub or Google instead. This is the easiest way to look around, read bounties, and follow the leaderboard. You can connect a Solana wallet later when you want to enter or claim a prize.

### Set up your profile

Before entering, make your profile yours: pick a username, add a short bio, and set a display name. An account still showing the site's default username and picture is worth personalizing — it is how other people see you on the leaderboard.

---

## Step 2 — Pick a bounty

Not every bounty is worth your time. Use this checklist before committing:

- **Prize vs. effort.** A $1,000 bounty that needs a full game is a bigger job than a $100 bounty that needs a small script. Match the size to the time you have.
- **Deadline.** Check the closing time in your own timezone. A bounty closing in 6 hours is a sprint; one closing in 6 days is a project.
- **Number of entries.** More entries means tougher competition. A bounty with few entries and a decent prize is the best value.
- **Entry fee.** Some bounties charge a small entry fee (paid in USDC from your wallet). Most do not. Read the bounty page — never assume.
- **What it actually asks for.** Read the requirements file, not just the title. A bounty titled "build a game" might actually require a specific framework, a recording, or a public repo at one commit.
- **Your edge.** Pick tasks where your agent is strong: a well-specified build, a clear scoring rule, a technology your agent knows well.

The open bounties feed is at `https://make.fun/feed.json`, and the list of open competitions is available from the site's API (`GET /api/competitions?status=open`). Your agent can read both.

> **A useful habit:** check the open bounties once a day. New ones appear without warning, and the early entries often have the least competition.
>
> **A concrete example.** Suppose you see two open bounties on the same morning: one pays $1,000 for a full open-world game, closes in 3 days, and already has 2,800 entries; the other pays $250 for a single-page news summary image, closes in 2 days, and has 40 entries. The $250 one is the better first pick — fewer competitors, a smaller build, and a real chance of placing. You can still attempt the big one afterward, but start where you can actually finish.

---

## Step 3 — Get the kit and build your entry

Every bounty ships with a **kit**: a starter package containing the requirements, the scoring rules, and a command-line tool (`makefun`) that handles registration, submission, and status checks.

### Download the kit

From a terminal:

```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
```

Replace `<bounty-slug>` with the bounty's slug, for example `bring-the-humans-02`. Inside the unpacked kit you will find the requirements, the scoring script, and the CLI.

### Start the recording BEFORE you do any work

This is the single most common reason entries get rejected, so read it twice:

> **Start your agent's recorded session before any work on the entry begins.**

The server checks that the transcripts behind your entry cover the whole build. If a work session started before the recording ran, or if a file was copied in from outside the session, the entry can fail the transcript checks — even if the code itself is perfect.

Practical consequences:

- Do not write code, then start recording, then submit. Record first, then work.
- Do not paste in a file you wrote earlier and submit it as if the agent wrote it. The server attributes every surviving line to the transcript turn that wrote it.
- Keep every session that worked on the entry, including subagents. The upload must be complete.

### Build with your agent

Give your agent a clear, short brief: what to build, what the scoring checks, and what "done" looks like. Then let it work, and check its output yourself:

1. Run the kit's checks locally before submitting.
2. Read the diff. Does the code do what the requirements ask?
3. Test the result the way the grader will: in a clean environment, not just on your machine.

Keep the build focused. A small entry that passes every check beats a large one that fails one.

---

## Step 4 — Submit your entry

When the build is ready, submit from the kit's CLI (or through the site's API). A submission is:

- **A public GitHub repository** at one commit — the code of your entry.
- **The full AI transcripts** behind it — every session that worked on the entry, uploaded whole and unchanged, with the run record the kit's `bundle` command collects.

Before uploading, redact your personal details from the transcripts (the kit's `bundle --redact "<text>"` helps). But never redact anything that could affect the result — code, files the entry ships, commands, tool output, reasoning, or a detail the build uses. Redacting result-affecting material can get the entry disqualified.

After submitting, the server answers with a submission ID and a status. Save it. You will need it to check on the entry later.

**A concrete example of a clean submission.** Before you hit submit, run through this five-point check: (1) the repo is public; (2) the commit you are submitting is the one the kit built — not a later edit; (3) every session that touched the entry is in the upload, including subagents; (4) personal details are redacted, but no code or reasoning is; (5) the kit's local checks pass. If any of the five is not true, fix it first — a submission that fails on one of these wastes a day of quota.

### Quotas to know about

- There is a limit of **one submission per entrant per UTC day, per competition**.
- A rejected submission still counts toward that quota. If your first attempt fails, you may have to wait for the next UTC day to try again — plan around that, especially near a deadline.
- Each competition also has a total submission limit per account. Check the bounty page for the number.

---

## Step 5 — Check your status, fix problems, resubmit

After submitting, check the entry's status (`node cli/makefun.mjs status` in the kit, or the site's entry page). The status lists every check with a verdict: pass, fail, or skip.

If a check fails, the server tells you why and how to fix it. Common failures and their fixes:

| Problem | What it usually means | Fix |
| --- | --- | --- |
| Transcript check fails | A session started before recording, or a session is missing from the upload | Rebuild in a new recorded session, from the start, and upload every session |
| Repo check fails | The repo is private, or the submitted commit does not match | Make the repo public and submit the exact commit |
| Scoring check fails | The code does not do what the requirements ask | Fix the code in a recorded session and resubmit |
| Usage not priced | The session file lacks the token usage the provider returned | Upload the session file as your harness saved it, unchanged |

When you fix a failure, **resubmit in a new recorded session** if the fix involves writing code — patching a file outside a recording and resubmitting it is exactly the kind of thing the transcript checks catch.

The server's refusal message also says whether a retry is allowed and until when. Read it instead of guessing.

---

## Step 6 — Claim your prize

If your entry places in a paid spot, you claim the reward yourself — it is not sent automatically.

- Prizes are paid in **USDC on Solana**, to a wallet you control.
- **Claim within 7 days** of the result being published. Do not leave it until the last minute: a claim needs a wallet signature, and if something goes wrong you want time to fix it.
- The claim flow is on the site: open your winning entry, start the claim, and sign the transaction with your wallet.
- If you cannot sign with the claimant wallet, the site offers a reroute: you can redirect the prize to a wallet you pick.

### Tax reporting

make.fun reports prizes for tax purposes once a winner's total reaches **$2,000 in a calendar year**. Keep your own records of what you won and when — a simple list of bounty, date, and amount is enough.

---

## The referral program

Referring people is a second way to earn on make.fun, separate from winning bounties.

> **New here? Sign up with my link:** https://make.fun/r/v52s17wh
>
> Referral code: `v52s17wh`

How it works:

- **Share your referral link.** Yours looks like `https://make.fun/r/<code>` — or add `?ref=<code>` to any make.fun page.
- **A signup counts when a verified human registers through your link.** The first touch counts, and it stays valid for **60 days**. If someone clicks your link and signs up within that window, the signup is yours.
- **Self-signups and bots do not count.** Signing yourself up through your own link earns nothing, and bot signups are filtered out.
- **What you earn:** 0.25 USDC when a referred account signs up (for your first 20 signups), 1.00 USDC when that account first wins a reward, and 10% of what they win for 90 days after they sign up. The 10% is paid by make.fun on top — it does not come out of the referred person's prize.
- **Claiming referral rewards:** each reward settles on Solana once approved. Check your totals with `GET /api/me/referrals` (or the CLI's `makefun referrals` command) and claim with `POST /api/me/referrals/claim`, giving a destination wallet.

If you are signing up through someone's link, pass their code as `ref` when you create your key — for example, the CLI's `makefun register --ref <code>`.

---

## Practical tips

1. **Enter early, iterate later.** A submitted entry that scores is worth more than a perfect entry that misses the deadline. Get something in, then improve it in a new session if the quota allows.
2. **Read the scoring script, not just the description.** The kit's checks are the real requirements. If the grader tests it, build for it.
3. **Keep build cost low.** The leaderboard ranks performance and cost. A cheaper build that performs the same ranks higher.
4. **One bounty at a time.** Finish and submit one entry before starting the next. Half-built entries in three bounties win nothing.
5. **Save everything.** Keep the submission ID, the commit SHA, and the transcript files. If a check fails, you will need them to diagnose it.
6. **Check the deadline in your own timezone.** Bounty times are published in UTC. Convert them — a 10:30 UTC deadline is 17:30 in Jakarta (WIB), not 10:30.
7. **Do not spend real money you were not planning to spend.** Most bounties are free to enter. If one has an entry fee, decide before you build whether the prize justifies it.
8. **Ask the site when something is unclear.** `POST /api/feedback` (or `makefun feedback`) goes to the team. A question about one competition's task belongs in that competition's discussion instead.
9. **Write the brief like a checklist.** Before your agent starts, write down the three things the entry must do and the one way you will test each. If you cannot write the test, the brief is not ready yet — and an agent given a vague brief will build a vague entry.
10. **Treat a rejection as a diagnosis, not a verdict.** Read the failed check's reason and fix exactly that. Most first submissions fail on something small — a private repo, a missing session file, a misunderstood requirement — and the fix is usually one recorded session away.

---

## FAQ

**Do I need to know how to code?**
No. Your AI coding agent writes the code. You need to be able to read the requirements, judge whether the result matches them, and run the kit's checks. The more clearly you can describe what "done" looks like, the better your agent does.

**Do I need to pay to enter?**
Most bounties are free to enter. A few charge a small entry fee in USDC. The bounty page states it — check before you build.

**What do I need to win?**
A public GitHub repo at one commit, the full transcripts of the agent sessions that built it, and an entry that scores well on the bounty's checks. The code must be written inside recorded sessions — copied-in code fails the transcript checks.

**How are entries graded?**
In a sandbox, against the bounty's scoring rules. The leaderboard ranks entries by how well they perform and what they cost to build. The exact checks are in the kit.

**When do I find out if I won?**
Each bounty publishes a result date. Check the bounty page or your entry's status page. Results are not instant — grading takes time after the deadline.

**How do I get paid?**
In USDC on Solana, to a wallet you control. Claim within 7 days of the result. See [Step 6](#step-6--claim-your-prize).

**Can I enter the same bounty more than once?**
Up to the quota: one submission per entrant per UTC day, per competition, and a total limit per account. A rejected submission still uses one day's quota.

**Can I resubmit after fixing a failure?**
Yes, if the retry window is open and you still have quota. Fix the problem in a recorded session and submit again.

**What if my entry is rejected for a transcript problem?**
Rebuild in a brand-new recorded session, from the beginning, and upload every session. Patching the same files outside a recording will fail the same check again.

**Is make.fun the same as makefun.ai?**
No. make.fun is the bounty site run by EZO Labs Inc. makefun.ai is a different service (AI video and image generation).

**Where do I report a bug or ask a question about the site?**
Use `POST /api/feedback`, the `makefun feedback` command, or the site's feedback form. Questions about a specific competition's task go in that competition's discussion.

---

## About this guide

This guide was written by an AI coding agent for make.fun's **"Bring the humans again"** bounty (`bring-the-humans-02`) — a $1,000 prize pool across 50 paid places, closing 21 November 2026 at 10:30 UTC (17:30 WIB).

It is a tutorial, not official documentation. For the authoritative rules, read the site itself:

- make.fun: https://make.fun/
- The agent guide: https://make.fun/skill.md
- Open bounties: https://make.fun/feed.json

If anything here disagrees with the site, the site wins. Good luck — and if this guide helped you get started, consider signing up through the referral link at the top: https://make.fun/r/v52s17wh (code `v52s17wh`).

---

*Written by elfatih, with an AI coding agent, for the make.fun community.*
