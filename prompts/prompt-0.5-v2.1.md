# Prompt #0.5 V2.1: Automated Workflow Setup with Linting Integration

**Version**: 2.1
**Last Updated**: January 2025
**Purpose**: Create a robust automated workflow system with better error handling, state management, and integrated code quality enforcement

**Usage**: Run this after MCP setup (Prompt #0 V2.0) to build the workflow automation framework. Creates all necessary files for sequential execution with linting integration.

```
I'll create an automated workflow system for the 8-prompt development process. This system will track progress, validate steps, enforce code quality, and ensure proper execution order.

**PREREQUISITES VERIFICATION:**
First, let me verify MCP servers are working:

Run: /mcp

Confirm all 5 servers show "connected". If not, return to Prompt #0 V2.0.

**STEP 1: Create Workflow Directory Structure**
I'll use the filesystem server to create the necessary directories:

Create directory: plan/
Create directory: plan/prompts/
Create directory: plan/automation/
Create directory: plan/logs/
Create directory: plan/quality/

**STEP 2: Create Core Workflow Files**

**FILE 1: plan/automation/workflow-executor.md**
```markdown
# Automated Workflow Executor

## System Overview
This executor manages the 8-prompt AI development workflow with automatic validation, error recovery, and code quality enforcement.

### Prompt Execution Order
0. **MCP Setup** - Infrastructure configuration (manual)
0.5. **Workflow Setup** - Automation framework (manual)
1. **Requirements** - Interactive discovery session
2. **Specification** - Document generation with linting config
3. **Planning** - Development roadmap with TDD and linting
4. **Project Setup** - Infrastructure, todos, and linter setup
5. **Session Init** - Daily startup routine with quality checks
6. **TDD Template** - Feature development with integrated linting

### Execution Modes

#### Full Project Setup (Prompts 1-4)
```
Execute complete project initialization sequence:
1. Load and run prompt-1-requirements.md
2. Validate outputs: spec outline created
3. Load and run prompt-2-specification.md  
4. Validate outputs: spec.md, claude.md, work-journal.md exist
5. Load and run prompt-3-plan-generation.md
6. Validate outputs: development plan created with linting tasks
7. Load and run prompt-4-project-setup.md
8. Validate outputs: todo.md, project structure, linter configured
9. Verify linter installation and configuration
```

#### Daily Development (Prompts 5-6)
```
Execute development session:
1. Load and run prompt-5-session-init.md
2. Validate: context loaded, linter verified, priorities identified
3. For each development task:
   - Load prompt-6-tdd-template.md
   - Replace [TASK_DESCRIPTION] with specific task
   - Execute with TDD and linting enforcement
   - Validate: tests written first, linting passes, all tests pass
```

### Validation Gates
Each step must pass validation before proceeding:
- Required files created via filesystem server
- No error messages in execution
- Workflow state updated successfully
- Memory server contains step context
- **Linter configured and passing (Phase 1+)**
```

**FILE 2: plan/automation/workflow-state.json**
```json
{
  "version": "2.1.0",
  "workflow_id": "{{GENERATE_UUID}}",
  "project_name": "",
  "project_language": "",
  "current_phase": "awaiting_initialization",
  "phases": {
    "infrastructure": {
      "mcp_setup": false,
      "workflow_automation": false,
      "verification_timestamp": null
    },
    "project_initialization": {
      "requirements_discovery": false,
      "specification_generation": false,
      "plan_generation": false,
      "project_setup": false,
      "linter_configured": false,
      "completion_timestamp": null
    },
    "code_quality": {
      "linter_type": "",
      "linting_enabled": false,
      "pre_commit_hooks": false,
      "ci_integration": false,
      "last_lint_check": null,
      "suppressed_warnings": 0
    },
    "development_sessions": []
  },
  "mcp_health": {
    "last_check": null,
    "serena": "unknown",
    "context7": "unknown",
    "filesystem": "unknown",
    "github": "unknown",
    "memory": "unknown"
  },
  "quality_metrics": {
    "linting_errors": 0,
    "test_coverage": 0,
    "build_time": 0,
    "last_quality_check": null
  },
  "validation_history": [],
  "error_log": [],
  "created_files": {
    "specifications": [],
    "project_files": [],
    "automation_files": [],
    "quality_files": []
  }
}
```

**FILE 3: plan/automation/workflow-validator.md**
```markdown
# Workflow Validation System

## Automated Validation Checks

### Pre-Step Validation
```javascript
function validatePreStep(stepName) {
  // Check MCP servers
  const mcpStatus = checkMCPServers();
  if (!allServersConnected(mcpStatus)) {
    return {valid: false, error: "MCP servers not connected"};
  }
  
  // Check previous step completion
  const workflowState = loadWorkflowState();
  if (!isPreviousStepComplete(workflowState, stepName)) {
    return {valid: false, error: "Previous step incomplete"};
  }
  
  // Check required files exist
  const requiredFiles = getRequiredFiles(stepName);
  if (!allFilesExist(requiredFiles)) {
    return {valid: false, error: "Required files missing"};
  }
  
  // Check linter status (if past setup phase)
  if (stepName >= "project_setup" && !workflowState.code_quality.linting_enabled) {
    return {valid: false, error: "Linter not configured"};
  }
  
  return {valid: true};
}
```

### Post-Step Validation
```javascript
function validatePostStep(stepName, expectedOutputs) {
  // Verify all expected files created
  const createdFiles = checkCreatedFiles(expectedOutputs);
  if (!allFilesCreated(createdFiles)) {
    return {valid: false, error: "Expected files not created"};
  }
  
  // Run linting check (if applicable)
  if (workflowState.code_quality.linting_enabled) {
    const lintResult = runLintCheck();
    if (lintResult.errors > 0) {
      return {valid: false, error: `Linting errors: ${lintResult.errors}`};
    }
  }
  
  // Update workflow state
  updateWorkflowState(stepName, "completed");
  
  // Store context in memory server
  storeStepContext(stepName);
  
  return {valid: true};
}
```

### Code Quality Validation
```javascript
function validateCodeQuality() {
  // Check linter installation
  const linterInstalled = checkLinterInstallation();
  if (!linterInstalled) {
    return {valid: false, error: "Linter not installed"};
  }
  
  // Run linting
  const lintResult = executeLinter();
  updateQualityMetrics(lintResult);
  
  // Check test coverage
  const coverageResult = checkTestCoverage();
  if (coverageResult.percentage < requiredCoverage) {
    return {valid: false, error: `Coverage below ${requiredCoverage}%`};
  }
  
  return {valid: true, metrics: {
    linting: lintResult,
    coverage: coverageResult
  }};
}
```

### MCP Server Health Check
Run this before any workflow step:
```
/mcp
```
All 5 servers must show "connected"

### Recovery Procedures
1. **MCP Failure**: Restart Claude Code, verify servers
2. **File Creation Failure**: Check filesystem permissions
3. **State Corruption**: Restore from backup or reset
4. **Context Loss**: Reload from specification files
5. **Linting Failure**: Run setup-project-linter.sh
```

**FILE 4: plan/automation/quick-start.md**
```markdown
# Quick Start Guide

## First Time Setup
1. ✅ MCP Servers (Prompt #0 V2.0)
2. ✅ Workflow Automation (Prompt #0.5 V2.1 - current)

## New Project Workflow
```bash
# Start new project
Execute full project setup using prompts 1-4 in sequence.
Validate each step before proceeding.

# Commands to run in order:
1. Use prompt-1-requirements.md for requirements gathering
2. Use prompt-2-specification.md for spec generation
3. Use prompt-3-plan-generation.md for development planning
4. Use prompt-4-project-setup.md for project infrastructure
5. Verify linter setup with ./setup-project-linter.sh
```

## Daily Development
```bash
# Start work session
Use prompt-5-session-init.md to load context and verify linting

# Develop features
Use prompt-6-tdd-template.md for each feature
Replace [TASK_DESCRIPTION] with your specific task
Follow TDD with integrated linting
```

## Code Quality Checks
```bash
# Run linter
./lint.sh

# Check pre-commit hooks
.git/hooks/pre-commit

# Verify CI/CD includes linting
cat .github/workflows/ci.yml | grep lint
```

## Troubleshooting
- Check workflow-state.json for current status
- Review error_log array for issues
- Verify MCP servers with /mcp
- Check linter configuration in code_quality section
- Review plan/logs/ for detailed execution logs
```

**FILE 5: plan/automation/prompt-loader.md**
```markdown
# Prompt Loading System

## Purpose
Dynamically load and execute prompts with variable substitution, validation, and quality enforcement.

## Usage Pattern
```
Load prompt file: [PROMPT_FILE]
Substitute variables: [VARIABLE_MAP]
Execute with validation: [VALIDATION_RULES]
Enforce quality: [LINTING_CHECKS]
```

## Variable Substitution
Prompts can contain variables in format: {{VARIABLE_NAME}}
These are replaced at execution time with actual values.

## Quality Enforcement
- Pre-execution: Verify linter is configured
- During execution: Monitor for linting commands
- Post-execution: Validate code quality metrics

## Execution Flow
1. Load prompt from file
2. Replace variables
3. Run pre-validation
4. Execute prompt
5. Run quality checks
6. Run post-validation
7. Update workflow state
8. Log execution details
```

**FILE 6: plan/automation/commands.md**
```markdown
# Workflow Commands Reference

## Check System Status
```
Show current workflow state, MCP server health, and code quality metrics
```

## Execute Full Setup
```
Run complete project setup (prompts 1-4) with validation and linter configuration
```

## Execute Single Step
```
Run specific workflow step: [STEP_NAME]
```

## Validate Environment
```
Check all prerequisites, system health, and linter configuration
```

## Run Quality Check
```
Execute linting, test coverage, and code quality validation
```

## Reset Workflow
```
Reset workflow state (use with caution)
```

## View Execution Log
```
Show recent workflow execution history with quality metrics
```
```

**FILE 7: plan/quality/linting-standards.md**
```markdown
# Linting Standards and Configuration

## Project Language Detection
The workflow automatically detects project language and configures appropriate linting:

- **Python**: Ruff + mypy
- **TypeScript/JavaScript**: ESLint + Prettier
- **Go**: golangci-lint
- **Rust**: Clippy + rustfmt
- **PHP**: PHP CodeSniffer + PHPStan
- **C#**: dotnet format
- **Java**: Checkstyle
- **Clojure**: clj-kondo
- **C/C++**: clang-tidy
- **Ruby**: RuboCop
- **Kotlin**: ktlint
- **Dart**: dart analyze

## Enforcement Points

### During Development
1. After test creation
2. After implementation
3. Before commits
4. During refactoring

### In CI/CD
1. Pre-merge checks
2. Build pipeline
3. Release validation

### Quality Gates
- Zero linting errors in main branch
- Document all suppressions
- Review rules monthly
- Track metrics over time

## Integration with Workflow
- Prompt #2: Configures linting in CLAUDE.md
- Prompt #3: Adds linting to development plan
- Prompt #4: Installs and configures linter
- Prompt #5: Verifies linter on session start
- Prompt #6: Enforces linting during TDD

## Metrics Tracking
- Errors per commit
- Suppressed warnings
- Time to fix issues
- Rule violations by type
```

**STEP 3: Create Workflow Commands**

**FILE 8: plan/automation/quality-validator.sh**
```bash
#!/bin/bash

# Quality validation script for workflow automation

echo "=== Code Quality Validation ==="

# Detect project language
detect_language() {
    if [ -f "package.json" ]; then
        echo "javascript"
    elif [ -f "requirements.txt" ] || [ -f "pyproject.toml" ]; then
        echo "python"
    elif [ -f "go.mod" ]; then
        echo "go"
    elif [ -f "Cargo.toml" ]; then
        echo "rust"
    else
        echo "unknown"
    fi
}

LANGUAGE=$(detect_language)
echo "Detected language: $LANGUAGE"

# Check linter installation
check_linter() {
    case $LANGUAGE in
        javascript)
            npm list eslint &>/dev/null
            ;;
        python)
            which ruff &>/dev/null
            ;;
        go)
            which golangci-lint &>/dev/null
            ;;
        rust)
            cargo clippy --version &>/dev/null
            ;;
        *)
            return 1
            ;;
    esac
}

