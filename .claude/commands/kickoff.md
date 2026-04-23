---
description: Start a new task using the plan-first workflow. Produces a checkable plan before implementation.
argument-hint: [task description]
---

Plan-first kickoff for a new task.

Task: $ARGUMENTS

## Instructions
1. Analyze the task and break it into checkable steps
2. Identify assumptions and open questions
3. Design a verification plan
4. Write the plan to `tasks/todo.md` and mirror the steps into TaskCreate
5. Present the plan for approval before implementing

## Return
1. Plan checklist (checkable items)
2. Assumptions / questions
3. Implementation approach
4. Verification plan
5. Updated `tasks/todo.md`
