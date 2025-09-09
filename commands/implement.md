---
description: Implement tasks from generated specifications
argument-hint: [feature_name] [task_number]
---

Implement task $2 for feature: $1

Read task specifications from: specs/$1/tasks.md

Find task $2 and implement:
- Load requirements from specs/$1/requirements.md
- Follow design from specs/$1/design.md  
- Generate production-ready code
- Include tests and documentation
- Follow project patterns and architecture

@specs/$1/requirements.md
@specs/$1/design.md
@specs/$1/tasks.md