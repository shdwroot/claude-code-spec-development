---
description: Discover and document comprehensive project context across multiple dimensions
argument-hint: [discovery_scope]
---

Execute the context discovery workflow with scope: $1

Use the general-purpose agent to run the comprehensive context discovery workflow with the following parameters:

- project_root: !pwd
- discovery_scope: $1
- discovery_targets: ["architecture", "patterns", "conventions", "domain", "integrations"]
- existing_documentation: []
- team_knowledge: {}

This will perform multidimensional context analysis and generate comprehensive documentation in .claude/context/, .claude/guidance/, and .claude/patterns/