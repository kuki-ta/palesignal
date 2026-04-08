# PALESIGNAL
### Edge technology discovery and civilian threat assessment protocol.

**[palesignal.netlify.app](https://palesignal.netlify.app)**

---

Public opinion on edge technology exists in isolated pockets. Reddit threads, podcasts, Discord servers. No mechanism for consensus, no shared record, no place where the signal actually accumulates. For technologies that will affect everyone, that feels like a problem worth trying to solve, even in a small and slightly unhinged way.

PALESIGNAL is a structured public record of edge technologies across neural, biotech, robotics, energy, space, quantum, and other categories. Anyone can vote, file a report, and push back on the official narratives. The signal gets clearer the more people engage by picking a side.

The aesthetic is cyberpunk. The premise is serious. The Archivist is a fictional former GS-12 analyst who decided the public should see the file. You don't have to buy the lore to find the database useful.

---

## What it does

- **150+ products** across categories, each with an authorized narrative, a suppressed narrative, and an independent AI assessment
- **Voting** — asset or threat, per product, deduplicated per session
- **Civilian reports** — open comment field, rate-limited, no account required
- **AI assessments** — on-demand analysis via the Anthropic API, proxied server-side, with archivist persona and a hard ban on em-dashes
- **Live data** — everything runs off a Supabase backend; no hardcoded seed data
- **Streak notifications** — the site notices if you're paying attention

---

## Stack

- **Frontend** — Vanilla HTML/CSS/JS, single file, no framework
- **Database** — Supabase (PostgreSQL), with RLS on all tables and public read/insert policies
- **Serverless** — Netlify Functions proxying the Anthropic API (API key server-side only)
- **AI** — Anthropic API via Claude, assessment prompt tuned for dry, resigned, mildly absurd output
- **Deployment** — Netlify, connected to GitHub for continuous deployment
- **Dev environment** — VS Code

---

## Privacy

Session tracking uses a cryptographically random ID via `crypto.getRandomValues()`, stored in `sessionStorage` only. It dies when the tab closes. Nothing persists across sessions. Vote deduplication and comment rate limiting are both session-scoped. No cookies, no accounts, no cross-session fingerprinting.

---

## Why I built it

Well first of all, because it's fun. Secondly, because I'm a fan of cyberpunk comics and art, and a person genuinely unsettled that the public conversation about technologies that will reshape everything happens in scattered, unconnected places with no way to aggregate the vibes.

---

## Status

Live at [palesignal.netlify.app](https://palesignal.netlify.app). Built and shipped in two days as a solo project, not open source. Ongoing but takes a back seat to other projects.

---

*I read everything. — The Archivist*
