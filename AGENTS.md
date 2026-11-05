# Ordinacija Martić agent guide

This is the static public practice website. Keep page content, contact information, and search metadata consistent across the HTML and sitemap.

Keep the task scoped to the user request. Preserve unrelated changes and use local or synthetic data in checks. Follow the machine's shared agent contract when it is installed.

## Verification

Run `git diff --check`. Check affected links and visible changes in a local browser, including keyboard navigation and narrow layouts.

## Review workflow verification

For changes to the portable Codex review runner, run `node --test .claude/skills/codex-review/scripts/codex-review.test.mjs`. The fixture needs Git and Node.js and runs locally.

## Project agent checks

Use the repository's `project-checks` skill when selecting verification or handing off a reviewed change. For changes to agent hooks, skills, or commands, run `node --test ".claude/hooks/*/*.test.mjs" ".claude/skills/codex-review/scripts/*.test.mjs"` from the repository root. The local Stop hook checks edited paths. Use the project checks for full behavior verification.
