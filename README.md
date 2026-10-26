# Agentic-Setup

Skills that automate analysis and reporting. Each skill is one self-contained folder in `skills/`: it needs nothing else, and it remembers your answers in its own `config.md`.

Skills: `analyze-data`, `daily-report`, `weekly-digest`.

## Use them anywhere

**Option 1: install as a plugin (any project or session, shareable)**
```
/plugin marketplace add abinash811/agentic-setup
/plugin install pm-skills@agentic-setup
```

**Option 2: copy one skill by hand**
Copy a folder from `skills/` into `~/.claude/skills/` (all your projects on that machine) or into `<project>/.claude/skills/` (one project).

## How every skill behaves
- Writes in simple words anyone can follow.
- Never assumes. Asks specific questions first and narrows broad requests down.
- Asks before connecting to or reading any tool; can combine two or more sources.
- Checks data first, tests its own conclusions, and prepares for tough questions.

`samples/` holds dummy data and example outputs for testing.
