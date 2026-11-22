@AGENTS.md

## Project workflows

Read `AGENTS.md` before planning, changing, or reviewing code. Load `project-checks` to select the project's validation. Use `/team-plan` to prepare a plan, `/build` for an approved implementation, and `/team-build` when its approved scope includes delegated work. `/workflow-build` requires explicit invocation and an approved scope.

Use `session-management` on resume, `sub-agent-invocation` for approved delegation, and `git-commits` for an authorized commit. Project agents live in `.claude/agents/`. Use their declared scope and keep reviews report-only. The local hooks suggest skills, format supported edits, check changed files, and show task context on resume. Run the complete relevant project checks before a Codex review.

## Codex second review

Use the `codex-review` skill once after the relevant project checks pass for a
substantive change, on a saved plan before implementation approval, and when the
user asks for a second opinion. Use the authorized Codex account and exact
source scope. Verify findings before acting on them. Report skipped or failed
reviews separately from the project checks.
