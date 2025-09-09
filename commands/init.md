---
description: Initialize project with comprehensive analysis and context discovery
argument-hint: [project_name]
---

Execute the project initialization workflow for project: $1

Use the project-initialization-coordinator agent to run the complete initialization workflow with the following parameters:

- project_root: !pwd
- project_name: $1
- analysis_depth: comprehensive
- focus_areas: ["architecture", "patterns", "dependencies", "security", "performance"]
- team_context:
  - team_size: mixed
  - experience_level: mixed
  - preferred_practices: ["clean_code", "testing", "documentation"]

This will analyze your codebase and generate intelligent steering files in .claude/steering/