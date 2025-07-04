# Prompt #3 V2.0: Claude Code Plan Generation with TDD

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Generate a comprehensive development plan using Claude Code's /plan command with strict TDD methodology and better task granularity

**Usage**: Run this after specification generation (Prompt #2 V3.0). Uses Claude Code's planning feature with TDD enhancement.

```
Generate a comprehensive development plan for this project using Claude Code's /plan command, then enhance it with strict TDD methodology and MCP server integration.

**STEP 1: Generate Base Plan**
First, enter Claude Code's plan mode:

Press **Shift+Tab** to enter plan mode, then type:
Create a comprehensive development plan for this project

This will generate an initial development roadmap based on the specification.

**STEP 2: Enhance Plan with TDD Requirements**
After the base plan generates, enhance EVERY development task to follow strict TDD methodology:

**TDD ENHANCEMENT TEMPLATE:**
For each feature/component in the plan, restructure as:

### [Feature Name]
1. **Write Failing Tests** (Red Phase)
   - [ ] Create test file: [name].test.ts
   - [ ] Write unit tests for [specific behavior]
   - [ ] Write integration tests for [API/service]
   - [ ] Verify all tests fail appropriately
   - [ ] Time estimate: [X hours]

2. **Implement Minimal Code** (Green Phase)
   - [ ] Create implementation file: [name].ts
   - [ ] Write ONLY enough code to pass tests
   - [ ] No extra features or optimizations
   - [ ] Run tests and verify they pass
   - [ ] Time estimate: [X hours]

3. **Refactor and Optimize** (Refactor Phase)
   - [ ] Improve code structure
   - [ ] Extract common patterns
   - [ ] Add documentation
   - [ ] Ensure tests still pass
   - [ ] Time estimate: [X hours]

4. **Integration Testing**
   - [ ] Test with existing components
   - [ ] Verify API contracts
   - [ ] Update integration test suite
   - [ ] Time estimate: [X hours]

**STEP 3: Add MCP Server Tasks**
Enhance the plan with specific MCP server utilization:

### Code Quality Tasks (Serena)
- [ ] Analyze codebase structure with Serena
- [ ] Identify refactoring opportunities
- [ ] Find and fix code smells
- [ ] Symbol-level dependency analysis

### Documentation Tasks (Context7)
- [ ] Research best practices with "use context7"
- [ ] Find implementation examples
- [ ] Update documentation with findings
- [ ] Create API documentation

### Version Control Tasks (GitHub)
- [ ] Create feature branches
- [ ] Set up PR templates
- [ ] Configure branch protection
- [ ] Automate PR checks

### Context Preservation (Memory)
- [ ] Store architectural decisions
- [ ] Track implementation choices
- [ ] Document gotchas and solutions
- [ ] Maintain session continuity

**STEP 4: Create Granular Task Breakdown**
Break down into specific, measurable tasks:

## Phase 1: Foundation (Week 1)
### Day 1-2: Environment Setup
- [ ] Initialize repository with GitHub server
- [ ] Configure TypeScript with strict mode
- [ ] Set up testing framework (Jest/Vitest)
- [ ] Create initial file structure
- [ ] Configure linting and formatting
- [ ] Set up pre-commit hooks
- [ ] Write tests for configuration validation

### Day 3-4: Core Architecture
- [ ] TEST: Core service interfaces
- [ ] IMPLEMENT: Base service classes
- [ ] TEST: Dependency injection
- [ ] IMPLEMENT: DI container
- [ ] TEST: Error handling
- [ ] IMPLEMENT: Error classes
- [ ] REFACTOR: Extract common patterns

### Day 5: CI/CD Pipeline
- [ ] TEST: Build process
- [ ] IMPLEMENT: Build scripts
- [ ] TEST: Deployment process
- [ ] IMPLEMENT: Deployment scripts
- [ ] Configure GitHub Actions
- [ ] Add test coverage reporting

## Phase 2: Core Features (Weeks 2-4)
[Continue with similar detail for each feature]

**STEP 5: Add Monitoring and Metrics**
Include measurable progress indicators:

### Testing Metrics
- [ ] Maintain >80% code coverage
- [ ] All tests run in <30 seconds
- [ ] Zero failing tests in main branch
- [ ] Integration tests for all APIs

### Code Quality Metrics  
- [ ] Zero linting errors
- [ ] No TypeScript errors
- [ ] Consistent code formatting
- [ ] All functions documented

### Development Velocity
- [ ] Track completed tasks per day
- [ ] Monitor test-to-code ratio
- [ ] Measure PR review time
- [ ] Document blockers

**STEP 6: Risk Mitigation Tasks**
Add specific tasks to address identified risks:

### Technical Risks
- [ ] Spike: Research [unknown technology]
- [ ] Prototype: Test [risky integration]
- [ ] Fallback: Plan B for [dependency]

### Process Risks
- [ ] Document setup procedures
- [ ] Create onboarding guide
- [ ] Establish code review process
- [ ] Define "done" criteria

**STEP 7: Create Development Artifacts**
Generate supporting files:

1. **development-plan.md**: Full enhanced plan
2. **tdd-checklist.md**: TDD verification for each feature
3. **milestone-tracker.md**: Progress tracking
4. **risk-register.md**: Risk monitoring

**VERIFICATION CHECKLIST:**
- [ ] Every feature has test-first tasks
- [ ] Time estimates are realistic
- [ ] Dependencies are identified
- [ ] MCP servers utilized throughout
- [ ] Metrics are measurable
- [ ] Risks have mitigation tasks

The enhanced plan ensures strict TDD methodology while leveraging all available tools for maximum development efficiency.
```