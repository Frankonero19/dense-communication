# Dense Communication

AI agent skill that maximizes information density in LLM responses and reasoning.

## Principles

- **BLUF** — conclusion first
- **Orwell compression** — cut filler
- **Inverted pyramid** — order by importance
- **Meaning-ink ratio** — every token carries data
- **Feynman checks** — simplify to verify understanding

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Universal skill definition — works in any agent that supports the Agent Skills standard |
| `anti-patterns.md` | Kill list of filler, hedging, and structural anti-patterns |
| `claude-code/CLAUDE.md` | Always-on adaptation for Claude Code projects (drop into your repo) |

## Installation

### Option A: As a Skill (triggered by description matching)

The `SKILL.md` format is an open standard. Same file works across agents — just clone into the right directory.

```bash
# Claude Code
git clone https://github.com/Frankonero19/dense-communication.git ~/.claude/skills/dense-communication

# Cursor
git clone https://github.com/Frankonero19/dense-communication.git ~/.cursor/skills/dense-communication

# GitHub Copilot
git clone https://github.com/Frankonero19/dense-communication.git ~/.copilot/skills/dense-communication

# Gemini CLI
git clone https://github.com/Frankonero19/dense-communication.git ~/.gemini/skills/dense-communication
```

The agent loads the skill when your prompt matches the description. Works best for on-demand use.

### Option B: Always-on project instructions (Claude Code only)

Copy `claude-code/CLAUDE.md` into your project root or `~/.claude/CLAUDE.md` for global use. Claude Code loads it at every session start — no trigger needed. Best for enforcing the style on every response.

```bash
# Per-project (commit to repo)
cp claude-code/CLAUDE.md ./CLAUDE.md

# Global (all projects)
cp claude-code/CLAUDE.md ~/.claude/CLAUDE.md
```

### Option C: Per-project skill (any agent)

Clone into your project's agent config directory. Useful for team-wide enforcement via version control.

```bash
# Claude Code
cp -r . .claude/skills/dense-communication

# Cursor  
cp -r . .cursor/skills/dense-communication
```

## Which option to choose?

| Need | Option |
|------|--------|
| Style on every response, Claude Code | **B** — CLAUDE.md |
| Triggered when relevant, any agent | **A** — Skill |
| Shared with team via repo | **C** — Per-project skill |
