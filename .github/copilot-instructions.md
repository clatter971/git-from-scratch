# Copilot Instructions for git-from-scratch

## What this repository does
- This is a hands-on Git and GitHub course, not an application codebase.
- The course has 17 modules across five parts. Each module combines a short lesson, a lab, and a setup script that creates a disposable practice repository.
- The main guided experience is through Claude Code slash commands, but every lab also works as plain markdown.

## Architecture hotspots
- `README.md` - public course overview, prerequisites, and supported workflows.
- `curriculum\part-*\NN-*\lesson.md` - concept explanation for each module.
- `curriculum\part-*\NN-*\lab.md` - numbered exercises, verification steps, and quizzes.
- `curriculum\part-*\NN-*\setup.sh` - bash setup scripts that build the practice repos in `/tmp/git-lab-NN/`.
- `progress.template.md` - local checklist template; users copy it to `progress.md` and keep it untracked.
- `.claude\CLAUDE.md` and `.claude\commands\lab.md` - teaching style, progress tracking, and guided lab flow.

## Commands that exist
Run these from the repository root unless noted otherwise:

```bash
cp progress.template.md progress.md
bash curriculum/part-1-foundations/01-what-is-git/setup.sh
claude
```

Claude Code workflows exposed by the repo:
- `/lab`
- `/lab 04`
- `/redo`
- `/redo course`

There is no build, lint, test, package manager, or CI workflow in this repository.

## Environment and runtime caveats
- Labs require a bash-compatible shell. Git Bash, WSL, or macOS/Linux terminals are supported; PowerShell and `cmd.exe` are not.
- Setup scripts are intentionally destructive to the lab directory and recreate `/tmp/git-lab-NN/` from scratch.
- Modules 05, 11, 12, 13, 14, and 16 require a GitHub account plus `gh auth login`; the rest work offline.
- This is a public repo. Do not add real names, emails, usernames, or machine-specific paths to tracked files.

## Conventions for future coding agents
- Treat the repo as curriculum content. Prefer changes to lessons, labs, and setup scripts over adding new tooling.
- Keep each module self-contained: `lesson.md`, `lab.md`, and `setup.sh` should still make sense together.
- Preserve the teaching style from `.claude\CLAUDE.md`: explain the why, ask for predictions, and verify outcomes.
- In learner-facing docs, prefer one command per code block and show complete copy-pasteable commands.
- Keep setup scripts idempotent and safe with `set -euo pipefail`.
- Never direct practice work into a learner's real repositories; all exercises should stay in temporary lab directories.