if check_linter; then
    echo "✅ Linter installed"
else
    echo "❌ Linter not installed"
    exit 1
fi

# Run linting
echo "Running linter..."
if [ -f "./lint.sh" ]; then
    ./lint.sh
else
    case $LANGUAGE in
        javascript) npm run lint ;;
        python) ruff check . ;;
        go) golangci-lint run ;;
        rust) cargo clippy ;;
    esac
fi

LINT_EXIT=$?

# Update workflow state
if [ $LINT_EXIT -eq 0 ]; then
    echo "✅ Linting passed"
    # Update workflow-state.json
else
    echo "❌ Linting failed"
    exit 1
fi

# Check test coverage
echo "Checking test coverage..."
case $LANGUAGE in
    javascript) npm run test:coverage ;;
    python) pytest --cov ;;
    go) go test -cover ./... ;;
    rust) cargo test ;;
esac

echo "=== Quality validation complete ==="
```

Make script executable:
```bash
chmod +x plan/automation/quality-validator.sh
```

**STEP 4: Initialize Workflow State**
After creating all files, initialize the workflow system:

1. Update workflow-state.json with current timestamp
2. Set mcp_setup = true
3. Set workflow_automation = true (in progress)
4. Run MCP health check and update status
5. Initialize code_quality section

**STEP 5: Final Validation**
Confirm all automation files created:
- [ ] plan/automation/workflow-executor.md
- [ ] plan/automation/workflow-state.json
- [ ] plan/automation/workflow-validator.md
- [ ] plan/automation/quick-start.md
- [ ] plan/automation/prompt-loader.md
- [ ] plan/automation/commands.md
- [ ] plan/quality/linting-standards.md
- [ ] plan/automation/quality-validator.sh

**STEP 6: Create Prompt File References**
Create references to the actual prompt files (which should already exist):
- plan/prompts/prompt-1-requirements.md
- plan/prompts/prompt-2-specification.md (V3.1 with linting)
- plan/prompts/prompt-3-plan-generation.md (V2.1 with linting)
- plan/prompts/prompt-4-project-setup.md (V2.1 with auto-linter)
- plan/prompts/prompt-5-session-init.md (V2.1 with linter verification)
- plan/prompts/prompt-6-tdd-template.md (V2.1 with integrated linting)

**SUCCESS CRITERIA:**
- All automation files created via filesystem server
- Workflow state initialized and tracking enabled
- Code quality enforcement integrated
- MCP servers verified as connected
- Linting standards documented
- Quality validation automated
- Ready to execute automated workflow sequences with code quality gates

The workflow automation system is now ready with integrated code quality enforcement. You can proceed with the development workflow using the automated execution commands while maintaining high code standards.
```