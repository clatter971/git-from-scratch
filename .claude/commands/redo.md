Reset course progress and lab environments.

## Instructions

The user typed `/redo` with optional arguments: `$ARGUMENTS`

### Determine the reset mode

**Mode 1: "this part" (or no arguments)**
Reset only the current module's lab environment.

1. Read `progress.md` to figure out which module the user is currently working on (the first unchecked module, or the last checked one if they might be revisiting it). If `progress.md` doesn't exist, tell the user to run `cp progress.template.md progress.md` first.
2. Identify the corresponding `/tmp/git-lab-NN` directory (e.g., module 10 = `/tmp/git-lab-10`). Verify that NN is between 01 and 17 and corresponds to an actual module directory under `curriculum/`.
3. Uncheck that module in `progress.md` if it was checked.
4. Tell the user to run these cleanup commands themselves. Show each command in its own code block so they can copy-paste:

   ```
   rm -rf /tmp/git-lab-NN
   ```

   ```
   rm -rf /tmp/git-lab-NN-files
   ```

   Explain: "`rm -rf` removes a directory and everything inside it. These delete the practice repo and any support files that the setup script created."

5. Finish with: "Once you've run those, type `/lab` to start the module fresh."

**Mode 2: "course"**
Full course reset -- requires confirmation.

1. Ask the user: **"Are you sure you want to reset the entire course? This will clear all progress. Type `yes` to confirm or `no` to cancel."**
2. **Wait for the user's response.** Do not proceed until they reply.
3. If the user says **no** (or anything other than yes): "No problem -- nothing was changed."
4. If the user says **yes**:
   a. Reset `progress.md` by copying the template: `cp progress.template.md progress.md`
   b. Tell the user to clean up lab directories by running this command:

      ```
      rm -rf /tmp/git-lab-*
      ```

      Explain: "`rm -rf` removes directories and everything inside them. The `*` wildcard matches all lab directories at once."

   c. Finish with:

      "Progress cleared! Once you've run the cleanup command above:
      - Type `/lab` to start from Module 01
      - Type `/lab NN` to jump to a specific module"

### Argument parsing

- `/redo` or `/redo this part` -> Mode 1
- `/redo course` -> Mode 2
- Anything else -> explain the two options and ask the user to pick one
