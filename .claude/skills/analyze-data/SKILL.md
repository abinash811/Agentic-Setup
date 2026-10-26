---
name: analyze-data
description: Analyze any kind of data (numbers, tables, survey answers, text such as reviews, tickets, chats, emails) and give insights that hold up when presented to a skeptical audience. Use when the user shares data, a file, a query result or text and wants to understand it, find patterns, do intent/sentiment/theme analysis, or prepare findings to present.
---

# Analyze Data

Goal: turn data into insights nobody can poke holes in. Assume the user will present this to people who will try to challenge every number and every claim.

## Rules for every answer (do not skip)

### 1. Write in simple words
- Anyone should understand the output. Short, everyday words. No jargon.
- If a technical term is unavoidable, explain it in plain words right there.
- Add a small example or analogy when it makes a point clearer.

### 2. Never assume. Ask first.
- Before doing any analysis, clear up every doubt by asking the user.
- Ask in simple words. Ask **specific** questions, not open ones, so the user can answer fast and the result is better.
  - Bad: "What do you want to know?"
  - Good: "Do you want to know why signups dropped last week, or which region dropped the most?"
- Offer choices when you can: "Is 'active user' someone who logged in this month (A) or did an action this month (B)?"
- Ask only what you need, in one short batch (usually 3 to 6 questions). Do not start the analysis until they answer.
- If the user says "just go ahead", state each assumption out loud at the top of your answer and mark it as an assumption.

Things to ask about when they are not already clear:
- **The decision:** What will this be used for? Who will see it? What will they decide?
- **The question:** The one thing the user most wants to know.
- **The data:** Where did it come from? What period does it cover? Is anything missing or filtered out? How was it collected?
- **Definitions:** What exactly counts as each metric, group or category?
- **Comparison:** Compared to what (last week, last year, another group, a target)?
- **Audience:** Who will challenge it, and what will they likely push on?

## How to analyze

1. **Restate the question** in one sentence and get the user to confirm it.
2. **Check the data before using it.** Report: row count, date range, missing values, duplicates, odd or impossible values, and anything that looks wrong. Say what you did about each (removed, kept, fixed) and how it changes the result. Never silently drop data.
3. **Use the simplest method that answers the question:** totals, averages, medians, percentages, change over time, comparison between groups. Use advanced methods only if the simple ones cannot answer it, and explain them in plain words.
4. **For text data** (reviews, tickets, chats, emails, survey comments):
   - Agree on the categories first (intents, themes, sentiment) with the user. Ask for their list, or propose one and get approval.
   - Define each category in one line, with example texts for each.
   - Label every item. Show how many were unclear or fit more than one category; do not force them in.
   - Read a sample by hand and show real quotes as evidence for each category.
   - Report counts and percentages, and say how many texts were analyzed.
5. **Make it bulletproof.** For every claim:
   - Show the number and the size of the group it comes from (for example "18% of 240 users", not just "18%").
   - Say if the group is too small to trust.
   - Do not say one thing caused another unless the data proves it. Say "goes together with" or "likely because", and label it as a guess.
   - Look for other explanations (seasonality, one big customer, a launch, a data glitch, a change in how things were counted). Say which you checked and which you could not.
   - Look for evidence that goes against your own conclusion, and report it.
   - Watch for common traps: averages hiding a split, one outlier driving the result, comparing unlike groups, picking a convenient time window, small samples, and survivors only (missing the people who left).
6. **Self-check before answering.** Imagine the toughest person in the room. List the 3 to 5 hardest questions they would ask and make sure the answer to each is in your output or clearly flagged as unknown.

## How to write the output

Use this order, in plain words. Keep it short; skip a part only if it truly does not apply.

1. **The answer.** One or two sentences with the key number.
2. **Why / what is behind it.** The evidence, with real numbers, group sizes and examples (quotes for text data).
3. **How sure we are.** High, medium or low, and why. What would change the answer.
4. **What we could not check.** Gaps, assumptions, missing data.
5. **Questions you may be asked.** The hard questions from step 6, each with a short answer or "we don't know yet, here is how to find out".
6. **What to do next.** One to three concrete actions.
7. **How we got here.** Source, filters, definitions, method. Enough that someone else could repeat it and get the same result.

Add a small table or one chart only if it shows the point faster than words. Every chart needs a plain title that states the takeaway, labeled axes, and the group size.

## Do not
- Do not guess or fill gaps with made-up numbers.
- Do not round or choose time windows in a way that flatters the story.
- Do not present a guess as a fact.
- Do not hide bad news or messy data.
- Do not start before the user's doubts are cleared.
