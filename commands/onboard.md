---
description: Complete project onboarding workflow
argument-hint: [project_name]
---

Execute the comprehensive project onboarding workflow for $1.

Use the project-initialization-coordinator agent to run the complete onboarding workflow defined in onboarding-complete.yml with the following parameters:

- project_root: !pwd
- project_name: $1
- team_context: 
  - team_size: mixed
  - experience_level: mixed
  - preferred_practices: ["clean_code", "testing", "documentation"]
- onboarding_goals: ["understand_architecture", "extract_patterns", "generate_guidelines", "setup_development"]
- analysis_focus:
  - architecture: true
  - business_domain: true
  - security: true
  - performance: true
  - testing: true