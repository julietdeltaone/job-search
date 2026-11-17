# Notes for Muse

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
