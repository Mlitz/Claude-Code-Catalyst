# Claude Code Catalyst - Quick Reference

## 🚀 Quick Start Commands

### Initial Setup (One-time)
```bash
# 1. Copy prompts/00-mcp-server-setup.md content into Claude Code
# 2. Copy prompts/01-automated-workflow-setup.md content into Claude Code
```

### New Project Workflow
```bash
# 3. Requirements: prompts/02-interactive-requirements-discovery.md
# 4. Specification: prompts/03-comprehensive-specification-generation.md  
# 5. Planning: prompts/04-claude-code-plan-generation.md
# 6. Setup: prompts/05-project-setup-todo-management.md
```

### Daily Development
```bash
# Session Start: prompts/06-development-session-initialization.md
# Feature Development: prompts/07-tdd-enforcement-template.md
```

## 📋 Prompt Sequence

| Step | Prompt File | Purpose | Duration |
|------|------------|---------|----------|
| 0 | `00-mcp-server-setup.md` | Configure MCP servers | 15-30 min |
| 0.5 | `01-automated-workflow-setup.md` | Setup automation | 10-15 min |
| 1 | `02-interactive-requirements-discovery.md` | Gather requirements | 30-60 min |
| 2 | `03-comprehensive-specification-generation.md` | Create specifications | 30-45 min |
| 3 | `04-claude-code-plan-generation.md` | Generate development plan | 20-30 min |
| 4 | `05-project-setup-todo-management.md` | Setup project infrastructure | 15-20 min |
| 5 | `06-development-session-initialization.md` | Daily session start | 5-10 min |
| 6 | `07-tdd-enforcement-template.md` | Feature development | Variable |

## 🧪 TDD Checklist

- [ ] ❌ **RED**: Write failing test first
- [ ] ✅ **GREEN**: Implement minimal code to pass
- [ ] 🔄 **REFACTOR**: Improve code quality
- [ ] 📋 **INTEGRATE**: Connect to system
- [ ] 📚 **DOCUMENT**: Update documentation

## 🛠️ MCP Server Commands

### Check Status
```bash
/mcp
```

### Server Usage
- **Serena**: `"Analyze [code] with Serena for [purpose]"`
- **Context7**: `"use context7 to find [topic] documentation"`
- **Memory**: `"Remember: [important decision/context]"`
- **Filesystem**: Used automatically for file operations
- **GitHub**: Used automatically for version control

## 🚨 Troubleshooting

### MCP Servers Disconnected
1. Exit Claude Code completely
2. Wait 10 seconds  
3. Restart Claude Code
4. Run `/mcp` to verify

### Tests Failing
```bash
npm test
npm run lint
npm run type-check
```

### Context Lost
- Use Session Initialization prompt
- Check work-journal.md
- Review memory server content

## 📁 Generated File Structure

```
your-project/
├── spec.md              # Technical specification
├── CLAUDE.md            # AI development context
├── todo.md              # Dynamic task tracking
├── work-journal.md      # Development journal
├── src/                 # Source code
├── tests/               # Test files
└── docs/                # Documentation
```

## 🎯 Quality Standards

- **Test Coverage**: 100% required
- **TDD**: Tests written first, always
- **Linting**: Zero errors
- **Type Safety**: Strict TypeScript
- **Security**: No secrets in code
- **Documentation**: Comprehensive and current