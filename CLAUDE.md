# Claude Global Configuration

This file contains reusable preferences and standards for Claude Code across all projects.

## Working Style

- **Communication**: Direct, action-oriented — skip preamble, lead with the decision or action
- **Output**: Concise responses focused on progress and blockers
- **Tool usage**: Prefer dedicated tools (Read, Edit, Glob, Grep) over Bash for file operations
- **Complexity**: Avoid over-engineering; solve only what's asked

## Git Workflow (Code Changes Only)

All code changes follow this workflow. Documentation/config changes may commit directly.

1. **Finalize code changes** — Complete all edits
2. **Run type checks** — Validate TypeScript/JSX (e.g., `npm run type-check`)
3. **Run tests** — Execute test suite (e.g., `npm test`)
4. **Verify tests pass** — Confirm all tests green before proceeding
5. **Create PR to main** — Push feature branch, open PR against main
6. **Add reviewers** — Request review before merge

**Why**: Catches bugs early, ensures quality gates, enables feedback.

## Security Standards

**Never commit**:
- API keys, tokens, or credentials
- Personal identifiers (emails, phone numbers, names)
- Infrastructure details (URLs, IPs, deployment paths)
- Webhook secrets or signing keys
- Database credentials or connection strings

**Always**:
- Use `.env.local` and `.env.local.example` for sensitive config
- Ensure `.gitignore` excludes sensitive files
- Use placeholders in documentation (`YOUR_API_KEY_HERE`, not real values)
- Review `.gitignore` before commits

## Code Style & Patterns

**General**:
- Simple, focused solutions over premature abstraction
- Trust internal code and framework guarantees
- Only validate at system boundaries (user input, external APIs)
- Prefer explicit over implicit; fail gracefully
- Don't add features/refactoring beyond what's requested

**TypeScript/JavaScript**:
- Use strict typing; leverage TypeScript
- ESLint/Prettier for formatting consistency
- Clear variable names; self-documenting code
- Comments only where logic isn't self-evident

**React**:
- Server components by default (if available in framework)
- Client components only for interactivity/state
- Proper error boundaries
- Accessible markup (semantic HTML, ARIA where needed)

**API Design**:
- RESTful endpoints with clear semantics
- Proper HTTP status codes
- Comprehensive error responses
- Request/response validation

**Database**:
- Prefer parameterized queries (prevent SQL injection)
- Use ORM/query builder when available
- Row-level security for multi-tenant systems
- Index frequently-queried columns

## Memory & Context Persistence

**Local memory** (per-project): `/Users/amarkulkarni/.claude/projects/<project>/memory/`
- Auto-loads each Claude session in that project
- Stores architecture, decisions, learnings
- Not committed to git

**Global CLAUDE.md**: Lives in `~/.claude/CLAUDE.md`
- Auto-loads for all Claude sessions
- Contains reusable preferences and standards
- Maintained in a personal `claude-config` repo

## Task Management

- Use TaskCreate for multi-step work within a session
- Mark tasks in_progress when starting, completed when done
- For complex features, use EnterPlanMode to align on approach before building

## External Tools & Resources

- GitHub: Use `gh` CLI for issues, PRs, repos
- When using web tools, prefer authenticated access (avoid pasting sensitive URLs/content)
- Always check for MCP tools first before general-purpose API calls

---

**Last Updated**: 2026-03-22

For project-specific context, see individual repo CLAUDE.md files.
