---
description: Switch output style for this session.
argument-hint: terse | verbose
---

If $ARGUMENTS is empty, list available styles by running `ls .claude/output-styles/` and ask the user which one to apply.

Otherwise, read `.claude/output-styles/$ARGUMENTS.md` and apply every rule in that file to all remaining responses in this session. If the file does not exist, list available styles and ask which one to apply.
