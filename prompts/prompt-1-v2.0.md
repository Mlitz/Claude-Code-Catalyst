# Prompt #0.5 V2.0: Automated Workflow Setup

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Create a robust automated workflow system with better error handling and state management

**Usage**: Run this after MCP setup (Prompt #0 V2.0) to build the workflow automation framework. Creates all necessary files for sequential execution.

```
I'll create an automated workflow system for the 8-prompt development process. This system will track progress, validate steps, and ensure proper execution order.

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

**STEP 2: Create Core Workflow Files**

**FILE 1: plan/automation/workflow-executor.md**
```markdown
# Automated Workflow Executor

## System Overview
This executor manages the 8-prompt AI development workflow with automatic validation and error recovery.

### Prompt Execution Order
0. **MCP Setup** - Infrastructure configuration (manual)
0.5. **Workflow Setup** - Automation framework (manual)
1. **Requirements** - Interactive discovery session
2. **Specification** - Document generation
3. **Planning** - Development roadmap with TDD
4. **Project Setup** - Infrastructure and todos
5. **Session Init** - Daily startup routine
6. **TDD Template** - Feature development (reusable)

### Execution Modes

#### Full Project Setup (Prompts 1-4)
```
Execute complete project initialization sequence:
1. Load and run prompt-1-requirements.md
2. Validate outputs: spec outline created
3. Load and run prompt-2-specification.md  
4. Validate outputs: spec.md, claude.md, work-journal.md exist
5. Load and run prompt-3-plan-generation.md
6. Validate outputs: development plan created
7. Load and run prompt-4-project-setup.md
8. Validate outputs: todo.md, project structure established
```

#### Daily Development (Prompts 5-6)
```
Execute development session:
1. Load and run prompt-5-session-init.md
2. Validate: context loaded, priorities identified
3. For each development task:
   - Load prompt-6-tdd-template.md
   - Replace [TASK_DESCRIPTION] with specific task
   - Execute with TDD enforcement
   - Validate: tests written first, all tests pass
```

### Validation Gates
Each step must pass validation before proceeding:
- Required files created via filesystem server
- No error messages in execution
- Workflow state updated successfully
- Memory server contains step context
```

**FILE 2: plan/automation/workflow-state.json**
```json
{
  "version": "2.0.0",
  "workflow_id": "{{GENERATE_UUID}}",
  "project_name": "",
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
      "completion_timestamp": null
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
  "validation_history": [],
  "error_log": [],
  "created_files": {
    "specifications": [],
    "project_files": [],
    "automation_files": []
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
  
  // Update workflow state
  updateWorkflowState(stepName, "completed");
  
  // Store context in memory server
  storeStepContext(stepName);
  
  return {valid: true};
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
```

**FILE 4: plan/automation/quick-start.md**
```markdown
# Quick Start Guide

## First Time Setup
1. ✅ MCP Servers (Prompt #0 V2.0)
2. ✅ Workflow Automation (Prompt #0.5 V2.0 - current)

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
```

## Daily Development
```bash
# Start work session
Use prompt-5-session-init.md to load context

# Develop features
Use prompt-6-tdd-template.md for each feature
Replace [TASK_DESCRIPTION] with your specific task
```

## Troubleshooting
- Check workflow-state.json for current status
- Review error_log array for issues
- Verify MCP servers with /mcp
- Check plan/logs/ for detailed execution logs
```

**FILE 5: plan/automation/prompt-loader.md**
```markdown
# Prompt Loading System

## Purpose
Dynamically load and execute prompts with variable substitution and validation.

## Usage Pattern
```
Load prompt file: [PROMPT_FILE]
Substitute variables: [VARIABLE_MAP]
Execute with validation: [VALIDATION_RULES]
```

## Variable Substitution
Prompts can contain variables in format: {{VARIABLE_NAME}}
These are replaced at execution time with actual values.

## Execution Flow
1. Load prompt from file
2. Replace variables
3. Run pre-validation
4. Execute prompt
5. Run post-validation
6. Update workflow state
7. Log execution details
```

**STEP 3: Create Workflow Commands**

**FILE 6: plan/automation/commands.md**
```markdown
# Workflow Commands Reference

## Check System Status
```
Show current workflow state and MCP server health
```

## Execute Full Setup
```
Run complete project setup (prompts 1-4) with validation
```

## Execute Single Step
```
Run specific workflow step: [STEP_NAME]
```

## Validate Environment
```
Check all prerequisites and system health
```

## Reset Workflow
```
Reset workflow state (use with caution)
```

## View Execution Log
```
Show recent workflow execution history
```
```

**STEP 4: Initialize Workflow State**
After creating all files, initialize the workflow system:

1. Update workflow-state.json with current timestamp
2. Set mcp_setup = true
3. Set workflow_automation = true (in progress)
4. Run MCP health check and update status

**STEP 5: Final Validation**
Confirm all automation files created:
- [ ] plan/automation/workflow-executor.md
- [ ] plan/automation/workflow-state.json
- [ ] plan/automation/workflow-validator.md
- [ ] plan/automation/quick-start.md
- [ ] plan/automation/prompt-loader.md
- [ ] plan/automation/commands.md

**STEP 6: Create Prompt File References**
Create references to the actual prompt files (which should already exist):
- plan/prompts/prompt-1-requirements.md
- plan/prompts/prompt-2-specification.md
- plan/prompts/prompt-3-plan-generation.md
- plan/prompts/prompt-4-project-setup.md
- plan/prompts/prompt-5-session-init.md
- plan/prompts/prompt-6-tdd-template.md

**SUCCESS CRITERIA:**
- All automation files created via filesystem server
- Workflow state initialized and tracking enabled
- MCP servers verified as connected
- Ready to execute automated workflow sequences

The workflow automation system is now ready. You can proceed with the development workflow using the automated execution commands.
```