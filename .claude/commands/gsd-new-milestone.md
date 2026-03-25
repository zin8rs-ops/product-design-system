Create a new milestone plan.

1. Ask the user for the milestone name and goal if not provided as an argument
2. Write `.planning/CURRENT_MILESTONE.md` with:
   - Milestone name + version
   - Goal statement
   - Empty task list (ask user to describe the work, then break it into tasks)
3. Confirm the file was created and show the task list

If a current milestone already exists, ask the user to complete it first with /gsd:complete-milestone.
