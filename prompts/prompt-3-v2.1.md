# Prompt #3 V2.1: Claude Code Plan Generation with TDD and Linting

**Version**: 2.1
**Last Updated**: January 2025
**Purpose**: Generate a comprehensive development plan using Claude Code's /plan command with strict TDD methodology, MCP server integration, and code quality enforcement through linting

**Usage**: Run this after specification generation (Prompt #2 V3.1). Uses Claude Code's planning feature with TDD and linting enhancement.

```
Generate a comprehensive development plan for this project using Claude Code's /plan command, then enhance it with strict TDD methodology, linting standards, and MCP server integration.

**STEP 1: Generate Base Plan**
First, enter Claude Code's plan mode:

Press **Shift+Tab** to enter plan mode, then type:
Create a comprehensive development plan for this project

This will generate an initial development roadmap based on the specification.

**STEP 2: Enhance Plan with TDD and Linting Requirements**
After the base plan generates, enhance EVERY development task to follow strict TDD methodology with integrated linting:

**TDD + LINTING ENHANCEMENT TEMPLATE:**
For each feature/component in the plan, restructure as:

### [Feature Name]
1. **Setup Code Quality Tools** (Pre-Development)
   - [ ] Verify linter is configured (run setup-project-linter.sh if needed)
   - [ ] Configure pre-commit hooks
   - [ ] Set up editor integration for real-time linting
   - [ ] Establish team linting standards
   - [ ] Time estimate: [X hours]

2. **Write Failing Tests** (Red Phase)
   - [ ] Create test file: [name].test.ts
   - [ ] Write unit tests for [specific behavior]
   - [ ] Write integration tests for [API/service]
   - [ ] **Lint test files** to ensure quality
   - [ ] Verify all tests fail appropriately
   - [ ] Time estimate: [X hours]

3. **Implement Minimal Code** (Green Phase)
   - [ ] Create implementation file: [name].ts
   - [ ] Write ONLY enough code to pass tests
   - [ ] **Run linter after each passing test**
   - [ ] Fix linting issues immediately
   - [ ] No extra features or optimizations
   - [ ] Run tests and verify they pass
   - [ ] Time estimate: [X hours]

4. **Refactor and Optimize** (Refactor Phase)
   - [ ] Improve code structure
   - [ ] Extract common patterns
   - [ ] **Apply linter auto-fix suggestions**
   - [ ] Add documentation
   - [ ] **Final linting check**
   - [ ] Ensure tests still pass
   - [ ] Time estimate: [X hours]

5. **Integration Testing with Quality Gates**
   - [ ] Test with existing components
   - [ ] Verify API contracts
   - [ ] **Lint all integration code**
   - [ ] Update integration test suite
   - [ ] Run full test coverage report
   - [ ] Time estimate: [X hours]

**STEP 3: Add Code Quality Enforcement Tasks**
Enhance the plan with specific code quality checkpoints:

### Linting Integration Tasks
- [ ] **Phase 0: Initial Setup**
  - [ ] Run setup-project-linter.sh
  - [ ] Verify language-specific linter installed
  - [ ] Configure linting rules per team standards
  - [ ] Set up CI/CD linting stage

- [ ] **Per-Sprint Quality Gates**
  - [ ] Zero linting errors before sprint close
  - [ ] Document any suppressed warnings
  - [ ] Review and update linting rules
  - [ ] Track linting metrics

### MCP Server Tasks with Linting
- [ ] **Serena Code Quality Analysis**
  - [ ] Run Serena on codebase before major refactoring
  - [ ] Compare Serena findings with linter results
  - [ ] Address code smells identified by both tools
  - [ ] Document improvement decisions

**STEP 4: Create Granular Task Breakdown with Quality Checks**
Break down into specific, measurable tasks:

## Phase 1: Foundation (Week 1)
### Day 1-2: Environment Setup
- [ ] Initialize repository with GitHub server
- [ ] Configure TypeScript with strict mode
- [ ] **Set up project linter (./setup-project-linter.sh)**
- [ ] Set up testing framework (Jest/Vitest)
- [ ] **Configure pre-commit hooks for linting**
- [ ] Create initial file structure
- [ ] **Run initial lint check on boilerplate**
- [ ] Configure formatting rules
- [ ] Set up pre-commit hooks
- [ ] Write tests for configuration validation

### Day 3-4: Core Architecture
- [ ] TEST: Core service interfaces
- [ ] **LINT: Test files**
- [ ] IMPLEMENT: Base service classes
- [ ] **LINT: Implementation files**
- [ ] TEST: Dependency injection
- [ ] IMPLEMENT: DI container
- [ ] **LINT: All new code**
- [ ] TEST: Error handling
- [ ] IMPLEMENT: Error classes
- [ ] REFACTOR: Extract common patterns
- [ ] **FINAL LINT: Entire module**

### Day 5: CI/CD Pipeline with Quality Gates
- [ ] TEST: Build process
- [ ] IMPLEMENT: Build scripts
- [ ] **Add linting stage to CI/CD**
- [ ] TEST: Deployment process
- [ ] IMPLEMENT: Deployment scripts
- [ ] Configure GitHub Actions with:
  - [ ] Linting check (must pass)
  - [ ] Test execution (100% pass rate)
  - [ ] Coverage reporting (maintain threshold)
- [ ] Add status badges to README

## Phase 2: Core Features (Weeks 2-4)
### Feature Development Pattern
For EACH feature, follow this pattern:
1. **Quality Setup** (30 min)
   - [ ] Review linting standards for feature type
   - [ ] Set up feature-specific test utilities
   - [ ] Configure mocks and fixtures

2. **TDD Cycle** (Per component)
   - [ ] Write failing test
   - [ ] Lint test file
   - [ ] Implement minimal code
   - [ ] Lint implementation
   - [ ] Refactor if needed
   - [ ] Final quality check

3. **Integration** (1 hour)
   - [ ] Connect to existing system
   - [ ] Lint all modified files
   - [ ] Run full test suite
   - [ ] Check coverage hasn't decreased

**STEP 5: Add Monitoring and Metrics**
Include measurable progress indicators:

### Code Quality Metrics
- [ ] Maintain zero linting errors
- [ ] Track suppressed warnings (target: < 5)
- [ ] Monitor linting time (target: < 30s)
- [ ] Review linting rules monthly
- [ ] Document linting exceptions

### Testing Metrics with Quality
- [ ] Maintain >80% code coverage
- [ ] All tests run in <30 seconds
- [ ] Zero failing tests in main branch
- [ ] Integration tests for all APIs
- [ ] **All code passes linting before merge**

### Development Velocity
- [ ] Track completed tasks per day
- [ ] Monitor test-to-code ratio
- [ ] **Track linting fixes per PR**
- [ ] Measure PR review time
- [ ] Document blockers

**STEP 6: Risk Mitigation Tasks**
Add specific tasks to address identified risks:

### Code Quality Risks
- [ ] Technical Debt: Schedule regular linting rule updates
- [ ] Legacy Code: Plan incremental linting adoption
- [ ] Team Adoption: Create linting workshop/documentation

### Technical Risks
- [ ] Spike: Research [unknown technology]
- [ ] **Ensure linting support for new tech**
- [ ] Prototype: Test [risky integration]
- [ ] Fallback: Plan B for [dependency]

### Process Risks
- [ ] Document linting standards
- [ ] Create onboarding guide with linting setup
- [ ] Establish code review process including linting
- [ ] Define "done" criteria (includes passing lint)

**STEP 7: Create Development Artifacts**
Generate supporting files:

1. **development-plan.md**: Full enhanced plan with linting
2. **tdd-checklist.md**: TDD verification including lint steps
3. **code-quality-standards.md**: Linting rules and exceptions
4. **milestone-tracker.md**: Progress tracking with quality metrics
5. **risk-register.md**: Risk monitoring including technical debt

**STEP 8: Quality Enforcement Checkpoints**
Add these to every sprint/milestone:

### Sprint Start Checklist
- [ ] Verify linter is working
- [ ] Update linting rules if needed
- [ ] Review previous sprint's linting metrics
- [ ] Set quality goals for sprint

### Sprint End Checklist
- [ ] Zero linting errors in all code
- [ ] Document any new suppressions
- [ ] Update team on linting changes
- [ ] Plan improvements for next sprint

### Release Quality Gates
- [ ] Full codebase lint check
- [ ] No suppressed warnings without documentation
- [ ] Linting performance acceptable
- [ ] All tests pass with coverage targets met

**VERIFICATION CHECKLIST:**
- [ ] Every feature has test-first tasks
- [ ] **Linting integrated at every step**
- [ ] Time estimates are realistic
- [ ] Dependencies are identified
- [ ] MCP servers utilized throughout
- [ ] **Quality metrics include linting**
- [ ] Metrics are measurable
- [ ] Risks have mitigation tasks
- [ ] **CI/CD includes linting stage**

The enhanced plan ensures strict TDD methodology with integrated code quality enforcement through linting, while leveraging all available tools for maximum development efficiency and maintainability.
```