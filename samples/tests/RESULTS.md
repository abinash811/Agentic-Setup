# Test results: 4 new skills on dummy inputs (2026-10-26)

Method: each skill's steps were followed by hand on a small made-up input with traps. The tester (Claude) also wrote the skills, so this is a friendly test. A fresh session or a real input may find more. Nothing here is a test on real work.

## meeting-notes — input: `meeting-transcript.txt`

**First turn (skill must ask before writing):** Is this a recap (A), full minutes (B) or actions only (C)? Please confirm full names of attendees (transcript has "Jon" and "John"). Who reads the notes? The transcript mentions a colleague's performance review: include (A) or leave out (B)? Do you have last week's open actions?

**Output (run with defaults: recap, sensitive left out):**

*Short version.* Weekly product sync. Launch delay to 15 Nov was proposed but is not settled because legal may need until 22 Nov. Churn figure needs checking. Four actions, one carried over.

*Decisions.* None final. **Tentative:** delay launch to 15 Nov (proposed by Meera, Priya said "we agreed", Ravi said it depends on legal). Marked as *not settled*.

*Actions*
| Action | Owner | Due |
|---|---|---|
| Send revised pricing to legal | Priya | Friday (date not stated; if this meeting was Tue 21 Oct, that is Fri 24 Oct. Check) |
| Check the churn figure (4.2% vs 2.4%) | Priya | not stated |
| Share survey results (carried over from last week, overdue) | Ravi | Wednesday |
| Talk to support about refund complaints | "John" in transcript (attendee list says Jon. Check) | not stated |

*Suggested, nobody committed:* update the dashboard to match finance numbers (no owner); look at the onboarding emails (Jon said "should", no owner or date).

*Open questions.* Will legal need until 22 Nov? Which churn number is right, 4.2% or 2.4%?

*Needs confirming.* Owner for the dashboard update. Owner and date for onboarding emails. Which of Jon or John. Date for "Friday". Date for the refund-complaints action. The final launch date after legal replies.

*Left out on purpose.* One comment about a colleague's performance (sensitive). One opinion about a competitor (opinion, not a decision).

**Checks**
| Trap | Result |
|---|---|
| Conflicting numbers 4.2 vs 2.4 | Pass: flagged, not "fixed" |
| "We agreed" but conditional on legal | Pass: shown as tentative, not a decision |
| "Someone needs to update the dashboard" | Pass: not turned into an action |
| "We should look at onboarding emails" | Pass: suggestion only |
| Jon vs John | Pass: flagged |
| Sensitive comment about a person | Pass: left out, and said so |
| Opinion about competitor | Pass: left out |
| Carried-over action | Pass: shown as overdue with new date |
| "Friday" | Pass: date shown as derived and to be checked |
**Result: 9 of 9.** No skill change needed.

## decision-memo — input: `decision-brief.txt`

**First turn (skill must ask before drafting):** Are we deciding build vs buy (A), or whether to act at all (B)? Who makes the final call? Is "do nothing" an option, and is there a smaller version, like a 1-year contract or a pilot? What matters most (rank): speed, total cost, fit for your custom metrics, risk, effort? Has anyone confirmed VendorX handles your custom metrics?

**Output (run in "just go ahead" mode, assumptions listed at top):**

*Assumptions (mine, please confirm):* final call is the user's; "CEO likes it" is not treated as a criterion; hourly cost of staff time is unknown, so not valued.

*Recommendation.* Do **not** sign the 3-year contract yet. First run a 2-week check on whether VendorX handles the custom metrics, or ask for a 1-year term. Decide by end of month.

*Why.* The brief says buying is cheaper. It is not, on the numbers given: $40k × 3 years = **$120k**, not $90k; build is about $90k. Buy is faster (2 weeks vs 4 months) but costs about $30k more over 3 years, before any extra costs. The biggest risk is a claim nobody has checked: the data team says VendorX cannot handle custom metrics.

*Options.* (1) Build: about $90k, 4 months, ongoing cost "small" (not quantified). (2) Buy 3-year: $120k, 2 weeks setup, locked in. (3) Buy 1-year or pilot (smaller version; price unknown, ask VendorX). (4) Do nothing: about 10 hours a week of manual work (about 520 hours a year; cost depends on hourly rate, unknown).

*Door.* A 3-year contract is close to a one-way door. A pilot is a two-way door.

*What we need to believe.* VendorX handles the custom metrics (unchecked, *unknown*). Build really costs about $90k (3 people × 4 months = 12 person-months, about $7.5k each. Check). Ongoing build cost is small (*unknown*).

*What would change my mind.* If VendorX cannot do the custom metrics, build wins. If a 1-year price is near $40k, buy wins.

*Tripwires.* If the build passes 5 months, or VendorX's first month shows missing metrics, stop and reassess.

*Not checked.* Ongoing build cost, VendorX 1-year price, hourly cost of manual work.

