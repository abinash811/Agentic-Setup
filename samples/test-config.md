# Test setup used for the sample reports

These choices were made by Claude only to test the skills with dummy data. They are not your real settings.

- Sources: samples/daily_metrics.csv, samples/pull_requests.csv
- Metrics: signups, active users, support tickets (web and mobile)
- Needs attention: a metric that moves more than 10% against the same weekday last week (tickets: more than 25%); a pull request open more than 5 days
- Daily report day: Sunday 2026-10-25. Weekly digest: Monday 2026-10-19 to Sunday 2026-10-25, against 2026-10-12 to 2026-10-18
- Definitions: "signup" = one new account created; "active user" = daily count of users who did at least one action
- Delivery: none (shown in chat)
