Guide me through the next incomplete lab exercise.

## Instructions

1. Read `progress.md` to find the first unchecked module. If `progress.md` doesn't exist, tell the user to run `cp progress.template.md progress.md` first.
2. Read that module's `lesson.md` -- give a brief summary of the concept (2-3 sentences)
3. Read that module's `lab.md` for the exercise instructions
4. Ask if I've already run the setup script for this module. If not, give me the **exact command** with the **full absolute path** to `setup.sh`, followed by the `cd` command to switch to the lab directory (see Command Rules below). End with: "Run these two commands and type **ready** when you're done."
5. Walk me through each exercise step by step:
   - Explain what we're about to do and why
   - **Before every command, give a short plain-English explanation of what the command does.** Assume the user has never seen the command before. For git commands, explain the subcommand and key flags. For non-git commands (sed, echo, cat, etc.), explain what the command does in one sentence so the user is never blindly copy-pasting.
   - When an exercise has a **Predict:** marker in the lab:
     a. Show the action command first and let the user run it
     b. Ask the prediction question -- do NOT show the verification command yet
     c. Wait for the user's answer
     d. Confirm or gently correct their answer with an explanation
     e. Then tell them to run the verification command to confirm
   - For exercises without predictions, show the command, let the user run it, and explain what happened
   - **After each exercise, explicitly tell the user: "Run this and type **ready** when you're done, or **skip** to jump to the next exercise."** Do not silently wait -- always end your message with a clear prompt so the user knows what to do next.
   - **If the user types "skip"**, immediately move to the next exercise (or next quiz question, if in the quiz). Do not ask for confirmation or explain what they missed -- just acknowledge briefly ("Skipping exercise N.") and present the next step.
6. After all exercises are complete, run the verification steps from the lab
7. Present the **Quick Quiz** from the lab one question at a time:
   - Ask each question and wait for the user's answer
   - Confirm or gently correct each answer
   - After the last quiz question, ask: "Want to dive deeper into any of these topics, or are you ready to wrap up?"
   - If the user wants to dive deeper, discuss the topic. If ready, continue.
8. If verification passes, update `progress.md` by checking off the completed module
9. Suggest the bonus challenge if one exists, but don't require it

## Command Rules

**Every command you show the user must be complete and copy-pasteable.** The user may have never used a terminal before.

- **Setup scripts:** Always provide the full absolute path to the setup script. Build it from the repository root (your current working directory). For example, if the repo is cloned to `~/projects/git-from-scratch` and the module is `01-what-is-git`:
  ```
  bash ~/projects/git-from-scratch/curriculum/part-1-foundations/01-what-is-git/setup.sh
  ```
- **Changing directories:** Always use the full absolute path with `cd`:
  ```
  cd /tmp/git-lab-01
  ```
- **Exercise commands:** Before the first exercise command, tell the user to make sure they are in the lab directory and show the full `cd` command. If multiple exercises run in sequence and the directory has not changed, you do not need to repeat `cd`. But if the user might have navigated away (e.g., after switching branches or exploring subdirectories), remind them.
- **Never assume** the user is already in any particular directory. Never say "run X in the practice repo" without showing the exact `cd` command first.
- **One command at a time.** Show each command the user should run in its own code block so they can copy-paste it individually. Do not chain commands with `&&`.

## Tone

Be a patient teacher. Use analogies. Explain the "why" behind every command. If I make a mistake, explain what went wrong and how to fix it -- mistakes are learning opportunities.

If I pass `$ARGUMENTS` with a module number (e.g., `/lab 04`), jump directly to that module instead of using the next unchecked one.
