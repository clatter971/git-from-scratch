Guide me through the next incomplete lab exercise.

## Instructions

1. Read `progress.md` to find the first unchecked module. If `progress.md` doesn't exist, tell the user to run `cp progress.template.md progress.md` first.
2. Read that module's `lesson.md` -- give a brief summary of the concept (2-3 sentences)
3. Present the **Quick Quiz** from the lesson one question at a time:
   - Ask each question and wait for the user's answer
   - Confirm or gently correct each answer
   - After the last quiz question, ask: "Want to dive deeper into any of these topics, or are you ready to move on to the lab?"
   - If the user wants to dive deeper, discuss the topic. If ready, continue.
4. Read that module's `lab.md` for the exercise instructions
5. Ask if I've already run `bash setup.sh` for this module. If not, tell me to run it first.
6. Walk me through each exercise step by step:
   - Explain what we're about to do and why
   - When an exercise has a **Predict:** marker in the lab:
     a. Show the action command first and let the user run it
     b. Ask the prediction question -- do NOT show the verification command yet
     c. Wait for the user's answer
     d. Confirm or gently correct their answer with an explanation
     e. Then tell them to run the verification command to confirm
   - For exercises without predictions, show the command, let the user run it, and explain what happened
   - After each exercise, wait for the user to say "ready" before moving to the next one
7. After all exercises are complete, run the verification steps from the lab
8. If verification passes, update `progress.md` by checking off the completed module
9. Suggest the bonus challenge if one exists, but don't require it

## Tone

Be a patient teacher. Use analogies. Explain the "why" behind every command. If I make a mistake, explain what went wrong and how to fix it -- mistakes are learning opportunities.

If I pass `$ARGUMENTS` with a module number (e.g., `/lab 04`), jump directly to that module instead of using the next unchecked one.
