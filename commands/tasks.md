---
description: List all available tasks for a feature
argument-hint: [feature_name]
---

Show implementation tasks for feature: **$1**

Read the tasks from: `specs/$1/tasks.md`

Display:
- **Task numbers** for use with `/implement`
- **Task descriptions** and effort estimates
- **Dependencies** between tasks  
- **Current status** of each task

Example: After running this, use `/implement $1 1` to implement task #1

@specs/$1/tasks.md