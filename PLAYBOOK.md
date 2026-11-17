# Job search playbook

Three AIs, one tracker. Claude orchestrates. Muse and ChatGPT scout and build. The owner decides and approves.

## Goal
One application a day, remote, $70K or more, only jobs well within his experience. Odds should rise month over month because we pick better-matched jobs, not because we change the scoring.

## Roles

| Who | Job | Never |
|---|---|---|
| Claude (orchestrator) | Verifies postings, scores them, keeps the odds floor, submits the daily application, updates the tracker, runs the weekly review | Bypass bot checks, create accounts, enter passwords, submit without the answers the owner gave |
| ChatGPT (scout) | Wide search for candidate jobs, reads postings, drafts short tailored cover notes for Claude to review | Score jobs, edit data/jobs.json, apply |
| Muse (builder) | Owns index.html and the look of the dashboard, keeps the repo tidy, adds a second opinion on leads | Edit data/jobs.json, change odds weights, apply |
| Owner | Signs in, clears bot checks, answers questions only he can answer, final say | |

If a tool cannot do something listed for it, it says so in inbox/notes.md and Claude covers it.

## The handoff (files in this repo are the only channel)
1. Scouts add leads to inbox/leads.json. Raw facts only: company, role, link, pay as posted, posted date, remote yes or no, one line on why it looks like a fit. No scores.
2. Claude verifies each lead is live, remote, open to New York, and states pay. Then scores it with the five factors in MUSE.md and adds it to data/jobs.json only if the odds clear the floor. Rejected leads get a one-line reason in inbox/rejected.md so scouts learn what to skip.
3. Muse changes only index.html and README. Claude reviews any change that touches how odds are computed.
4. Only one writer per file. data/jobs.json: Claude. index.html: Muse. inbox/leads.json: scouts, then Claude clears it.

## When blocked (priority order)
1. Try another way yourself first, such as a different source or the next-best job.
2. If a helper could unblock it, add an entry to inbox/blockers.md addressed to ChatGPT or Muse and move on to other work. Do not wait for the reply.
3. Only ask the owner for what only he can give: his own answers, a sign-in, a bot check, or an approval.
4. Never guess, never invent facts, never skip a safety rule to get past a block.

What each helper can be asked:
- ChatGPT: find the employer's own careers page for a posting, confirm a posting is still live, find a missing fact such as New York eligibility, or draft a cover note or an answer for Claude to check against the resume.
- Muse: fix or add something on the dashboard page.

Helpers answer in the entry's Reply line and mark it answered. Claude verifies every reply before using it.

## Daily rhythm
- Morning: scouts drop 3 to 5 leads.
- Midday: Claude verifies and scores, picks the highest-odds open job, and applies. Needs his Chrome open and signed in to Indeed.
- If a question needs his own answer, Claude stops and asks. The day's application waits.
- Evening: the dashboard shows Today 1 of 1.

## Weekly review (Sunday)
Claude counts applications, replies and interviews, then compares them with the odds we gave each job.
- Under 20 outcomes: change nothing. Too little data.
- 20 or more: if high-odds jobs are not getting more replies than low-odds ones, the weights are wrong. Adjust one weight at a time and log it in model.changeLog.
- Raise the floor on the first of each month (already scheduled in model.oddsFloor).

## Cover notes
ChatGPT drafts, Claude checks every claim against the resume. No invented facts or stories. No em dashes. Three to five sentences.

## Rules for everyone
- This repo is public. No emails, phone numbers, addresses or passwords.
- Keep AngelinaWatch and the Tinder analytics dashboard out of everything.
- Do not lower the odds floor to fit a job.
- Plain, short language.
