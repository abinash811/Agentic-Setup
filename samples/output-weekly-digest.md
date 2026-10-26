# Weekly digest: 19 to 25 Oct 2026 vs 12 to 18 Oct (test run on dummy data)

## The week in 3 lines
- Support tickets jumped 46% and mobile signups fell 16%. Both started midweek.
- Web signups, active users and merged work stayed steady.
- Do next: find out what changed on Wed 21 Oct (tickets) and Thu 22 Oct (mobile signups).

## What changed and why
**1. Support tickets: 194 vs 133 (+46%).**
- Split: web 106 vs 79 (+34%), mobile 88 vs 54 (+63%). Both up, mobile more.
- Timing: Mon and Tue were normal (37 vs 43). Wed to Sun were 157 vs 90 (+74%). So the jump starts on Wednesday, not gradually.
- Normal range: the last 4 weeks were 127, 134, 133 and 194. This week is far outside the usual ups and downs.
- Stress tests: held when removing the biggest day, and when looking at web and mobile separately.
- Reason: **unknown (guess: something shipped on Wed 21 Oct).** I have no release or ticket-topic data. How sure: high that it is real, low on why.

**2. Mobile signups: 265 vs 315 (-16%).**
- Split: web 426 vs 425 (flat). So the whole drop is mobile.
- Timing: Mon to Wed 146 vs 153 (-5%, normal). Thu to Sun 119 vs 162 (-27%). The drop starts Thu 22 Oct.
- Normal range: the last 4 weeks of mobile signups were 301, 308, 315 and 265. This is the lowest by a clear margin.
- Stress tests: held after removing the duplicate row; held when comparing the same weekdays. It does depend on a duplicate fix: left in, the week would read 318 (+1%) and hide the drop.
- Reason: unknown. How sure: medium to high that it is real, low on why.

**3. Things that stayed steady**
- Total signups: 691 vs 740 (-7%), but all of this is the mobile drop.
- Active users per day: mobile 661 vs 651 (+2%); web 837 vs 874 (-4%), but last week's web figure is based on 6 days (17 Oct is missing), so the two are not fully comparable.
- Pull requests merged: 6 vs 7.

## Numbers at a glance
| Metric | This week | Last week | Change | 4-week values (oldest to newest) |
|---|---|---|---|---|
| Signups, all | 691 | 740 | -7% | 726, 750, 740, 691 |
| Signups, mobile | 265 | 315 | -16% | 301, 308, 315, 265 |
| Signups, web | 426 | 425 | 0% | 425, 442, 425, 426 |
| Support tickets | 194 | 133 | +46% | 127, 134, 133, 194 |
| PRs merged | 6 | 7 | -1 | not checked |

## Risks and stuck work
- 3 pull requests open more than 5 days: #11 (17 days), #4 (13), #23 (10). Owners not known from the data.
- If the ticket jump continues, support load stays about 1.5 times normal.

## Decisions or actions needed
1. Ask engineering what shipped on Wed 21 Oct and Thu 22 Oct.
2. Read a sample of this week's tickets to see what people are writing about.
3. Unblock or close the 3 stuck pull requests.

## Questions you may be asked
- *"Is the mobile drop real or a data problem?"* Real, as far as we can tell. One duplicate row would have hidden it; it is removed. Not checked: whether tracking on mobile changed.
- *"Is it just a bad week?"* Unlikely for tickets (the jump is far outside 4 weeks of history). Mobile signups are the lowest of 4 weeks, but 4 weeks is a short history, so say "unusual", not "proven".
- *"Did the release cause it?"* Unknown. The timing fits, but we have no release data. It is a guess.
- *"Why did total signups only fall 7%?"* Because web is flat and is about 60% of the total.
- *"How big are these groups?"* Mobile signups 265 vs 315; tickets 194 vs 133. Large enough that the changes are not a few people.

## What we could not check
Releases and deployments, ticket topics, mobile tracking changes, anything before 28 Sep.

## How we got here
Data: samples/daily_metrics.csv, 28 Sep to 25 Oct. One duplicate row (mobile, 20 Oct) removed. One missing value (web active users, 17 Oct) left out of averages. Weeks run Monday to Sunday, 7 days each. Definitions: signup = one new account; active user = daily count of users who did at least one action. Pull requests from samples/pull_requests.csv; "stuck" = open more than 5 days at 25 Oct.
