---
name: weekly-digest
description: Prepare a weekly digest of how the week went compared with the week before (wins, problems, trends, risks, decisions needed). Use when the user asks for a weekly report, weekly digest, week in review or weekly update for stakeholders, or when it runs on a schedule.
---

# Weekly Digest

Goal: explain how the week went, why, and what to do about it, so the user can share it and defend every line. Assume people will try to challenge it.

## Rules for every answer (do not skip)

### 1. Write in simple words
- Anyone should understand it. Short, everyday words. No jargon.
- If a technical term is unavoidable, explain it in plain words right there.
- Add a small example or analogy when it makes a point clearer.

### 2. Never assume. Ask first.
- Clear every doubt by asking, in simple words, before building the digest.
- Ask **specific** questions, not open ones, and offer choices.
  - Bad: "Who is this for?"
  - Good: "Is this for your team (A) or for leadership (B)? Leadership gets fewer details and more decisions."
- Ask only what you need, in one short batch.
- Read `config.md` in this skill's folder first. Anything already saved there does not need asking again; just confirm it in one line.
- **When running on a schedule and nobody can answer:** do not guess. Use only what is saved in `config.md`. Put anything unclear in a "Needs your answer" box at the top, as specific questions.

Things to find out, then save to `config.md`:
- **Audience and purpose:** who reads it and what they decide with it.
- **Sources and coverage:** exact files, repos, boards, dashboards.
- **Week definition:** Monday to Sunday, or something else. Which week to report on.
- **Definitions:** what each metric means. Save confirmed definitions in `config.md` so they stay the same every run.
- **Targets or goals** to compare against, if any.
- **What counts as a risk,** with exact thresholds.
- **Where to send it** and in what form.

### 3. Always start by narrowing it down and choosing sources
Questions come first, every time. Even if the request is broad ("how did the week go?"), do not start. A broad request gives a broad, useless digest.
- **Narrow it down in rounds.** Ask specific questions until you can say the task in one sentence and the user says yes. If the answers are still broad, ask again.
- **Ask about sources before touching anything.** Look at which tools, connectors and files are available in this session and list them by name: "I can see X, Y and Z. Want me to connect to or check any of these before I start? Which ones?" Never read from a tool without a yes. Saved sources in `config.md` still need a one-line confirm on interactive runs.
- **Two or more sources are fine.** When using several: say what each one gave you; check they match on period, definitions and IDs; if they disagree, show both numbers and ask which one is the source of truth (on a schedule, show both and flag it in "Needs your answer"). Never pick one silently.
- **Read only.** Never change anything in a connected tool unless the user asks.
- If no tools are connected, ask the user to paste or upload the data.

## How to build it

1. **Check the data first.** Row count, date range for both weeks, missing values, duplicates, odd values. Fix or exclude what is clearly wrong, say exactly what you did and how it changes the numbers. Never silently drop data. Make sure both weeks cover the same number of days.
2. **Compare like with like.** This week against last week, same length, same definitions, with the group size beside every percent ("-16%, 265 vs 315 signups").
3. **Split before you conclude.** Break each headline change down by group (platform, region, team). Say whether one group explains most of the change.
4. **Doubt surprises first.** If a number looks too good, too bad or too neat, assume a data mistake until checked.
5. **Stress-test the main findings.** Re-check with the biggest outliers removed, a different cut of days, and a slightly different definition. Report in plain words whether the finding held. If it flips, say so up front and lower your confidence.
6. **Separate signal from noise.** One week is a short time. Show the last 4 weeks beside the change and say whether the change is outside the normal ups and downs.
7. **Do not claim a cause** unless the data proves it. Label guesses as guesses. Look for other explanations (a release, a holiday, one big customer, a tracking change) and say which you checked.
8. **Look for evidence against your own story** and report it.
9. **Self-check:** list the 3 to 5 hardest questions someone could ask and make sure each is answered in the digest or marked as unknown.

## How to write the digest

Plain words. Bullet points and small tables. No charts unless the user asks.

1. **Needs your answer** (only if something is unsettled). Specific questions.
2. **The week in 3 lines.** What went well, what did not, what to do.
3. **What changed and why.** Per headline: the number, the comparison, the split by group, the likely reason (labelled as fact or guess), how sure you are and what the stress tests showed.
4. **Numbers at a glance.** A table: metric, this week, last week, change, 4-week average.
5. **Risks and stuck work.** What could hurt next week, with evidence and an owner if known.
6. **Decisions or actions needed.** One to three, specific.
7. **Questions you may be asked.** The hard questions from step 9, each with a short answer or "unknown, here is how to find out".
8. **What we could not check.** Gaps and assumptions.
9. **How we got here.** Sources, period, filters, definitions, fixes made to the data. Enough for someone to repeat it.

## Do not
- Do not guess, fill gaps with made-up numbers, or present a guess as a fact.
- Do not pick time windows or roundings that flatter the story.
- Do not hide bad news or messy data.
- Do not pad. Skip empty sections.
