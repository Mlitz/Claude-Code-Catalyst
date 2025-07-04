# Prompt #5 V2.0: Development Session Initialization

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Start each development session with comprehensive context loading, health checks, and session preparation

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

2. **AI Context (claude.md)**
   - Coding standards
   - TDD requirements
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
# TypeScript compiler
npx tsc --version

# Test runner
npx jest --version

# Linter
npx eslint --version
```

**STEP 5: Session Intelligence Report**

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
- **Technical Debt**: [Low/Medium/High]

### Today's Focus
**Primary Objective**: [Main goal for this session]
**Priority Tasks**:
1. [Task 1 - Time estimate]
2. [Task 2 - Time estimate]
3. [Task 3 - Time estimate]

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

**STEP 6: Session Configuration**

### TDD Commitment
✅ **I acknowledge and will enforce:**
- Tests MUST be written first
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
- [ ] Follow coding standards in claude.md
- [ ] Maintain project structure
- [ ] Update documentation
- [ ] Write meaningful commits

**STEP 7: Session Initialization Complete**

## ✅ Ready for Development

**Session ID**: [Generated UUID]
**Started**: [Timestamp]
**Mode**: TDD Enforced
**Next Action**: [Specific next step]

### Quick Commands
```bash
# Run tests
npm test

# Start development
npm run dev

# Check linting
npm run lint

# Type checking
npm run type-check
```

### Session Plan
1. [First 30 minutes]: [Task]
2. [Next hour]: [Task]
3. [Following hour]: [Task]
4. [End of session]: Update journal & export

### Reminders
- 🧪 Write tests first
- 📝 Update todo.md as you progress
- 💾 Commit frequently with good messages
- 📚 Document decisions in work-journal.md
- 🔄 Export conversation before ending

**READY TO START**: Which task would you like to tackle first?

---

**Note**: If this is your first session, some files may not exist yet. That's okay - we'll create them as needed.