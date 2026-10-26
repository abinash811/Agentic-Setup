---
name: daily-report
description: Prepare a short daily report of what changed since yesterday (metrics, pull requests, issues, tickets) and say what needs attention. Use when the user asks for a daily report, daily update or "what happened yesterday", or when it runs on a schedule.
---

# Daily Report

Goal: in under two minutes of reading, tell the user what changed, what looks wrong, and what needs their attention today. Assume the user may repeat this in a meeting where people will challenge it.

## Rules for every answer (do not skip)

### 1. Write in simple words
- Anyone should understand it. Short, everyday words. No jargon.
- If a technical term is unavoidable, explain it in plain words right there.
- Add a small example or analogy when it makes a point clearer.

### 2. Never assume. Ask first.
- Clear every doubt by asking, in simple words, before building the report.
- Ask **specific** questions, not open ones, and offer choices.
  - Bad: "What should be in the report?"
  - Good: "Should 'a bad day' for signups mean a drop of more than 10% against the same weekday last week (A) or against the 7-day average (B)?"
- Ask only what you need, in one short batch.
- Read `config.md` in this skill's folder first. Anything already saved there does not need asking again; just confirm it in one line ("Same sources and alert thresholds as last time, right?").
- **When running on a schedule and nobody can answer:** do not guess. Use only what is saved in `config.md`. Put anything unclear in a "Needs your answer" box at the top of the report, as specific questions.

Things to find out, then save to `config.md`:
- **Sources:** which files, repos, boards or dashboards to read. Name them exactly.
- **What to cover:** which metrics, which repos, which teams.
- **Definitions:** what each metric means. Also read the glossary in `../analyze-data/definitions.md` if it exists, and reuse those wordings.
- **What counts as "needs attention":** exact thresholds (for example "PR open more than 5 days", "tickets up more than 25% against last week's same day").
- **Which day to report on:** normally yesterday. Ask about weekends and holidays.
- **Where to send it** and in what form (chat reply, file, email, Slack, doc).

## How to build it

1. **Check the data first.** Row count, date range, missing values, duplicates, odd values. Fix or exclude what is clearly wrong, and say exactly what you did and how it changes the numbers. Never silently drop data.
2. **Compare fairly.** Compare yesterday to the same weekday last week, not just to the day before, because weekdays and weekends behave differently. Show both numbers and the group size ("324 signups vs 351").
3. **Doubt surprises first.** If a number looks too good, too bad or too neat, assume a data mistake until you have checked it (duplicates, missing days, a changed definition).
4. **One day is noisy.** Do not call a trend from one day. Say "one day, could be noise" and show the last 7 days beside it.
5. **Do not claim a cause** unless the data proves it. Say "goes together with" or "possible reason (a guess)".
6. **Self-check:** think of the toughest question someone could ask about each headline and make sure the answer is in the report or marked as unknown.

## How to write the report

Plain words. Bullet points and small tables. No charts unless the user asks.

1. **Needs your answer** (only if there is something). Specific questions you could not settle.
2. **The short version.** 2 to 3 lines: is today normal, and what is the one thing to look at.
3. **Needs attention.** Each item: what, how big (numbers and group size), how sure you are, and a suggested next step.
4. **Numbers at a glance.** A table: metric, yesterday, same day last week, change, last-7-days average.
5. **Work in progress.** Merged, opened, and stuck items (for example pull requests older than the agreed limit) with names or ids.
6. **Data notes.** Anything that was missing, duplicated, fixed or unchecked.
7. **Sources.** Exactly what was read and for what period.

Keep it short. If nothing needs attention, say so clearly and keep the rest brief.

## Do not
- Do not guess, fill gaps with made-up numbers, or present a guess as a fact.
- Do not hide bad news or messy data.
- Do not pad the report. Skip empty sections.
