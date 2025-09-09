# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## System Overview

This repository contains a **complete implementation** of a spec-driven development system using Claude Code's agent architecture. This is not just documentation—it's a working system with 13 specialized agents, 5 workflows, and comprehensive project initialization capabilities.

## Framework Architecture

### Three-Tier System Architecture
1. **Project Intelligence Layer** - Deep codebase analysis and context farming
2. **Workflow Orchestration Layer** - Multi-agent coordination with quality gates  
3. **Implementation Layer** - Context-aware code generation and testing

### Spec-Driven Development Process
1. **Project Initialization** - Comprehensive codebase analysis and intelligent context discovery
2. **Requirements Phase** - Convert requests into formal EARS-syntax requirements
3. **Design Phase** - Create technical architectures following discovered patterns
4. **Tasks Phase** - Break down designs into executable, traceable implementation plans
5. **Implementation Phase** - Generate code that follows established project patterns

## Working with This System

### When Extending or Modifying This Framework

#### 1. Follow Agent Specialization Patterns
- **Each agent has a specific domain expertise** - maintain clear boundaries
- **Use hierarchical coordination** - Orchestrator agents manage complex workflows
- **Preserve context across agents** - Always pass comprehensive context between phases
- **Maintain human approval gates** - Never bypass quality control checkpoints

#### 2. Adhere to Workflow Standards
```yaml
# All workflows must follow this structure:
workflow_structure:
  inputs: # Clear parameter definitions with validation
  phases: # Sequential phases with clear dependencies
  human_gates: # Mandatory approval checkpoints
  outputs: # Structured, traceable deliverables
  error_handling: # Robust recovery mechanisms
```

#### 3. Context Preservation Requirements
- **Always read steering files** before any analysis or generation
- **Preserve MCP context** across all agent interactions
- **Maintain traceability** from original request to final implementation
- **Document decision rationale** for future learning

#### 4. Quality Gate Implementation
```markdown
Every workflow phase must include:
- Input validation and completeness checking
- Process execution with comprehensive analysis
- Output validation against established criteria
- Human review gate with clear approval options
- Context storage for future reference
```

### Development Standards for This Framework

#### Agent Development
```python
# Agent system prompt structure requirements:
class AgentSystemPrompt:
    def must_include(self):
        return [
            "Role and specialization definition",
            "Core responsibilities with specific boundaries", 
            "Analysis methodology with concrete steps",
            "Output format specifications with templates",
            "MCP integration strategy",
            "Quality validation checklist",
            "Communication style guidelines"
        ]
```

#### Workflow Development
```yaml
# Required workflow components:
required_components:
  - name: "descriptive_workflow_name"
  - description: "clear_purpose_and_scope"
  - config: "timeout, retries, human_interaction"
  - inputs: "validated_parameters_with_types"
  - phases: "sequential_steps_with_dependencies"
  - human_gates: "approval_points_with_options"
  - error_handling: "recovery_strategies"
  - outputs: "structured_deliverables"
```

#### Template Development
```markdown
# All templates must:
1. Use consistent variable naming: {VARIABLE_NAME}
2. Include comprehensive examples and guidance
3. Support both new and existing project contexts
4. Maintain traceability to requirements
5. Include validation criteria for completeness
6. Provide clear instructions for agents
```

## MCP Integration Requirements

### Continuity MCP Server Usage
```python
# Required MCP operations for all agents:
required_mcp_operations = {
    "context_storage": "Store analysis results and decisions",
    "pattern_retrieval": "Access similar successful patterns",
    "relationship_mapping": "Connect related project elements",
    "learning_integration": "Contribute to continuous improvement"
}
```

### State Management Standards
- **Session State**: Active workflow progress and agent interactions
- **Project State**: Comprehensive project context and steering files
- **Historical State**: Previous decisions and their outcomes
- **Cross-Project State**: Patterns and learnings shared across projects

## Implementation Guidelines

### Adding New Agents
1. **Create agent directory**: `.claude/agents/{agent-name}/`
2. **Write system prompt**: Follow established template structure
3. **Define specialization**: Clear domain boundaries and responsibilities
4. **Implement MCP integration**: Context storage and retrieval patterns
5. **Add quality validation**: Checklists and validation criteria
6. **Update orchestration**: Integrate into relevant workflows

### Extending Workflows  
1. **Follow sequential phases**: Maintain clear phase dependencies
2. **Include human gates**: Never bypass quality control checkpoints
3. **Preserve context**: Pass comprehensive context between phases
4. **Handle errors gracefully**: Robust recovery and retry mechanisms
5. **Document outputs**: Structured, traceable deliverables

### Creating Templates
1. **Use variable substitution**: `{VARIABLE_NAME}` format consistently
2. **Include agent instructions**: Clear guidance for template processing
3. **Provide examples**: Concrete examples for each template section
4. **Support validation**: Include criteria for completeness checking
5. **Maintain traceability**: Links back to requirements and decisions

## Quality Assurance Framework

### Code Quality Standards
- **Follow existing patterns** discovered through project analysis
- **Maintain consistency** with established naming and organizational conventions
- **Include comprehensive testing** aligned with project testing patterns
- **Apply security standards** based on project security requirements
- **Document decisions** for future reference and learning

### Validation Requirements
```python
# Every component must include validation:
validation_requirements = {
    "input_validation": "Verify all inputs meet specification",
    "process_validation": "Confirm process follows established patterns", 
    "output_validation": "Check outputs meet quality standards",
    "context_validation": "Ensure context preservation and accuracy",
    "traceability_validation": "Verify links to original requirements"
}
```

## Working with Existing Projects

### Project Onboarding Process
1. **Launch comprehensive analysis** using initialization workflows
2. **Review generated steering files** for accuracy and completeness
3. **Validate discovered patterns** against actual project implementation
4. **Customize agent behaviors** based on project-specific requirements
5. **Establish monitoring** for context drift and pattern evolution

### Feature Development Process
1. **Use orchestrator agent** for all feature development workflows
2. **Follow three-phase process** - Requirements → Design → Tasks
3. **Apply discovered patterns** consistently throughout implementation
4. **Maintain context awareness** by referencing steering files
5. **Document outcomes** for continuous learning improvement

## Extension Points

### Custom Agent Development
- **Domain-Specific Agents**: Add agents for specific business domains
- **Integration Agents**: Connect to external systems and APIs
- **Validation Agents**: Custom quality and compliance checking
- **Monitoring Agents**: Track system performance and outcomes

### Workflow Customization
- **Industry-Specific Workflows**: Adapt for specific industry requirements
- **Compliance Workflows**: Add regulatory and audit requirements
- **Integration Workflows**: Connect to existing development tools
- **Team-Specific Workflows**: Customize for team size and experience

This system represents a complete, working implementation of intelligent spec-driven development. When working within this framework, always prioritize context preservation, quality gates, and continuous learning to maintain the system's effectiveness and improve its recommendations over time.