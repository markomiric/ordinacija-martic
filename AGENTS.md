# ordinacija-martic agent guide

Use the shared contract in `~/.agents/AGENTS.md`, loaded by the global Codex and
Claude configuration. Start substantive work by reading the matching Agency
profile and relevant skills, then announce and record that selection. Prefer
Matt Pocock workflows, Context7 for library documentation, and Brave Search for
external evidence when the task calls for them.

The site is one static page, `index.html`, styled with a Bulma 0.9.4 subset and
local fonts. GitHub Pages serves the repository root as it is, so file paths are
public URLs; keep them stable. `css/README.md` owns how the CSS, fonts and icons
are rebuilt. A Next.js rebuild was archived to the ignored
`output/nextjs-app-2026-11-22.tgz` on 2026-11-22 and is not in use.

Read this checkout's source and nearer instructions for product context.
Preserve its security controls and unrelated dirty or staged work. Do not infer
current behavior from another checkout. Format touched files to the repository's
`.prettierrc` and run the relevant existing checks.

## Review workflow verification

For changes to the portable Codex review runner, run `node --test .claude/skills/codex-review/scripts/codex-review.test.mjs`. The fixture needs Git and Node.js and runs locally.

## Project agent checks

Use the repository's `project-checks` skill when selecting verification or handing off a reviewed change. For changes to agent hooks, skills, or commands, run `node --test ".claude/hooks/*/*.test.mjs" ".claude/skills/codex-review/scripts/*.test.mjs"` from the repository root. The local Stop hook checks edited paths. Use the project checks for full behavior verification.
