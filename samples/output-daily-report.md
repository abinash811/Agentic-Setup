# Daily report: Sunday 25 Oct 2026 (test run on dummy data)

## The short version
Mobile signups and support tickets both need a look. Tickets are far above normal and have been since Wednesday. Mobile signups dropped yesterday and have been low since Thursday. Active users are normal.

## Needs attention
1. **Support tickets are way up.** 23 tickets yesterday vs 10 on the previous Sunday (+130%). Sundays are small numbers, so one day alone could be noise. But the last 5 days (Wed to Sun) total 157 vs 90 for the same 5 days the week before (+74%). That is not noise. *How sure: high that it is real. Reason: unknown, a guess is a change that went live on Wednesday. Next step: ask engineering what shipped on Wed 21 Oct.*
2. **Mobile signups are down.** 23 yesterday vs 31 last Sunday (-26%). Small numbers for one day, so by itself not proof. Thursday to Sunday together: 119 vs 162 the week before (-27%). *How sure: medium to high. Web signups are flat (40 vs 41), so it looks mobile-only. Next step: check if anything changed in the mobile sign-up flow on Thu 22 Oct.*
3. **3 pull requests are stuck** (open more than 5 days): #11 (17 days), #4 (13 days), #23 (10 days). *Next step: ask the authors if they are blocked.*

## Numbers at a glance
| Metric | Yesterday | Same day last week | Change | Last 7 days, daily average |
|---|---|---|---|---|
| Signups (all) | 63 | 72 | -12% | 99 |
| Signups, mobile | 23 | 31 | -26% | 38 |
| Signups, web | 40 | 41 | -2% | 61 |
| Active users (all) | 1,275 | 1,261 | +1% | 1,498 |
| Support tickets | 23 | 10 | +130% | 28 |

## Work in progress
- Merged this week so far (Mon to Sun): 6. Last week: 7.
- Stuck: see item 3.

## Data notes
- **One duplicate row removed:** mobile on 20 Oct appeared twice (identical). Kept one. If left in, it would have added 53 extra signups to that week and hidden most of the mobile drop.
- **One missing value:** web active users on 17 Oct is blank. It is left out of averages; it does not affect yesterday's numbers.
- Sunday numbers are small, so percent changes look big. Treat one-day changes with care.

## Sources
samples/daily_metrics.csv (28 days, 28 Sep to 25 Oct) and samples/pull_requests.csv (30 rows). Test thresholds are in samples/test-config.md.
