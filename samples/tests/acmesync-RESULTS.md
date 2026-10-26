# Test: product-research on made-up product "AcmeSync" (inputs in samples/tests/acmesync/)

Tester also wrote the skill, so this is a friendly test. Sources were supplied as files, so the "ask before searching the web" step was not exercised.

**First turn (must ask before researching):** Is this to choose a tool (A), check a vendor claim (B), or learn how it works (C)? What matters most: cost, real-time speed, security, scale, leaving easily? How many connections and records do you expect? Do you need EU data storage? I plan to read the 5 files you gave me; anything else to include?

**Output (assuming: choosing a tool for ~15 connections, security and real-time matter most):**

**The short version.** AcmeSync syncs data between apps on a schedule, and on its paid plans the fastest sync is every 60 seconds. It is not "real-time" on most plans. Biggest limits: 50,000 records per run, US-only data storage, CSV-only export, and no SOC 2 Type II yet.

**Marketing vs evidence (the main finding)**
| Marketing says | Docs and users say | Tag |
|---|---|---|
| "Unlimited" sync | Connections: 2 (Free), 10 (Pro), unlimited only on Business ($199/mo). 1,000 or 10,000 API requests per hour. 50,000 records per run. | Documented (A, Aug 2026) |
| "Real-time" | Every 60 seconds on Pro and Business. True real-time (webhooks) is beta, Business only. | Documented (A) |
| "SOC 2 compliant" | Type I report on request; Type II "in progress". Type I checks that controls are designed; Type II checks they worked over time. | Documented (A, Feb 2026, may be outdated) |
| "99.99% uptime" | No SLA or status history found. Users report sync stopping silently for 2 days. | Claimed only; users contradict |
| "200+ apps" | Not checked, no connector list provided. | Unknown |
| "Loved by 10,000 teams" | No source. | Claimed only |
| "Export anywhere" | CSV only, no bulk history export. | Documented. Contradicted |

**Limits that bite later.** 15 connections needs Pro (10) at minimum, so Business at $199/mo (A). Failures at the 50,000-record cap give vague errors (B, 6 replies). No alert when sync stops (B, several confirm, staff acknowledged). Support slow on billing (B, 1 thread: weak evidence). Data in one US region, EU on the roadmap with no date (A): a roadmap item, not a feature.

**How sure we are.** Medium. Docs are recent (Aug 2026) but the changelog's last entry is March 2025, so it is unclear whether it is still actively updated. All user reports come from one forum.

**Source quality.** The article (C) is promotion: it carries an affiliate link and says "we earn a commission". It was not used as evidence for any claim. Marketing page (C, undated) used only to list what is being claimed.

**Could not verify, and what to do**
- Uptime: ask the vendor for the status page and 12-month incident history.
- Silent failures: ask whether alerts exist now and which plan includes them.
- Connector list: check that your 15 apps are on it.
- Record volume: test with a sample close to your real size before you pay.

**Hardest questions you may get.** "Is it really real-time?" (No, 60 seconds, or beta webhooks on Business.) "Is it secure?" (Type I only, Type II pending.) "Is this still maintained?" (Docs updated Aug 2026, changelog stale since Mar 2025, unclear.)

**Technical corner.** *Webhook:* the app tells the other app the moment something changes, instead of checking every minute. *Rate limit:* a cap on how many requests you can make per hour. *SOC 2 Type I vs II:* a design check versus a check that controls worked over months.

| Check | Result |
|---|---|
| Asks questions first | Pass |
| "Unlimited" vs plan limits | Pass |
| "Real-time" defined in numbers | Pass |
| SOC 2 Type I vs "in progress" Type II | Pass |
| 99.99% uptime with no evidence | Pass: "claimed only", users contradict |
| Affiliate article not used as evidence | Pass |
| Stale changelog flagged | Pass |
| Roadmap not treated as shipped (EU) | Pass |
| Gaps left as "unknown" (connector list) | Pass |
| Source grades and dates on facts | Pass |
**Result: 10 of 10. Not tested:** the live web search path, open-source library and API checks, and article checks beyond the one promo piece.
