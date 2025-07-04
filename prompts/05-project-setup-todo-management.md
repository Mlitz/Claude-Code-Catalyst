# Prompt #4 V2.0: Project Setup & Todo Management

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Create comprehensive project infrastructure with enhanced organization and automation capabilities

**Usage**: Use after development plan generation (Prompt #3 V2.0). This establishes complete project management infrastructure.

```
I'll create a comprehensive project management system using our MCP servers. This includes todo tracking, documentation, automation setup, and project infrastructure.

**PREREQUISITE CHECK:**
First, verify required files exist:
- spec.md (from Prompt #2 V3.0)
- claude.md (from Prompt #2 V3.0)
- development-plan.md (from Prompt #3 V2.0)
- work-journal.md (ongoing)

**STEP 1: Initialize Git Repository**
Set up version control foundation:

```bash
# Initialize repository
git init

# Create main branch
git checkout -b main

# Verify GitHub MCP server
/mcp
```

Confirm "github: connected" before proceeding.

**STEP 2: Create Core Project Files**

**FILE 1: todo.md**
Dynamic task tracking with phase-based organization:

```markdown
# [Project Name] Development Checklist

## 🎯 Quick Stats
- **Total Tasks**: [Count]
- **Completed**: [Count] ([Percentage]%)
- **In Progress**: [Count]
- **Blocked**: [Count]

## Phase 0: Environment Setup ✅
- [x] MCP servers installed and verified
- [x] Workflow automation created (Prompt #0.5 V2.0)
- [x] Project specification completed
- [x] Development plan generated
- [x] Export tool configured

## Phase 1: Project Foundation
### Week 1 Goals
- [ ] Repository structure created
- [ ] Development environment configured
  - [ ] TypeScript with strict mode
  - [ ] ESLint + Prettier setup
  - [ ] Jest/Vitest configuration
  - [ ] Pre-commit hooks (Husky)
- [ ] CI/CD pipeline foundation
  - [ ] GitHub Actions workflow
  - [ ] Automated testing
  - [ ] Code coverage reporting
- [ ] Docker configuration
  - [ ] Development Dockerfile
  - [ ] docker-compose setup
- [ ] Documentation structure
  - [ ] API documentation setup
  - [ ] Architecture diagrams

## Phase 2: Core Infrastructure (TDD)
### Authentication & Security
- [ ] TEST: Authentication service specs
- [ ] IMPLEMENT: JWT token management
- [ ] TEST: Authorization middleware
- [ ] IMPLEMENT: Role-based access
- [ ] REFACTOR: Security hardening

### Database Layer
- [ ] TEST: Database connection specs
- [ ] IMPLEMENT: Connection pooling
- [ ] TEST: Migration system
- [ ] IMPLEMENT: Schema migrations
- [ ] TEST: Repository patterns
- [ ] IMPLEMENT: Data access layer

### API Foundation
- [ ] TEST: Base controller specs
- [ ] IMPLEMENT: RESTful controllers
- [ ] TEST: Validation middleware
- [ ] IMPLEMENT: Request validation
- [ ] TEST: Error handling
- [ ] IMPLEMENT: Global error handler

## Phase 3: Feature Development (TDD)
[Generated from development-plan.md]

### Feature: [Name]
- [ ] TEST: Unit tests for business logic
- [ ] TEST: Integration tests for API
- [ ] IMPLEMENT: Core functionality
- [ ] REFACTOR: Code optimization
- [ ] DOC: API documentation
- [ ] REVIEW: Code review checklist

## Phase 4: Integration & Quality
### Testing Suite
- [ ] E2E test scenarios
- [ ] Performance benchmarks
- [ ] Security audit
- [ ] Accessibility testing
- [ ] Cross-browser testing

### Documentation
- [ ] User documentation
- [ ] API reference
- [ ] Deployment guide
- [ ] Troubleshooting guide

## Phase 5: Deployment
- [ ] Production environment setup
- [ ] Monitoring configuration
- [ ] Backup procedures
- [ ] Rollback plan
- [ ] Launch checklist

## 🚨 Blocked Items
[Track blocked tasks with reasons]

## 📝 Notes
[Important reminders and context]
```

**FILE 2: .gitignore**
Comprehensive exclusions for modern development:

```gitignore
# Dependencies
node_modules/
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
.pnpm-store/

# Environment
.env
.env.local
.env.*.local
.env.development
.env.test
.env.production

# IDE
.vscode/
!.vscode/extensions.json
!.vscode/settings.json
.idea/
*.swp
*.swo
*~
.DS_Store

# Build
dist/
build/
out/
.next/
.nuxt/
.cache/
*.tsbuildinfo

# Testing
coverage/
.nyc_output/
test-results/
playwright-report/

# Logs
logs/
*.log
lerna-debug.log*

# OS
Thumbs.db
.DS_Store
.AppleDouble
.LSOverride

# Temporary
tmp/
temp/
*.tmp
*.temp

# MCP
.mcp-cache/
mcp-logs/

# Project specific
# Add your specific exclusions here
```

**FILE 3: project-structure.md**
Scalable organization guide:

```markdown
# Project Structure Guide

## Directory Organization
```
[project-root]/
├── .github/                    # GitHub specific files
│   ├── workflows/             # GitHub Actions
│   ├── ISSUE_TEMPLATE/        # Issue templates
│   └── PULL_REQUEST_TEMPLATE.md
├── docs/                      # Documentation
│   ├── api/                   # API documentation
│   ├── architecture/          # Architecture decisions
│   └── guides/                # User guides
├── src/                       # Source code
│   ├── components/            # UI components
│   ├── services/              # Business logic
│   ├── controllers/           # API controllers
│   ├── middleware/            # Express middleware
│   ├── models/                # Data models
│   ├── utils/                 # Utilities
│   ├── types/                 # TypeScript types
│   └── index.ts              # Entry point
├── tests/                     # Test files
│   ├── unit/                  # Unit tests
│   ├── integration/           # Integration tests
│   ├── e2e/                   # End-to-end tests
│   └── fixtures/              # Test data
├── scripts/                   # Build/deploy scripts
├── config/                    # Configuration files
├── docker/                    # Docker files
├── plan/                      # Workflow automation
└── [project files]            # Root config files
```

## Naming Conventions
- **Files**: kebab-case (user-service.ts)
- **Components**: PascalCase (UserProfile.tsx)
- **Tests**: [name].test.ts or [name].spec.ts
- **Interfaces**: PascalCase with 'I' prefix (IUserData)
- **Enums**: PascalCase (UserRole)

## Import Organization
```typescript
// 1. External imports
import express from 'express';
import { z } from 'zod';

// 2. Internal imports
import { UserService } from '@/services/user-service';
import { logger } from '@/utils/logger';

// 3. Type imports
import type { Request, Response } from 'express';
import type { IUser } from '@/types/user';
```

## MCP Integration Points
- **Serena**: src/ directory for code analysis
- **Context7**: Reference when adding libraries
- **Filesystem**: All file operations
- **GitHub**: Version control workflow
- **Memory**: Session context storage
```

**FILE 4: README.md**
Professional project documentation:

```markdown
# [Project Name]

![CI Status](https://github.com/[username]/[repo]/workflows/CI/badge.svg)
![Coverage](https://img.shields.io/codecov/c/github/[username]/[repo])
![License](https://img.shields.io/github/license/[username]/[repo])

> [One-line project description from spec.md]

## 🚀 Features

- ✨ [Key feature 1]
- 🔒 [Key feature 2]
- 📊 [Key feature 3]
- 🎯 [Key feature 4]

## 📋 Prerequisites

- Node.js >= 16.0.0
- npm >= 8.0.0
- Git
- Docker (optional)
- Claude Code with MCP servers configured

## 🛠️ Installation

### 1. Clone the repository
```bash
git clone https://github.com/[username]/[repo].git
cd [repo]
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure environment
```bash
cp .env.example .env
# Edit .env with your configuration
```

### 4. Set up MCP servers
Follow instructions in `docs/mcp-setup.md` or use the automated setup:
```bash
# Review mcp-config-reference.json for server details
claude mcp list  # Verify servers are configured
```

## 🚦 Quick Start

### Development mode
```bash
npm run dev
```

### Run tests
```bash
npm test
npm run test:watch  # Watch mode
npm run test:coverage  # With coverage
```

### Build for production
```bash
npm run build
npm start
```

## 📖 Documentation

- [API Documentation](./docs/api/README.md)
- [Architecture Guide](./docs/architecture/README.md)
- [Development Workflow](./docs/guides/development.md)
- [Deployment Guide](./docs/guides/deployment.md)

## 🧪 Testing

This project follows strict Test-Driven Development:

```bash
# Run all tests
npm test

# Run specific test suite
npm test -- user.test.ts

# Generate coverage report
npm run test:coverage
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Write tests first (TDD required)
4. Commit your changes (`git commit -m 'feat: add amazing feature'`)
5. Push to the branch (`git push origin feature/amazing-feature`)
6. Open a Pull Request

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

## 📄 License

This project is licensed under the [LICENSE_TYPE] License - see [LICENSE](./LICENSE) file for details.

## 🙏 Acknowledgments

- [Acknowledgment 1]
- [Acknowledgment 2]

## 📞 Support

- 📧 Email: [support email]
- 💬 Discord: [discord link]
- 🐛 Issues: [GitHub Issues](https://github.com/[username]/[repo]/issues)
```

**FILE 5: mcp-config-reference.json**
Enhanced MCP configuration documentation:

```json
{
  "version": "2.0",
  "lastUpdated": "[TIMESTAMP]",
  "servers": {
    "serena": {
      "scope": "user",
      "purpose": "Semantic code analysis and intelligent refactoring",
      "command": "uvx --from git+https://github.com/oraios/serena serena-mcp-server --context ide-assistant",
      "capabilities": [
        "Symbol-level code analysis",
        "Intelligent refactoring suggestions",
        "Dependency analysis",
        "Code quality insights",
        "TypeScript language server integration"
      ],
      "usage": {
        "codeAnalysis": "Analyze [file/directory] with Serena for [purpose]",
        "refactoring": "Use Serena to refactor [component] for [goal]",
        "dependencies": "Check dependencies with Serena in [module]"
      }
    },
    "context7": {
      "scope": "user",
      "purpose": "Real-time documentation and code examples",
      "command": "npx -y @upstash/context7-mcp@latest",
      "capabilities": [
        "Latest framework documentation",
        "Code examples from 100k+ repos",
        "Best practices",
        "Security advisories"
      ],
      "usage": {
        "documentation": "use context7 to find [library] documentation",
        "examples": "use context7 for [pattern] examples",
        "bestPractices": "use context7 for [technology] best practices"
      }
    },
    "filesystem": {
      "scope": "project",
      "purpose": "Secure file operations",
      "command": "npx -y @modelcontextprotocol/server-filesystem ./src ./tests ./docs ./config ./scripts",
      "security": {
        "restricted": true,
        "allowedPaths": ["./src", "./tests", "./docs", "./config", "./scripts"],
        "forbidden": ["node_modules", ".git", ".env"]
      }
    },
    "github": {
      "scope": "project",
      "purpose": "Version control and collaboration",
      "command": "npx -y @modelcontextprotocol/server-github",
      "features": [
        "Repository management",
        "Branch operations",
        "Pull request automation",
        "Issue tracking",
        "GitHub Actions integration"
      ],
      "authentication": {
        "required": true,
        "scopes": ["repo", "workflow", "read:org"]
      }
    },
    "memory": {
      "scope": "user",
      "purpose": "Persistent context across sessions",
      "command": "npx -y @modelcontextprotocol/server-memory",
      "storage": {
        "projectContext": true,
        "sessionHistory": true,
        "decisions": true,
        "learnings": true
      }
    }
  },
  "exportTool": {
    "name": "claude-code-exporter",
    "command": "npm install -g claude-code-exporter",
    "usage": {
      "listSessions": "claude-prompts --list",
      "exportCurrent": "claude-prompts",
      "exportAll": "claude-prompts --aggregate",
      "exportPeriod": "claude-prompts --period=7d"
    }
  }
}
```

**FILE 6: workflow-guide.md**
Comprehensive workflow documentation:

```markdown
# Development Workflow Guide

## Daily Workflow

### 1. Session Start
```bash
# Use Prompt #5 V2.0 to initialize session
# This loads context and verifies MCP servers
```

### 2. Feature Development
```bash
# Use Prompt #6 V2.0 template for EVERY feature
# Replace [TASK_DESCRIPTION] with your task
# Follow TDD strictly
```

### 3. Session End
```bash
# Update work-journal.md
# Export conversation: claude-prompts
# Commit all changes
# Update todo.md progress
```

## Git Workflow

### Branch Strategy
- `main`: Production-ready code
- `develop`: Integration branch
- `feature/*`: New features
- `fix/*`: Bug fixes
- `docs/*`: Documentation updates

### Commit Convention
```
type(scope): subject

body

footer
```

Types: feat, fix, docs, style, refactor, test, chore

### Pull Request Process
1. Create feature branch
2. Write tests first (TDD)
3. Implement feature
4. Update documentation
5. Create PR with template
6. Pass all checks
7. Code review
8. Merge

## Quality Gates

### Pre-commit
- Linting passes
- Tests pass
- Type checking passes
- No console.logs

### Pre-push
- All tests pass
- Coverage maintained
- Build succeeds
- No merge conflicts

### PR Checks
- CI/CD passes
- Code review approved
- Documentation updated
- Changelog updated

## MCP Server Usage

### Development Flow
1. **Serena**: Analyze before refactoring
2. **Context7**: Research before implementing
3. **Filesystem**: All file operations
4. **GitHub**: Version control
5. **Memory**: Preserve decisions

### Best Practices
- Verify servers at session start
- Use appropriate server for each task
- Store important context in memory
- Export conversations regularly
```

**STEP 3: Initialize Project Infrastructure**

After creating all files, set up the basic project structure:

1. **Create directories**:
   ```bash
   mkdir -p src/{components,services,controllers,middleware,models,utils,types}
   mkdir -p tests/{unit,integration,e2e,fixtures}
   mkdir -p docs/{api,architecture,guides}
   mkdir -p scripts config docker
   ```

2. **Initialize npm project** (if not done):
   ```bash
   npm init -y
   npm pkg set type="module"
   ```

3. **Create initial commit**:
   ```bash
   git add .
   git commit -m "chore: initial project setup with workflow automation"
   ```

4. **Update memory server** with project context:
   - Project name and description
   - Key architectural decisions
   - Workflow preferences
   - Team conventions

**VERIFICATION CHECKLIST:**
- [ ] All 6 files created successfully
- [ ] Git repository initialized
- [ ] Directory structure created
- [ ] MCP servers verified
- [ ] Memory server updated
- [ ] Export tool tested
- [ ] Initial commit made

The project infrastructure is now complete and ready for development!
```