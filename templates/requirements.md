# Requirements: {FEATURE_NAME}

**Feature ID**: {FEATURE_ID}  
**Priority**: {PRIORITY}  
**Created**: {CREATED_DATE}  
**Status**: {STATUS}

## Overview

{FEATURE_OVERVIEW_DESCRIPTION}

## Stakeholders

- **Primary Users**: {PRIMARY_USER_TYPES}
- **Secondary Users**: {SECONDARY_USER_TYPES}  
- **Business Owner**: {BUSINESS_STAKEHOLDER}
- **Technical Owner**: {TECHNICAL_STAKEHOLDER}

## User Stories

### Epic: {EPIC_NAME}
**Priority**: {EPIC_PRIORITY}

#### Story 1: {USER_STORY_TITLE}
**As a** {USER_ROLE}  
**I want** {DESIRED_CAPABILITY}  
**So that** {BUSINESS_VALUE}

**Acceptance Criteria**:
1. **WHEN** {TRIGGER_CONDITION} **THEN** the system **SHALL** {EXPECTED_BEHAVIOR}
2. **WHEN** {ERROR_CONDITION} **THEN** the system **SHALL** {ERROR_HANDLING_BEHAVIOR}
3. **WHERE** {EVENT_OCCURRENCE} **THE** system **SHALL** {RESPONSE_BEHAVIOR} **WITHIN** {TIME_CONSTRAINT}

**Priority**: {STORY_PRIORITY}  
**Estimated Effort**: {STORY_EFFORT}

#### Story 2: {USER_STORY_TITLE}
**As a** {USER_ROLE}  
**I want** {DESIRED_CAPABILITY}  
**So that** {BUSINESS_VALUE}

**Acceptance Criteria**:
1. **WHEN** {TRIGGER_CONDITION} **THEN** the system **SHALL** {EXPECTED_BEHAVIOR}
2. **WHILE** {SYSTEM_STATE} **THE** system **SHALL** {CONTINUOUS_BEHAVIOR}
3. **IF** {CONDITION_A} **AND** {CONDITION_B} **THEN** the system **SHALL** {CONDITIONAL_BEHAVIOR}

**Priority**: {STORY_PRIORITY}  
**Estimated Effort**: {STORY_EFFORT}

## Non-Functional Requirements

### Performance Requirements
- **WHEN** {LOAD_CONDITION} **THE** system **SHALL** {PERFORMANCE_REQUIREMENT}
- **THE** system **SHALL** process {OPERATION_TYPE} **WITHIN** {TIME_LIMIT}

### Security Requirements  
- **THE** system **SHALL** {SECURITY_BEHAVIOR} **FOR ALL** {PROTECTED_OPERATIONS}
- **WHEN** accessing {RESOURCE_TYPE} **THE** system **SHALL** verify {AUTHORIZATION_REQUIREMENT}

### Usability Requirements
- **THE** interface **SHALL** {USABILITY_REQUIREMENT} **WITHIN** {USABILITY_CONSTRAINT}
- **WHEN** {USER_ACTION} **THE** system **SHALL** provide {FEEDBACK_REQUIREMENT}

### Scalability Requirements
- **THE** system **SHALL** support {CONCURRENT_USERS} concurrent users
- **WHEN** load exceeds {THRESHOLD} **THE** system **SHALL** {SCALING_BEHAVIOR}

### Reliability Requirements
- **THE** system **SHALL** maintain {UPTIME_REQUIREMENT} availability
- **WHERE** system failure occurs **THE** system **SHALL** {RECOVERY_BEHAVIOR} **WITHIN** {RECOVERY_TIME}

## Business Rules

### Rule 1: {BUSINESS_RULE_NAME}
**THE** system **SHALL** {RULE_BEHAVIOR} **WHEN** {RULE_CONDITION}

### Rule 2: {BUSINESS_RULE_NAME}  
**IF** {BUSINESS_CONDITION} **THEN** the system **SHALL** {REQUIRED_ACTION}

## Data Requirements

