# Quick Start Guide: Project Initialization and Context Discovery

## Overview

This guide walks you through the complete process of initializing your existing project with the spec-driven development system, including comprehensive context discovery and intelligent steering file generation.

## Prerequisites

- Claude Code installed and configured
- Project repository accessible
- Basic understanding of your project's technology stack
- Administrative access to project files and git history

## Step-by-Step Initialization Process

### Step 1: Setup Project Structure

1. **Navigate to your project root directory**
   ```bash
   cd /path/to/your/project
   ```

2. **Copy the spec-driven development system**
   ```bash
   # Copy the .claude directory to your project
   cp -r /path/to/spec-driven-code/.claude ./
   ```

3. **Verify structure**
   ```bash
   ls -la .claude/
   # Should show: agents/, config/, steering/, templates/, workflows/
   ```

### Step 2: Launch Comprehensive Project Onboarding

Using Claude Code, start the complete onboarding workflow:

```
Launch the initialization-coordinator agent with the complete project onboarding workflow.

Project Details:
- Project Root: /absolute/path/to/your/project
- Project Name: YourProjectName
- Analysis Scope: comprehensive
- Team Context: {
    "team_size": 5,
    "experience_level": "mixed", 
    "preferred_practices": ["testing", "documentation", "security"],
    "compliance_requirements": ["GDPR", "SOC2"]
  }

Please run the complete onboarding workflow including:
1. Repository structure analysis
2. Technology stack discovery
3. Architecture pattern identification  
4. Code quality assessment
5. Business domain extraction
6. Security and performance analysis
7. Intelligent steering file generation
8. Knowledge base creation
```

### Step 3: Workflow Phases Explained

The onboarding process includes these major phases:

#### Phase 1: **Repository Discovery** (5-10 minutes)
- **Codebase Archaeologist** analyzes your directory structure
- Maps file organization patterns and naming conventions
- Analyzes git history for development patterns
- **Expected Output**: Repository structure analysis and file classification

#### Phase 2: **Technology Analysis** (10-15 minutes)  
- **Tech Stack Analyst** identifies all technologies and dependencies
- Analyzes framework usage patterns and build configurations
- Assesses modernization opportunities
- **Expected Output**: Complete technology inventory and dependency analysis

#### Phase 3: **Architecture Discovery** (15-20 minutes)
- **Architecture Detective** identifies architectural patterns
- Maps component relationships and data flows
- Analyzes integration points and design quality
- **Expected Output**: Comprehensive architecture documentation

#### Phase 4: **Quality Assessment** (10-15 minutes)
- **Code Quality Auditor** analyzes coding standards and conventions
- Assesses testing patterns and documentation quality
- Identifies maintainability patterns
- **Expected Output**: Code quality metrics and standards analysis

#### Phase 5: **Business Context Extraction** (10-15 minutes)
- **Domain Analyst** extracts business domain understanding
- Identifies user workflows and business rules
- Maps feature capabilities and user personas
- **Expected Output**: Business domain model and user understanding

#### Phase 6: **Security & Performance Analysis** (10-15 minutes)
- **Security/Performance Analyst** assesses current patterns
- Identifies security implementations and performance characteristics
- Evaluates scalability and monitoring setup
- **Expected Output**: Security posture and performance baseline

#### Phase 7: **Human Review Gate** 
⚠️ **Required Human Interaction**

You'll be presented with a comprehensive analysis summary including:
- Repository metrics and organization patterns
- Technology stack assessment and modernization opportunities
- Architecture patterns and design quality scores  
- Code quality metrics and standards
- Business domain understanding and feature mapping
- Security and performance assessments

**Review Options:**
- **Approve**: Proceed to steering file generation
- **Refine**: Request deeper analysis in specific areas
- **Manual Review**: Examine specific findings in detail
- **Restart**: Restart with different analysis parameters

#### Phase 8: **Intelligent Steering File Generation** (5-10 minutes)
- **Steering File Generator** synthesizes all analysis results
- Creates customized steering files based on your specific codebase patterns
- Generates context-aware guidelines and standards
- **Expected Output**: Four intelligent steering files tailored to your project

### Step 4: Review Generated Assets

