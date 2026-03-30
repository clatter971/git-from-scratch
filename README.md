# Git From Scratch -- Zero to Hero

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

A hands-on Git course with 17 modules -- short lessons followed by labs where you actually practice on real repos. The labs are designed to be guided by [Claude Code](https://claude.ai/claude-code): type `/lab` in your terminal and it walks you through each exercise, explains commands before you run them, and helps you fix things when you mess up.

You don't need Claude Code to use this -- every lab is a self-contained markdown file you can follow on your own. But the guided mode is the main way I use it and where the course works best.

Free, open source, just clone and go.

## Why this exists

I was using Git daily but didn't actually understand what I was doing. I kept Googling the same things and copy-pasting commands. So I built this to force myself to learn it properly.

The Claude Code integration happened because the biggest pain point when learning Git is screwing up a command and ending up in some weird state with no idea how to get out. Claude can see your terminal output and walk you through fixing it, which removes a lot of the guesswork. You can also ask questions mid-exercise and get answers that reference the actual repo you're working in, not generic explanations.

## Prerequisites

| Tool | Check | Install guide |
|------|-------|---------------|
| **Git** | `git --version` | [git-scm.com/downloads](https://git-scm.com/downloads) |
| **Bash terminal** | `bash --version` | See [terminal setup](#terminal-setup) below |
| **GitHub account** | -- | [github.com/signup](https://github.com/signup) |
| **GitHub CLI** | `gh --version` | [cli.github.com](https://cli.github.com/) |
| **Claude Code** | `claude --version` | [claude.ai/claude-code](https://claude.ai/claude-code) -- the guided lab experience |

### GitHub connection

Several labs (05, 11, 12, 13, 14, 16) create temporary repositories on GitHub to practice pull requests, issues, actions, and other platform features. These labs require:

1. A **GitHub account** -- [sign up here](https://github.com/signup) if you don't have one
2. The **GitHub CLI (`gh`) installed** -- [cli.github.com](https://cli.github.com/)
3. The **CLI authenticated** to your account -- run `gh auth login` and follow the prompts
4. The **`delete_repo` scope** on your token (needed to clean up practice repos) -- run `gh auth refresh -h github.com -s delete_repo`

You can verify your connection with:

```bash
gh auth status
```

> **No GitHub account?** Modules 01-04, 06-10, 15, and 17 work entirely offline with local Git -- no account needed. You can complete those first and set up GitHub when you're ready.

### Terminal setup

The setup scripts and lab exercises use **bash**. This works out of the box on macOS and Linux. Windows users need one of the following:

- **Git Bash** (recommended) -- included when you install [Git for Windows](https://gitforwindows.org/). Open "Git Bash" from the Start menu.
- **WSL (Windows Subsystem for Linux)** -- run `wsl --install` in PowerShell, then open the Ubuntu terminal. [Microsoft WSL guide](https://learn.microsoft.com/en-us/windows/wsl/install).
- **VS Code terminal** -- if you have Git for Windows installed, configure VS Code to use Git Bash as the default terminal.

> **Note:** PowerShell and cmd.exe are not supported. The setup scripts use bash syntax (heredocs, `/tmp/` paths, `set -euo pipefail`) that requires a bash-compatible shell.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/clatter971/git-from-scratch.git
cd git-from-scratch
```

### 2. Create your progress tracker

```bash
cp progress.template.md progress.md
```

This file tracks which modules you have completed. It is listed in `.gitignore` so it stays local to your machine.

### 3. Start learning

Pick one of the two paths below and jump into Module 01.

## How to Use This Course

### With Claude Code

1. Open a terminal in the repo directory and run `claude`
2. Type `/lab` to start a guided walkthrough of your next module
3. Claude walks you through exercises step by step and marks modules complete when you're done
4. Jump to a specific module anytime: `/lab 04`
5. Reset the current lab: `/redo` -- removes the lab directory and marks the module incomplete so you can start it fresh
6. Reset the entire course: `/redo course` -- clears all progress and lab directories (asks for confirmation first)

### Without Claude Code

Each lab is fully self-contained -- you don't need Claude to follow along:

1. **Read the lesson** -- open `curriculum/<part>/<module>/lesson.md` for the concept explanation and video links
2. **Run the setup** -- `bash curriculum/<part>/<module>/setup.sh` creates a practice repo in `/tmp/`
3. **Follow the exercises** -- open `lab.md` in the same folder and work through the numbered steps
4. **Check your work** -- each lab has a "Verify" section telling you how to confirm success
5. **Track progress** -- check off completed modules in `progress.md`

Example for Module 01:

```bash
bash curriculum/part-1-foundations/01-what-is-git/setup.sh
# then open curriculum/part-1-foundations/01-what-is-git/lab.md and follow along
```

## Curriculum

Modules marked *GitHub* require a GitHub account and the `gh` CLI. All other modules work entirely offline with local Git.

### Part 1: Foundations
| # | Module | What You Learn |
|---|--------|----------------|
| 01 | What is Git? | Mental model of version control, repos, commits |
| 02 | Setup & Config | Install, configure identity, SSH keys |
| 03 | The Basics | init, add, commit, status, log, diff |

### Part 2: Branching & Collaboration
| # | Module | What You Learn | |
|---|--------|----------------|-|
| 04 | Branches | Create, switch, delete branches; understand HEAD | |
| 05 | PR Workflow | Fork, clone, branch, push, open PR, review, merge | *GitHub* |
| 06 | Merging & Conflicts | Fast-forward vs 3-way merge, resolving conflicts | |
| 07 | Rebasing | Rebase vs merge, interactive rebase, when to use each | |
| 08 | Stashing | Save work-in-progress, apply later, manage stash stack | |

### Part 3: Recovery & History
| # | Module | What You Learn | |
|---|--------|----------------|-|
| 09 | Undoing Mistakes | reset, revert, checkout, restore, clean | |
| 10 | Cherry-pick & History | Cherry-pick commits, bisect, log filtering | |
| 11 | Tags & Releases | Lightweight vs annotated tags, GitHub releases | *GitHub* |

### Part 4: GitHub Platform
| # | Module | What You Learn | |
|---|--------|----------------|-|
| 12 | Issues & Projects | Issue tracking, labels, milestones, project boards | *GitHub* |
| 13 | GitHub Actions | CI/CD basics, workflow files, common actions | *GitHub* |
| 14 | Branch Protection | Rules, required reviews, status checks | *GitHub* |

### Part 5: Security
| # | Module | What You Learn | |
|---|--------|----------------|-|
| 15 | Securing Your Account | 2FA, SSH keys, PATs, session management | |
| 16 | Repository Security | Dependabot, secret scanning, security policies | *GitHub* |
| 17 | Public Repo Best Practices | .gitignore, secrets hygiene, LICENSE, CODEOWNERS | |

## Philosophy

- **Short explanations, then practice** -- you learn Git by doing, not reading
- **Real scenarios** -- labs simulate actual situations you will encounter at work
- **Safe to experiment** -- everything runs in temporary directories, your real repos are untouched
- **Progressive** -- each module builds on the previous ones

## Built With

This course was built with [Claude Code](https://claude.ai/claude-code) -- both as a development tool for writing the curriculum and as the interactive lab instructor that guides you through it.

## Contributing

Found a typo, broken link, or have an idea for a new module? Open an [issue](https://github.com/clatter971/git-from-scratch/issues) or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
