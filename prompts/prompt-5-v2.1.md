# Prompt #5 V2.1: Development Session Initialization with Linter Verification

**Version**: 2.1
**Last Updated**: January 2025
**Purpose**: Start each development session with comprehensive context loading, health checks, linter verification, and session preparation

**Usage**: Run this at the beginning of EVERY Claude Code session to ensure continuity and proper setup.

```
Welcome back! I'll initialize your development session with full context loading and system verification.

**STEP 1: System Health Check**

### MCP Server Status
```bash
/mcp
```

**Expected Output:**
```
Available MCP servers:
- serena: connected ✅
- context7: connected ✅
- memory: connected ✅
- filesystem: connected ✅
- github: connected ✅
```

**If any server shows disconnected:**
1. Exit Claude Code completely
2. Wait 10 seconds
3. Restart Claude Code
4. Run `/mcp` again
5. If issues persist, return to Prompt #0 V2.0

### Export Tool Check
```bash
claude-prompts --list
```
This should show available sessions. If not found, install:
```bash
npm install -g claude-code-exporter
```

**STEP 2: Context Recovery**

### Load Core Documentation
Using filesystem server, I'll load and summarize:

1. **Project Specification (spec.md)**
   - Project goals and objectives
   - Technical architecture
   - Key requirements
   - Success metrics

2. **AI Context (CLAUDE.md)**
   - Coding standards
   - TDD requirements
   - Linting requirements
   - Security constraints
   - MCP usage patterns

3. **Work Journal (work-journal.md)**
   - Last session summary
   - Recent decisions
   - Current challenges
   - Next priorities

4. **Development Plan (development-plan.md)**
   - Current phase
   - Milestone progress
   - Upcoming deadlines
   - Risk factors

5. **Todo Status (todo.md)**
   - Completed tasks count
   - In-progress items
   - Blocked tasks
   - Next priorities

### Memory Server Context
Retrieve stored context:
- Previous session objectives
- Unresolved issues
- Important decisions
- Implementation notes

**STEP 3: Repository Status**

### Git Status Check
Using GitHub server:
```bash
# Current branch
git branch --show-current

# Uncommitted changes
git status --short

# Recent commits
git log --oneline -5

# Upstream status
git fetch --dry-run
```

### Dependency Check
```bash
# Verify dependencies are current
npm list --depth=0

# Check for updates (don't install)
npm outdated
```

**STEP 4: Environment Validation**

### Configuration Check
- [ ] .env file exists and is populated
- [ ] All required environment variables set
- [ ] No sensitive data in tracked files

### Development Tools
```bash
# TypeScript compiler (if applicable)
npx tsc --version

# Test runner
npx jest --version

# Check project-specific linter
if [ -f "./lint.sh" ]; then
    echo "Project linter: ✅"
    ./lint.sh --version 2>/dev/null || echo "Linter configured"
elif [ -f "package.json" ] && grep -q "\"lint\":" package.json; then
    echo "NPM lint command: ✅"
else
    echo "⚠️  No linter configured - run setup-project-linter.sh"
fi
```

### Linter Health Check
```bash
# Quick lint check to ensure it's working
echo "Running linter health check..."

# Try to run the linter
if [ -f "./lint.sh" ]; then
    ./lint.sh 2>&1 | head -10
elif [ -f "package.json" ] && grep -q "\"lint\":" package.json; then
    npm run lint 2>&1 | head -10
else
    echo "⚠️  Linter not found - this may impact code quality"
fi

# Check for pre-commit hooks
if [ -f ".git/hooks/pre-commit" ]; then
    echo "Pre-commit hooks: ✅"
else
    echo "⚠️  No pre-commit hooks - linting won't run automatically"
fi
```

**STEP 5: Code Quality Status**

### Coverage Report
```bash
# Check current test coverage
if [ -f "coverage/coverage-summary.json" ]; then
    echo "Last coverage report found"
    # Extract coverage percentage
