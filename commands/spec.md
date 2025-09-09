---
description: Generate specs for a feature using three-phase workflow
argument-hint: [feature_name] [feature_request]
---

Generate specifications for feature: **$1**

Description: $ARGUMENTS

Execute the complete spec-driven development workflow:

1. **Requirements Analysis** - Generate EARS format requirements
2. **Technical Design** - Create detailed architecture and API specifications  
3. **Task Breakdown** - Build implementation plan with dependencies

This creates comprehensive documentation in `specs/$1/` including:
- requirements.md (EARS format user stories)
- design.md (technical architecture)
- tasks.md (implementation tasks)