# claude-config

Global Claude Code preferences and standards. This repo ensures consistent working style and best practices across all projects.

## Setup

Clone this repo and symlink or copy to `~/.claude/`:

```bash
# Clone the repo
git clone https://github.com/<username>/claude-config.git ~/repos/claude-config

# Option 1: Symlink (recommended, stays up-to-date with git)
ln -s ~/repos/claude-config/CLAUDE.md ~/.claude/CLAUDE.md

# Option 2: Copy (if symlink isn't possible)
cp ~/repos/claude-config/CLAUDE.md ~/.claude/CLAUDE.md
```

**On new machines**: Clone this repo and create the symlink, then Claude will auto-load your preferences in any project.

## Contents

- **CLAUDE.md** — Global working style, git workflow, security standards, code patterns, and best practices

## What's Included

- ✅ Communication and output preferences
- ✅ Git workflow for code changes (type check → test → PR → review)
- ✅ Security standards (never commit secrets, credentials, personal IDs)
- ✅ Code style patterns (React, TypeScript, API, database)
- ✅ Memory and context persistence
- ✅ Task management approach
- ✅ External tools and resources

## What's NOT Included

- Project-specific architecture or decisions
- Personal identifiers or sensitive information
- Credentials or API keys
- Infrastructure details

Project-specific context lives in each repo's `CLAUDE.md` file.

## Updating

Edit `CLAUDE.md` in this repo, commit, and push. Since most projects symlink to it, changes auto-propagate.

---

**Purpose**: Persistent Claude Code preferences across all machines and projects.