After completion, you'll have:

#### **Generated Steering Files** (`.claude/steering/`)
- `product.md` - Product vision and user context extracted from your codebase
- `tech.md` - Technology standards and patterns derived from your code
- `structure.md` - Project organization rules based on your current structure
- `security.md` - Security requirements based on your current implementations

#### **Comprehensive Analysis** (`.claude/analysis/`)
- `repository_analysis.md` - Complete repository structure and organization analysis
- `architecture_documentation.md` - Detailed architectural patterns and component relationships
- `technology_inventory.md` - Complete technology stack and dependency analysis
- `code_quality_report.md` - Code quality metrics and standards assessment
- `security_assessment.md` - Security posture and compliance analysis

#### **Development Guides** (`.claude/guides/`)
- `development_setup.md` - Optimized development workflow recommendations
- `contribution_guidelines.md` - Team onboarding and contribution standards
- `architecture_decisions.md` - Documented architectural decisions and rationale

#### **Knowledge Base** (MCP Continuity Storage)
- Searchable project intelligence
- Pattern libraries and best practices
- Cross-referenced project relationships
- Historical decision context

### Step 5: Begin Spec-Driven Development

With initialization complete, you can now use the full spec-driven development workflow:

```
I need to implement user authentication with OAuth support.
The feature should allow users to sign in with Google and GitHub,
store user profiles, and provide secure session management.
```

The system will now:
1. **Generate Requirements** using your extracted business context and user understanding
2. **Create Technical Design** following your discovered architectural patterns and technology stack
3. **Plan Implementation Tasks** using your established coding standards and project structure
4. **Generate Code** that follows your existing patterns and conventions

## Advanced Configuration Options

### Custom Analysis Focus

If you want to focus the analysis on specific areas:

```
Launch initialization with custom focus:
- Analysis Focus: {
    "architecture": true,
    "business_domain": true, 
    "security": true,
    "performance": false,  // Skip performance analysis
    "testing": false       // Skip testing analysis
  }
```

### Team-Specific Customization

Customize for your team's experience level:

```
Team Context: {
  "team_size": 3,
  "experience_level": "senior",        // More principles, less detailed guidance
  "preferred_practices": ["TDD", "DDD", "microservices"],
  "compliance_requirements": ["HIPAA", "PCI-DSS"]
}
```

### Incremental Analysis

For large codebases or time constraints:

```
Analysis Scope: "standard"    // Options: focused, standard, comprehensive, deep
```

## Troubleshooting Common Issues

### Issue: "Insufficient Permissions"
**Solution**: Ensure Claude Code has read access to all project directories and git history.

### Issue: "Analysis Timeout" 
**Solution**: Use "standard" or "focused" analysis scope for large repositories, or enable sampling mode.

### Issue: "Inconsistent Analysis Results"
**Solution**: The system will automatically trigger cross-validation. Review specific findings that seem incorrect.

### Issue: "Missing Technology Detection"
**Solution**: Ensure your package manager files (package.json, requirements.txt, etc.) are present and up-to-date.

## Next Steps After Initialization

1. **Review Steering Files**: Customize the generated steering files if needed
2. **Share with Team**: Distribute the generated documentation to your development team  
3. **Start Feature Development**: Use the spec-driven workflow for your next feature
4. **Monitor and Refine**: The system learns from usage - provide feedback on generated specs and code

## Benefits You'll Experience

- **Consistent Development**: All new features follow established patterns
- **Reduced Onboarding Time**: New team members understand the project quickly
- **Better Architecture**: AI agents understand your existing architecture and extend it properly
- **Quality Assurance**: Built-in quality gates ensure consistent code quality
- **Knowledge Preservation**: Institutional knowledge is captured and preserved

## Support and Customization

The initialization system is designed to be extensible:

- **Custom Agents**: Add domain-specific analysis agents
- **Extended Templates**: Create templates for your specific feature types
- **Custom Workflows**: Adapt workflows for your development process
- **Integration Hooks**: Connect to your existing development tools

---

**Ready to transform your development process?** Start with the initialization workflow and experience the power of comprehensive project understanding combined with structured AI-assisted development.