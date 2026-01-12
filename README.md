# Flow-Power-Automation

A tiny automation that saves a surprising amount of admin time.

## The story (aka: why this exists)
Every pay period, the same thing happens:
- Everyone is busy.
- Deadlines sneak up.
- Someone submits late.
- Then someone else has to chase people down with reminder emails.

I built a Power Automate setup that does two things reliably:
1) **Reminds people before the deadline**
2) **Labels late submissions automatically**

No drama. No guessing. Just consistent process.

## What this solves
✅ Fewer late timesheets  
✅ Less manual emailing / follow-ups  
✅ Clear late tracking (consistent deadline rule)  
✅ Minimal term-by-term maintenance (update deadlines once)

## How it works (high level)
### Flow 1 — Submission + Late Labeling
**Trigger:** Microsoft Forms submission  
**Steps:**
1. Read pay period selected in the form
2. Look up the deadline in a SharePoint PayPeriods list
3. Compare submission time vs deadline
4. Save the uploaded file as:
   - `<filename>` or
   - `LATE_<filename>`

### Flow 2 — Reminder Emails (planned / next)
**Trigger:** Scheduled (daily, includes weekends)  
**Sends:**
- Reminder #1: **2 days before** deadline  
- Reminder #2: **on** the deadline day  

Recipients are managed via **one email group / distribution list** (so the flow doesn’t need a giant list of addresses).

## What changes each term?
Just update SharePoint:
- PayPeriod name
- Deadline date/time

That’s it.

## Setup notes
This repo includes exported Power Automate flows and lightweight documentation.
> ⚠️ Please don’t commit real student/staff data, internal links, or personal emails.

## Roadmap
- [ ] Add Flow 2 (reminders)
- [ ] Optional Phase 2: remind only people who haven’t submitted (requires submission logging + roster)
- [ ] Optional: weekly summary to admin (late counts + missing submissions)

## Tech
- Microsoft Forms
- Power Automate
- SharePoint list (PayPeriods)
- Outlook email (distribution list)

<img width="491" height="731" alt="image" src="https://github.com/user-attachments/assets/0e269117-ad20-4bee-b09a-e696ab3c6b44" />

