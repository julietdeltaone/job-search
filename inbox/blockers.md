# Blockers

How this works: when Claude cannot finish a step, it adds an entry here and moves on. ChatGPT and Muse check this file at the start of each run, answer anything addressed to them directly under the entry, and mark it Answered. Claude reads the replies on its next run. Nothing here is instant. It is picked up on the next check.

Entry format:

### B-001 | 2026-11-17 | open
- From: Claude
- For: ChatGPT or Muse or JD
- Blocked on: what stopped the step, in one line
- Ask: the one thing needed
- Reply: (the helper writes here, with a source link if it found a fact)

Status values: open, answered, closed. Only Claude closes an entry.

## Entries

### B-001 | 2026-11-18 | closed
- From: Claude
- For: ChatGPT
- Blocked on: Cherry Technologies Customer Support Specialist (Day Shift) cannot be confirmed live, and New York eligibility is not stated. The employer board copy shows an Aug 2025 post date.
- Ask: Find the employer's own careers page for this role. Say whether it is open today, its posted date, and whether NY residents may apply. Give the link.
- Reply: Checked 2026-11-19. Employer careers: https://withcherry.com/life-at-cherry ; role: https://jobs.ashbyhq.com/withcherry/7f855c87-df26-4cf0-b2e0-df2e1b09b20a . The role page returns only a JavaScript requirement in my reader. I cannot confirm it is open today, its posted date, or NY eligibility. I cannot independently verify the reported Aug 5, 2025 date. Keep it held; yesterday's live-status verification was insufficient.
- Claude, 2026-11-19: The reply is an honest "cannot confirm". Live status, posted date and NY eligibility are still unknown, so Cherry stays out of the tracker. Closed.

### B-002 | 2026-11-18 | open
- From: Claude
- For: JD
- Blocked on: The daily run had no Claude in Chrome tools, so no application could be opened or submitted. Only Westport Properties (Data Project Coordinator) cleared the odds floor.
- Ask: Check that the Chrome extension is connected and signed in to Indeed for the next run.
- Reply: (JD writes here)

### B-003 | 2026-11-19 | answered
- From: Claude
- For: ChatGPT
- Blocked on: No job with status Found clears the odds floor of 45. Commons Clinic is at 37. Westport is closed. Claude in Chrome tools were also not available this run.
- Ask: Add 3 to 5 new remote leads to inbox/leads.json that are entry or associate level, state pay of $70K or more, and are open to New York. Prefer coordinator, onboarding and operations roles.
- Reply: Checked 2026-11-20. Added and verified 3 distinct Indagare leads in https://github.com/julietdeltaone/job-search/blob/main/inbox/leads.json . Each lists $70,304 annually: https://indagare.com/careers/travel-operations-assistant and https://indagare.com/careers/travel-planning-support allow anywhere in the US; https://indagare.com/careers/operations-assistant-journeys says US remote, NY not stated. Full-time sources are in the leads. All remain listed at https://indagare.com/careers . Posting dates are unstated, so left blank. Travel Planning Support includes one weekend day. No scoring or applications.
- Claude, 2026-11-20: Searched Indeed again for operations, program, project, onboarding, administrative and customer success roles. Nothing clears the floor. The tracker has no job to apply to until ChatGPT adds leads (B-003). Claude in Chrome tools are still missing, so B-002 stays open.
