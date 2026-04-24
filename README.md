# skillspool-find-skill

An Agent Skill for searching and discovering AI Agent Skills from the [Skills Pool](https://skillspool.org) directory.

Use this skill when you need to **find new skills** from the ecosystem — not for recommending already-installed local skills (use [suggest-local-skills](https://github.com/qCanoe/suggest-local-skills-skill) for that).

## Features

- **One-call search**: Single API endpoint to find skills by keyword
- **Quality ranking**: Results sorted by relevance and community trust (GitHub stars)
- **Security guidance**: Built-in assessment checklist for evaluating skill safety
- **Removal instructions**: How to safely remove a skill if it's found to be unsafe

## When to use

- "Find me a skill for code review"
- "I need a skill that helps with X"
- "Search for agent skills online"
- After local skill search finds nothing suitable

## Quick start

### Option A: npx (recommended)

```bash
# Project-local
npx add-skill mechanicianwang/skillspool-find-skill

# User-wide
npx add-skill mechanicianwang/skillspool-find-skill -g
```

### Option B: Manual install

```bash
# Cursor
git clone https://github.com/mechanicianwang/skillspool-find-skill.git ~/.cursor/skills/skillspool-find-skill

# Claude Code
git clone https://github.com/mechanicianwang/skillspool-find-skill.git ~/.claude/skills/skillspool-find-skill
```

## Repository layout

```
skillspool-find-skill/
├── SKILL.md      # Full skill instructions: API, workflow, security, removal
├── README.md     # This file
└── LICENSE        # MIT
```

## How it works

1. Agent extracts keywords from user's request
2. Calls `GET https://skillspool.org/api/v1/skills/search?q=keywords&limit=10`
3. Evaluates results by relevance, stars, and safety signals
4. Recommends up to 5 best-matching skills with trust indicators
5. Helps user install their chosen skill

## License

MIT
