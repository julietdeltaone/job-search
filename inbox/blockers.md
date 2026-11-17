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

(none yet)