fi
```

### Outstanding Linting Issues
```bash
# Check for any ignored linting rules
grep -r "eslint-disable\|pylint: disable\|@ts-ignore" src/ 2>/dev/null | wc -l
echo "Suppressed linting warnings found"
```

**STEP 6: Session Intelligence Report**

## 📊 Session Status Report

### Project Overview
**Project**: [Name]
**Phase**: [Current Phase]
**Sprint**: [Week X of Y]
**Health**: [🟢 Good | 🟡 Attention Needed | 🔴 Critical]

### Progress Metrics
- **Overall Completion**: [X]% ([Y] of [Z] tasks)
- **Current Phase**: [X]% complete
- **Test Coverage**: [X]%
- **Linting Status**: [✅ Clean | ⚠️ Issues | ❌ Not configured]
- **Technical Debt**: [Low/Medium/High]

### Code Quality Indicators
- **Linter**: [Detected linter type]
- **Last Lint Run**: [Timestamp if available]
- **Suppressed Warnings**: [Count]
- **Pre-commit Hooks**: [Active/Inactive]

### Today's Focus
**Primary Objective**: [Main goal for this session]
**Priority Tasks**:
1. [Task 1 - Time estimate]
2. [Task 2 - Time estimate]
3. [Task 3 - Time estimate]

**Quality Reminders**:
- [ ] Run linter before each commit
- [ ] Write tests first (TDD)
- [ ] Check coverage after implementation

**Blocked Items**: [List any blockers]

### Recent Activity
**Last Session**: [Date]
**Completed**:
- [Achievement 1]
- [Achievement 2]

**Decisions Made**:
- [Decision 1 and rationale]
- [Decision 2 and rationale]

### Upcoming Milestones
- [ ] [Milestone 1] - Due: [Date]
- [ ] [Milestone 2] - Due: [Date]

**STEP 7: Session Configuration**

### Quality Commitment
✅ **I acknowledge and will enforce:**
- Tests MUST be written first
- Linting MUST pass before commits
- No implementation without failing tests
- Full test suite must pass before commits
- Coverage must not decrease

### MCP Server Assignments
For today's work, I'll use:
- **Serena**: [Planned usage]
- **Context7**: [When I'll need docs]
- **Filesystem**: All file operations
- **GitHub**: [Branch strategy]
- **Memory**: [What to preserve]

### Quality Standards
- [ ] Follow coding standards in CLAUDE.md
- [ ] Run linter after each implementation
- [ ] Maintain project structure
- [ ] Update documentation
- [ ] Write meaningful commits

### Pre-Session Checklist
- [ ] All MCP servers connected
- [ ] Linter is functional
- [ ] No uncommitted changes (or they're intentional)
- [ ] Tests are passing
- [ ] Ready to write tests first

**STEP 8: Session Initialization Complete**

## ✅ Ready for Development

**Session ID**: [Generated UUID]
**Started**: [Timestamp]
**Mode**: TDD Enforced + Linting Active
**Next Action**: [Specific next step]

### Quick Commands
```bash
# Run tests
npm test

# Start development
npm run dev

# Check linting
./lint.sh  # or npm run lint

# Run tests in watch mode
npm run test:watch

# Type checking (if applicable)
npm run type-check
```

### Session Workflow Reminder
1. Pick task from todo.md
2. Write failing test FIRST
3. Run test to verify failure
4. Implement minimal solution
5. **Run linter and fix issues**
6. Run tests to verify pass
7. Refactor if needed
8. **Final lint check**
9. Commit with good message

### Quality Gates
Before ANY commit:
```bash
# 1. Run tests
npm test

# 2. Run linter
./lint.sh

# 3. Check coverage
npm run test:coverage

# All must pass!
```

### Session Plan
1. [First 30 minutes]: [Task]
2. [Next hour]: [Task]
3. [Following hour]: [Task]
4. [End of session]: Update journal & export

### Reminders
- 🧪 Write tests first
- 🧹 Lint before every commit
- 📝 Update todo.md as you progress
- 💾 Commit frequently with good messages
- 📚 Document decisions in work-journal.md
- 🔄 Export conversation before ending

**READY TO START**: Which task would you like to tackle first?

---

**Note**: If linting is not configured, run `./setup-project-linter.sh` from Prompt #4 V2.1 before proceeding with development.
```