### Data Entities
- **{ENTITY_NAME}**: {ENTITY_DESCRIPTION}
  - Required fields: {REQUIRED_FIELDS}
  - Optional fields: {OPTIONAL_FIELDS}
  - Validation rules: {VALIDATION_REQUIREMENTS}

### Data Relationships
- **{ENTITY_A}** has {RELATIONSHIP_TYPE} **{ENTITY_B}**
- **{ENTITY_C}** requires {DEPENDENCY_TYPE} **{ENTITY_D}**

### Data Quality Requirements
- **THE** system **SHALL** validate {DATA_TYPE} **BEFORE** storage
- **WHEN** data validation fails **THE** system **SHALL** {ERROR_RESPONSE}

## Integration Requirements

### External Systems
- **THE** system **SHALL** integrate with {EXTERNAL_SYSTEM} via {INTEGRATION_METHOD}
- **WHEN** {EXTERNAL_SYSTEM} is unavailable **THE** system **SHALL** {FALLBACK_BEHAVIOR}

### APIs and Services
- **THE** system **SHALL** expose {API_TYPE} endpoints for {PURPOSE}
- **THE** system **SHALL** consume {EXTERNAL_API} for {FUNCTIONALITY}

## Constraints and Assumptions

### Technical Constraints
- Must use existing {TECHNOLOGY_STACK}
- Must comply with {TECHNICAL_STANDARDS}
- Must integrate with {EXISTING_SYSTEMS}

### Business Constraints  
- Must be delivered by {DEADLINE}
- Must stay within budget of {BUDGET_CONSTRAINT}
- Must comply with {REGULATORY_REQUIREMENTS}

### Assumptions
- Users have {ASSUMED_TECHNICAL_CAPABILITY}
- {EXTERNAL_DEPENDENCY} will remain available
- {BUSINESS_ASSUMPTION} will continue to be true

## Risk Assessment

### High Risk Items
- **Risk**: {RISK_DESCRIPTION}
  - **Impact**: {IMPACT_DESCRIPTION}
  - **Probability**: {PROBABILITY_LEVEL}
  - **Mitigation**: {MITIGATION_STRATEGY}

### Dependencies
- **Dependency**: {DEPENDENCY_NAME}
  - **Type**: {DEPENDENCY_TYPE}
  - **Owner**: {DEPENDENCY_OWNER}
  - **Risk Level**: {RISK_LEVEL}

## Success Criteria

### Primary Success Metrics
- {SUCCESS_METRIC_1}: {TARGET_VALUE}
- {SUCCESS_METRIC_2}: {TARGET_VALUE}

### Secondary Success Metrics  
- {SUCCESS_METRIC_3}: {TARGET_VALUE}
- {SUCCESS_METRIC_4}: {TARGET_VALUE}

## Out of Scope

### Explicitly Excluded
- {EXCLUDED_FUNCTIONALITY_1}
- {EXCLUDED_FUNCTIONALITY_2}

### Future Phases
- **Phase 2**: {FUTURE_FUNCTIONALITY_1}
- **Phase 3**: {FUTURE_FUNCTIONALITY_2}

## Traceability Matrix

| Requirement ID | User Story | Business Rule | Test Cases | Design Elements |
|----------------|------------|---------------|------------|-----------------|
| REQ-001 | Story 1 | Rule 1 | TC-001, TC-002 | Component A |
| REQ-002 | Story 1 | Rule 2 | TC-003, TC-004 | Component B |
| REQ-003 | Story 2 | Rule 1 | TC-005, TC-006 | Component C |

## Appendices

### Appendix A: Glossary
- **{TERM_1}**: {DEFINITION_1}
- **{TERM_2}**: {DEFINITION_2}

### Appendix B: References
- {REFERENCE_1}
- {REFERENCE_2}

---

**Template Variables for Agent Processing**:
- Replace all `{VARIABLE_NAME}` placeholders with actual content
- Ensure all EARS syntax follows the prescribed patterns
- Maintain numbering and structure consistency
- Include all mandatory sections even if brief
- Link requirements to user stories and business rules
- Provide objective, testable acceptance criteria