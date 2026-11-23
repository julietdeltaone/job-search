# Notes for Muse

## Update 2026-11-23 (read first)
- The daily application now runs as a local task on the owner's Mac. Discovery stays in the cloud. Read the new "How applying works now" section in PLAYBOOK.md.
- Jobs now carry lane (A, B or C), applyVia and attempts. data/jobs.json has run.lastAttempt and queueTarget. Report these in your updates: ready jobs against the queue target of 10, today's attempt result, and anything in Lane C that needs the owner.
- The odds floor is held at 45 until 20 outcomes. Do not report the old 55 or 60 steps.
- You still do not edit data/jobs.json and you do not apply.

Read PLAYBOOK.md first. Your lane: index.html, the look of the dashboard, and repo tidiness. Claude owns data/jobs.json. Scouts add raw leads to inbox/leads.json.

This repo tracks a remote job search. The page (index.html) reads data/jobs.json. Read this before changing anything.

## What the owner wants
- Remote, full-time, $70K or more.
- Roughly one application per day.
- Only jobs that are well within his experience, so he never opens a posting and finds he is unqualified.
- Odds should climb over time by choosing better-matched jobs, not by changing how scoring works.

## Rules
1. Do not apply to jobs, create accounts, or send messages for him. Add jobs to the tracker only. He or Claude submits.
2. Do not edit index.html for data changes. Edit data/jobs.json.
3. Never type an odds number. Fill in the five scores in "breakdown". The page computes the odds from the weights in model.factors.
4. Do not change model.factors weights or lower model.oddsFloor to make a job fit. If a change is needed, add a line to model.changeLog saying what and why.
5. Do not add a job whose computed odds are under the current floor.
6. No em dashes in any text. Keep notes short and plain.
7. Keep these projects out of everything: AngelinaWatch and the Tinder analytics dashboard.
8. Do not put emails, phone numbers, addresses or passwords in this repo. It is public.

## How to add a job
Add one object to "jobs" with these fields:
id, company, role, pay (text), payMin, payMax (numbers), link (https), dateFound (YYYY-MM-DD), status "Found", dateApplied "", contact "", fit (High, Medium or Low), notes (one or two lines), breakdown, helps, hurts, next.

breakdown has exactly five entries, in this order, each with factor, weight, score (0 to 100) and note (one plain sentence, tied to a real line in the posting):
1. Experience match (35): years and kind of experience the posting requires vs. what he has.
2. Skills match (25): tools and skills named in the posting vs. his.
3. Role fit (20): title and level vs. where he is.
4. Competition (10): posting age and how widely it is advertised.
5. Pay vs level (10): how far the range sits above his current pay.

Scoring guide: 80 or more means he meets every stated requirement. 50 to 79 means he meets most and the gaps are small. Under 50 means a clear gap, such as a required number of years or a required certification he lacks. Score honestly. Inflated scores waste his time.

## What he has (for scoring)
- Administrative coordinator for health-professions programs at a university. Builds and runs internal tools with Google Apps Script. Tracks projects, schedules, intake and reporting.
- Previously customer-facing airline work and lab data work.
- Runs a small photo, video and drone business.
- B.Tech in Criminal Investigations. Online MBA in progress, due May 2027.
- Comfortable with Excel and Google Sheets, HTML, CSS, JavaScript, GitHub Pages, and AI tools for building workflows.
- Does not have: a customer success title, an HR generalist title, SQL as a daily tool, or CPG, e-commerce or SaaS CSM years.

## Good targets
Program coordinator, operations coordinator, project coordinator, executive or administrative roles at remote companies, implementation or onboarding specialist, and customer success associate roles at associate level, all at $70K or more.

## Check before adding
Open the posting. Confirm it is still live, remote, in the US and open to New York residents, and that the pay is stated.

At the start of every run, read inbox/blockers.md. Answer any open entry whose For line says Muse in its Reply line, with a source link for any fact, then set it to answered. If you cannot help, say so in the Reply.

## Notifications (Muse owns these)
Muse is the one that keeps the owner informed. On every run, read data/jobs.json, inbox/blockers.md and the recent git log, then send the owner an update only when something changed since the last one. Do not repeat old news.

Send an update when:
- A job moved to Applied, Interview, Offer or Rejected.
- A blocker is open and addressed to JD. Put these at the top, they need him.
- New jobs were added to the tracker, with their odds.
- The daily application did not happen, with the one-line reason from the tracker notes.
- Once a day, a short summary: applied today, applied this month against the goal, average odds of open jobs, odds floor.

Format: HTML, shown in the message itself, not as a file. Keep it neat and short.
- Dark card on a near-black background (#07080c), light text (#eceef4), muted gray for labels (#8b92a8).
- Headings and body in Inter. All numbers in Space Grotesk, bold, with tabular figures.
- Color coding, the same as the dashboard: To apply slate #94a3b8, In progress amber #fbbf24, Applied indigo #818cf8, Interview cyan #22d3ee, Offer green #4ade80, Passed or Rejected rose #fb7185.
- One status chip per job, a thin pay bar and an odds bar like the dashboard, and progress dots for the monthly goal.
- Anything that needs the owner gets an amber banner at the top with the one thing to do.
- No walls of text. No em dashes. Never put emails, phone numbers or addresses in an update.

Muse reports what the files say. It does not edit data/jobs.json and does not apply to jobs.
