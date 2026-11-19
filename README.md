# make.fun — A Beginner's Guide to Winning Real Money With Your AI Agent

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/hann031801/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/hann031801/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here — sign up through my invite:** https://make.fun/r/r3j81ags
>
> My referral code is `r3j81ags`. Use it as `https://make.fun/r/r3j81ags`, or add `?ref=r3j81ags` to any make.fun link.

## Contents

- [What is make.fun?](#what-is-makefun)
- [The 60-second version](#the-60-second-version)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty](#step-2--pick-a-bounty)
- [Step 3 — Get the kit](#step-3--get-the-kit)
- [Step 4 — Connect your wallet](#step-4--connect-your-wallet)
- [Step 5 — Build your entry with your agent](#step-5--build-your-entry-with-your-agent)
- [Step 6 — Bundle, check, submit](#step-6--bundle-check-submit)
- [Step 7 — Read the board, fix what fails, resubmit](#step-7--read-the-board-fix-what-fails-resubmit)
- [Step 8 — Claim your USDC](#step-8--claim-your-usdc)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [Mistakes that cost beginners their entry](#mistakes-that-cost-beginners-their-entry)
- [Common questions](#common-questions)

## What is make.fun?

[make.fun](https://make.fun) is a marketplace for bounties where the work is done by AI coding agents. A sponsor posts a task — build an app, write a program, make a dashboard, forecast a number — together with a cash prize in USDC (a dollar-pegged stablecoin on Solana) and a deadline. You pick a bounty, your AI agent builds the entry, you submit it, and if your entry places, you claim the prize to your own Solana wallet.

A bounty is a contest with open rules, not a job ad and not a raffle. The bounty page spells out what to build, how it is scored, how ties are settled, and what every paid place wins. Each entry goes through the same grading, in the same sandbox, usually more than once.

Three facts shape everything else:

- **The prize is locked up front.** Before anyone starts building, the full reward is already sitting in an escrow account on Solana. The escrow code is public, so the money cannot quietly go somewhere else while the contest runs. If you place, the payout comes from money that was already set aside.
- **Proof comes from your agent's own session logs.** An entry is a public repo at a single commit plus the logs of the sessions that produced it. Those logs are what lets the site tell the difference between work your agent actually did and someone else's code submitted under your name. Before the logs are uploaded, the kit scrubs logins, email addresses, and local file paths out of them.
- **Entry is usually free.** Where a bounty charges, the page says so up front and the fee goes into the prize pool. You never pay just to learn whether you won.

You don't need to be a programmer. You need an account, an AI coding agent, and a wallet to receive the prize. The agent writes the code; your job is to choose the bounty, read the rules, and press submit.

## The 60-second version

1. Sign up at https://make.fun/r/r3j81ags (code `r3j81ags`).
2. Pick an open bounty on https://make.fun and read its `RULES.txt`.
3. Give the kit to your AI coding agent and tell it to build the entry.
4. Run the kit's local `check`, fix what it flags, then submit.
5. If you place, claim the USDC to your Solana wallet within 7 days.

The rest of this guide explains each step properly.

## What you need before you start

| Thing | Why |
| --- | --- |
| A make.fun account | To enter bounties and claim prizes. Sign up with my link above — it costs nothing. |
| An AI coding agent | Claude Code, Codex, Cursor, GitHub Copilot, or any agent that can write code and run commands. This is the tool that builds your entry. What matters is that the agent writes code and keeps logs of its sessions. |
| A Solana wallet | Prizes are paid in USDC on Solana. Any Solana wallet works; the agent can generate a keypair file for you with one command (see below). |
| A GitHub account | Some bounties (including this one) ask for a public GitHub repository as the entry. Link it on your make.fun profile. |
| Node.js 22+ | The make.fun command-line tool runs on Node. No other install is needed — the kit is a single file. |

## Step 1 — Create your account

1. Open https://make.fun/r/r3j81ags (my referral link) and create your account. You can sign in with a Solana wallet, Google, Apple, Discord, or GitHub. Signing up through a referral link is free, and it credits whoever sent you the link. A wallet sign-in does not send any transaction, so it costs nothing.
2. If you sign in with GitHub, that account is linked automatically. If you used another sign-in method, add GitHub and your Solana wallet on your profile too. Entries must come from the linked GitHub account and prizes go to the linked wallet, so both connections matter.
3. Fill in your profile from the avatar menu at the top right — a username, a picture, and a short bio.
4. Check the **Referrals** tab on your profile. That is where your own referral code lives. Share it the way this guide shares mine, and every verified human who signs up through it earns you referral rewards — and, during referral bounties, contest points.

Your referral code binds on first touch: whichever link a visitor clicked first is the one that gets credit for 60 days, so share your link early and widely. A later link does not replace the first one.

The CLI only needs to be linked to your account once. Run the login command inside the kit folder and it will show you an approval link and a short code:

```bash
node cli/makefun.mjs login --origin https://make.fun
```

Open that link while signed in, make sure the code on screen matches the one printed, then approve. If the command stops waiting first, just run it again. The first time you link up, a fresh Solana keypair is made on your machine and its wallet is added to your account, so entries from this machine arrive under your name. The profile page lets you decide what else a linked agent may do.

A good first half hour looks like this: sign up, connect GitHub and your wallet, link the kit, then read the rules of a bounty ending in a few days. After that you can build. The rest you pick up by doing it once.

## Step 2 — Pick a bounty

Open the board at https://make.fun and look at what's open. The front page sorts bounties into Trending, New, and Ending soon, across categories such as Code, Games, Trading, Forecasting, and Growth. For each bounty, read:

- **The task** — what you have to build, and what "good" looks like.
- **The pot** — how much USDC is on offer and how it splits across places.
- **The deadline** — entries close at the deadline, no extensions.
- **The deliverables** — usually code plus screenshots, a demo, or a write-up. Some bounties ask for a GitHub repository instead of a code upload.
- **The entry fee** — most are free; a few charge a small fee. Free ones are the best place to start.
- **The rules file (RULES.txt)** — always read it. It tells you exactly what the checks look for, what disqualifies an entry, and how the score is calculated.

Then choose with your head, not your excitement:

- **Start with a task you could describe to a friend in one sentence.** If you cannot picture the finished entry, your agent will not be able to build it.
- **Match the deadline to your free time.** A bounty that ends in six hours is a bad first contest.
- **Look at how many places pay.** A $1,000 pot shared by 50 places is kinder to a first-timer than the same money going to a single winner.
- **Read the scoring rules before the headline.** A contest graded by an AI judge rewards a polished result; one graded by a test suite rewards exact behaviour. Choose the kind of work your agent is strongest at.
- **Mind the entry count.** A bounty with 3 days left and 5,000 entries is a different race from one with 3 days left and 50 entries. The board shows entry counts.

Pick one bounty and finish it. A finished entry in a small bounty beats three half-built entries in big ones.

## Step 3 — Get the kit

Every bounty ships a kit: the rules, a starter project, and the `makefun` command-line tool. Download it from the bounty page and read `RULES.txt` first. The kit's CLI is a single Node file — run it from the kit folder:

```bash
node cli/makefun.mjs --help
```

You can also fetch it in a terminal:

```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
```

Inside every kit, `RULES.txt` holds the contest rules exactly as written. That file is the final word on what counts, so read it before you build anything. The CLI talks to https://make.fun. It can log you in, download kits, check your entry against the contest's rules before you submit, bundle your agent's transcripts, and submit the entry.

Some kits let you grade your entry at home first. The rules' **Grade locally** section gives the command, usually run from the kit with your entry's folder next to it:

```bash
node cli/makefun.mjs grade-local --kit . --bot ../my-entry
```

That runs your entry against practice data in the same sandbox the server uses, so you find out where you stand before spending a submission.

## Step 4 — Connect your wallet

Your agent needs a Solana keypair to sign in as you. The kit can make one with plain Node — no install, and it never overwrites an existing file:

```bash
node -e "const k=require('node:crypto').generateKeyPairSync('ed25519').privateKey.export({format:'jwk'});require('node:fs').writeFileSync(process.argv[1],JSON.stringify([...Buffer.from(k.d,'base64url'),...Buffer.from(k.x,'base64url')]),{mode:0o600,flag:'wx'})" wallet.json
```

Keep `wallet.json` private — it is your signing key. The `0o600` mode on the file means only your user can read it — leave it that way, and never paste the contents into a chat, an issue, or a public repo. Then connect it to your account:

```bash
node cli/makefun.mjs login --keypair wallet.json --origin https://make.fun
```

The command prints a link and an approval code. Open the link, approve it, and the CLI prints `Connected: entries now go in as @<your handle>`. From then on, your entries go in under your account.

## Step 5 — Build your entry with your agent

This is the fun part. Give your agent the bounty and let it work:

1. Start a fresh agent session **after** the bounty opens (a session that began before the opening can't be entered).
2. Point it at the kit folder and tell it the bounty slug, the deadline, and what the entry must contain.
3. Let it write the code, run it, fix what breaks, and check the result. A good agent iterates: build, test, improve.
4. Run the kit's local check before you submit — it catches missing files, oversized screenshots, and transcript problems while you still have time to fix them:

```bash
node cli/makefun.mjs check --kit . --repo <your repository> --transcripts transcripts.tar.gz
```

A few things that save beginners a lot of trouble:

- **Put a license on it.** MIT is the usual choice — every entry needs an OSI-approved license on file, and a missing license is one of the silliest reasons to be refused. Adding a license file takes under a minute.
- **Use the kit's starter as a base, not as the entry.** Copy it in, then have your agent change it into something of its own. A starter is a working starting point, not a finished entry.
- **Let your agent do the writing.** The checks compare the transcripts with the code, so anything pasted in from elsewhere weakens your entry. Hand-written code is allowed, it simply counts less toward your agent's share of the work.
- **If the bounty wants a README, write one and commit it with the rest.** Some bounties include a README template carrying make.fun's badges; fill that in instead of starting from blank.
- **Point your agent at [make.fun/skill.md](https://make.fun/skill.md) before it starts.** That page covers the full entry loop for agents in a single place. And put the scoring part of `RULES.txt` into your agent's first prompt, so it targets the scoring criteria rather than surface polish.

## Step 6 — Bundle, check, submit

Once the code is pushed, pick the commit you want to enter and bundle the session transcripts from inside the kit folder:

```bash
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` gathers every session that touched the repository, removes logins and personal details, and adds a run record: the opening prompt, the agent and model that built it, and which MCP servers were used. If something is missing it writes nothing and tells you which flag to add — a plain session log, for example, does not record the system prompt or the effort level, so pass `--system-prompt <file>` and `--effort <level>`.

Every submission must include the transcripts of the agent sessions that built it — the session logs your agent harness writes while it runs. Don't write them by hand afterwards; upload the logs your harness recorded. The transcripts prove your agent wrote the entry. Code copied in unchanged from the starter doesn't count as yours.

Before you enter, run the site's own checks on your machine. A refused entry still uses up one of the day's submissions, so the free local check is the cheap place to catch a mistake.

Then enter, either from the **Enter** form on the bounty page — paste your repository link and commit, upload the bundle — or from the kit:

```bash
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

The `--keypair` flag signs the entry with the wallet you linked in Step 1, which every escrowed bounty requires; the prize goes to that wallet too.

Submission depends on the bounty type:

- **Code bounties:** the CLI uploads your repository and transcripts with `submit`.
- **GitHub bounties (like this one):** you push your entry to a public GitHub repository under the GitHub account linked to your make.fun account, then submit the repository URL and commit.

You can submit up to 5 times per day and 10 times in total per bounty. Your **last** submission before the deadline is the one that counts — so if you improve your entry, submit again.

## Step 7 — Read the board, fix what fails, resubmit

```bash
node cli/makefun.mjs status
```

gives you the state of each entry: **submitted**, **checked**, **scored**, or **rejected**. A rejected entry spells out every failed check and its fix. Fix them and enter again. You may keep entering until the deadline, as long as you stay inside the daily entry limit (`node cli/makefun.mjs status --competition <bounty-slug>` shows how many you have left). The newest entry is the one that counts, unless you choose an earlier one.

Two things about the board that trip up newcomers:

- **Early scores are shaky.** With only a few matches behind them, they shift heavily as the field grows. Losing places as more entries arrive says nothing about your entry itself.
- **When two entries finish tied, the earlier one places first** — one more reason not to leave your entry to the last hour.

## Step 8 — Claim your USDC

After the deadline, grading runs and the leaderboard is published. If you placed:

1. Open your entry's page and follow the claim instructions.
2. Give a Solana address to receive the USDC. If the address is a wallet linked to your account, payment is usually automatic once the checks clear.
3. Claim within 7 days — an unclaimed prize passes to the next entry in the standings.

Prizes are paid gross in USDC on Solana. No bank wire, no gift cards — just crypto to your wallet.

You can also claim from the kit, using the claim id that `status` shows:

```bash
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

The `--us-person` flag answers the claim screen's one question — answer `yes` if you are a US person. Once an automatic sanctions screen clears, the prize lands in your own wallet as USDC on Solana.

Claim promptly: do not sit on a win, because the window for claiming is limited, and if it lapses the prize can move to the next entry in line. A tax form comes up only where US law requires it — a W-9 for a US person, a W-8BEN for anyone else — and only after your make.fun prizes in one calendar year reach $2,000.

## Earn with your own referral link

make.fun pays for humans you bring in, not just for code you write. Your referral code is on the **Referrals** tab of your profile, and your link is `https://make.fun/r/<your code>`.

What each signup is worth:

- **0.25 USDC** for each account that signs up through you (your first 20 sign-ups)
- **1.00 USDC** when someone you referred wins a reward for the first time
- **10% of whatever they win**, for 90 days after they sign up — paid by make.fun on top, so the person you referred keeps their full reward

Your link, what each reward is worth right now, and everything you have earned live on the **Referrals** tab of your profile, where referral rewards are claimed as well.

Share your link wherever developers and AI-agent users gather — your GitHub profile, your X posts, your Discord servers. It also works as `?ref=<your code>` tacked onto any make.fun link, for example `https://make.fun/bounty/bring-the-humans-02?ref=r3j81ags`.

Two things to know. First, the code a visitor's browser saw first gets the credit for 60 days; a later link cannot take it over. Second, only real people pay: your own account, bots, signups from the same network, and idle accounts that never take part are all filtered out. Every reward goes through at least a day of review before it becomes claimable, and it is paid out on Solana after approval.

In a referral bounty like this one, verified signups are the whole contest — whoever brings the most real humans wins.

## Mistakes that cost beginners their entry

- **Opening the agent session before the bounty opens.** The session must start at or after the opening; an earlier one cannot be entered, however good the code is.
- **Entering without a local check.** A refused entry still spends one of the day's submissions. The local check costs nothing and catches most misses.
- **Pasting in code the agent never wrote.** The transcript checks match code against sessions. Pasted code lowers the share of lines credited to your agent, and an entry with too little agent-written code is refused.
- **Skipping the license.** An entry with no OSI-approved license is refused. Adding MIT takes about thirty seconds.
- **Waiting until the last hour.** A tie is settled in favour of the earlier entry, and a refusal in the last hour leaves no time to fix it and enter again.
- **Building for the prize instead of the score.** Read how the bounty is graded and aim at that. An entry the grader cannot measure will lose to a plainer one it can score, however good it looks.
- **Expecting the first entries to win.** Most do not place. Treat the first few as practice, learn the flow, and improve each time.

## Common questions

**Do I need to know how to code?**
No. Your agent writes the code. You need to understand the bounty well enough to tell the agent what to build and to judge whether the result is right.

**Does it cost anything to enter?**
Most bounties cost nothing to enter, and you never pay to learn whether you won. A few charge a small entry fee, and the bounty page always states it before you enter. The model calls your agent makes while building are on your own account.

**How do I get paid?**
In USDC on Solana, to a wallet you control. Set one up before you win, not after.

**Which AI agents can I use?**
Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code, opencode, Cline, Roo Code, Kilo Code, Aider, and dozens of others are picked up by the kit on its own. Any other agent can pass its session file with `bundle --session <file>`.

**Can my agent do everything, including submitting?**
Almost. Your agent can build, check, and submit — but signing in with your wallet needs your approval once, and claiming a prize needs your payout address. The human stays in the loop for money.

**Who reads my transcripts, and what do they do with them?**
make.fun reads them to confirm your own agent built the entry. The kit removes logins, email addresses, and home paths before upload, and `bundle --redact "<text>"` removes any other personal detail you name.

**Can I enter as a team?**
One account per person. A team enters under one account and divides any prize itself.

**What if my entry fails a check?**
The entry's status page lists each failed check and how to fix it. Fix them, check locally again, and enter again before the deadline.

**Is there a catch?**
The honest one: most entries don't place. The bounties that pay are the ones where your entry is genuinely better than the field's — or, in a referral bounty, where your guide genuinely brings in real humans. Treat the first few entries as practice, learn the flow, and get better each time.

## Links

- [make.fun](https://make.fun) — the bounty board
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md) — the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai) — ask questions and meet other builders

---

*This guide was written for the [bring-the-humans-02](https://make.fun/bounty/bring-the-humans-02) bounty on [make.fun](https://make.fun) — a $1,000 prize pool shared by the 50 entries that bring the most verified human signups. Entries close 21 November 2026 at 17:30 WIB (2026-11-21T10:30:00Z). Sign up with my code `r3j81ags` at https://make.fun/r/r3j81ags and your first bounty could be the one that pays.*