**Checks**
| Trap | Result |
|---|---|
| Only two options, "do nothing" buried at the end | Pass: do nothing and a smaller version added as options |
| Arithmetic ($40k × 3 ≠ $90k) | Pass: caught, with the corrected total |
| Criteria bent toward a favourite ("CEO happiness") | Pass: not used; asked for ranked criteria |
| Unchecked claim from data team | Pass: top "need to believe", with a cheap test |
| Lock-in | Pass: one-way vs two-way door |
| Invented numbers | Pass: hourly cost left as unknown |
**Result: 6 of 6.** No skill change needed.

## customer-voice — input: `reviews.csv` (75 items)

**First turn (skill must ask before labelling):** What is the decision: why people leave (A), what features to build (B), or what annoys them now (C)? Who writes these (all customers, or only people who contact support)? Is there a category list, or should I propose one? May emails appear in the output? Label all 75 or a sample?

**Data checks reported.** 75 items, 35 people, 1 to 25 Oct. **18 Oct has 16 items, the median day has 3** (possible incident). One person posted the same billing complaint 8 times. The user column holds email addresses (personal data): removed from all output.

**Labelling.** Rules written from reading the text; labels saved to `labels.csv`; counts made by script. Graded afterwards against hidden answers: **74 of 75 correct** (the one "miss" was a bug in my test data, not in the labelling). The real miss: *"Great, another crash. Love waiting 5 minutes."* was labelled praise because of the word "love". It is sarcasm about slowness.

**Result by count (items):** login 22, billing 19, export 10, slow 9 (of 75).
| Stress test | Ranking |
|---|---|
| All data | login 22, billing 19, export 10, slow 9 |
| Without 18 Oct | **billing 18**, slow 9, export 9, **login 8** |
| Without the repeat poster | login 22, billing 11, export 10, slow 9 |
| Without both | billing 10, slow 9, export 9, login 8 |

**What the skill must say:** "Login looks like the top problem, but 14 of its 22 items came on one day, 18 Oct, which looks like an outage. Without that day, login is the *smallest* of the four. Billing is first in the other cuts, but after removing one repeat poster the top four are close (8 to 10), so the ranking beyond 'billing first' is not reliable."

**Checks**
| Trap | Result |
|---|---|
| Outage-day spike | Pass: found, and the ranking flip reported |
| One person posting 8 times | **Partial:** found, but the skill did not say to count *people* as well as items. **Fixed in the skill.** |
| Emails in data | Pass: flagged, removed |
| Sarcasm | **Fail:** labelled praise. **Fixed in the skill:** read all positive-looking items that mention problem words, and report how many were checked. |
| French review, one-word comments | **Partial:** went to "other", not reported. **Fixed in the skill:** report language and unreadable counts. |
| Counting by script, n of N | Pass |
**Result: 3 pass, 2 partial, 1 fail. Skill updated (see git log), then re-checked below.**

## skill-builder — input: the vague request "make me a skill for sales"

**First turn (must ask, must not write files):**
1. What exactly is the job: prepping for a call (A), writing follow-ups (B), tracking the pipeline (C), or something else?
2. What would a **great** result look like? Can you share a real example?
3. What do beginners get wrong on this job, and what must never happen (for example, never email a customer)?
4. What do the best people in sales do that others skip?
5. What data does it read (CRM, email, notes), and should it be read only?

Then (after answers): name, trigger words, output, and **three test requests** (one vague, one with traps, one where the right answer is "I don't know"), confirmed with the user before any file is written.

**Checks**
| Behaviour | Result |
|---|---|
| Asks before writing | Pass |
| Asks for a great and a bad example | Pass |
| Writes tests before the skill | Pass (in the plan) |
| Checks overlap with existing skills | Pass: would note overlap with `meeting-notes` and `decision-memo` if relevant |
| Limited to a short question batch | Pass (5) |
**Result: 5 of 5 on the first turn.** **Not tested:** the full build loop (writing a skill, running its tests, iterating). That needs a real example job from you.

## Re-check after the customer-voice fix
- Sarcasm: the new rule makes the skill read every "positive" item that also has a problem word. That finds exactly 1 item, *"Great, another crash..."*, which is then relabelled slow / negative. **Now passes.**
- People vs items: login 22 items from 22 people-or-fewer is reported both ways (see script output in the chat); billing's 19 items include 8 from one person. **Now passes.**
- Foreign-language and one-word items: now listed and counted ("ok", "Used it once", 1 French item). **Now passes.**

## Overall
| Skill | First-turn questions | Traps caught | Changed after test |
|---|---|---|---|
| meeting-notes | yes | 9 of 9 | no |
| decision-memo | yes | 6 of 6 | no |
| customer-voice | yes | 3 pass, 2 partial, 1 fail, then fixed | yes |
| skill-builder | yes | 5 of 5 (first turn only) | no |

Not tested: real inputs, the full skill-builder build loop, and how a fresh session (not the author) follows the skills.
