# Prompt #4 V2.1: Project Setup & Todo Management with Auto-Linter

**Version**: 2.1
**Last Updated**: January 2025
**Purpose**: Create comprehensive project infrastructure with enhanced organization, automation capabilities, and automatic language-specific linter configuration

**Usage**: Use after development plan generation (Prompt #3 V2.0). This establishes complete project management infrastructure with intelligent linter setup.

```
I'll create a comprehensive project management system using our MCP servers. This includes todo tracking, documentation, automation setup, project infrastructure, and automatic linter configuration based on your project language.

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
- [ ] Project-specific linter configured

## Phase 1: Project Foundation
### Week 1 Goals
- [ ] Repository structure created
- [ ] Development environment configured
  - [ ] TypeScript with strict mode (if applicable)
  - [ ] Language-specific linter setup
  - [ ] Pre-commit hooks (Husky/git hooks)
  - [ ] Editor configuration (.editorconfig)
- [ ] CI/CD pipeline foundation
  - [ ] GitHub Actions workflow
  - [ ] Automated testing
  - [ ] Linting in CI
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
- [ ] LINT: Run project linter
- [ ] DOC: API documentation
- [ ] REVIEW: Code review checklist

## Phase 4: Integration & Quality
### Testing Suite
- [ ] E2E test scenarios
- [ ] Performance benchmarks
- [ ] Security audit
- [ ] Accessibility testing
- [ ] Cross-browser testing
- [ ] Linter compliance check

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
target/
*.class
*.jar

# Testing
coverage/
.nyc_output/
test-results/
playwright-report/
htmlcov/
.pytest_cache/
.coverage

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

# Language specific
__pycache__/
*.py[cod]
*$py.class
.mypy_cache/
.ruff_cache/
vendor/
composer.lock
Cargo.lock
.gradle/

# Linter specific
.eslintcache
.stylelintcache

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

- Node.js >= 16.0.0 (for JS/TS projects)
- Python >= 3.9 (for Python projects)
- Go >= 1.19 (for Go projects)
- [Language-specific requirements]
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
# JavaScript/TypeScript
npm install

# Python
pip install -r requirements.txt

# Go
go mod download

# [Other language commands]
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
npm run dev      # JS/TS
python main.py   # Python
go run .         # Go
# [Language specific]
```

### Run tests
```bash
npm test              # JS/TS
pytest               # Python
go test ./...        # Go
# [Language specific]
```

### Lint code
```bash
npm run lint         # JS/TS
ruff check .         # Python
golangci-lint run    # Go
# Or use universal command:
./lint.sh
```

### Build for production
```bash
npm run build        # JS/TS
python setup.py build # Python
go build            # Go
# [Language specific]
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

## 🧹 Code Quality

This project uses [LINTER_NAME] for code quality:

```bash
# Check code
./lint.sh

# Auto-fix issues (if supported)
npm run lint:fix  # JS/TS
ruff format .     # Python
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Write tests first (TDD required)
4. Ensure linting passes
5. Commit your changes (`git commit -m 'feat: add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

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
      "supportedLanguages": [
        "Python",
        "TypeScript/JavaScript (some instability)",
        "PHP",
        "Go (requires gopls)",
        "Rust",
        "C# (requires dotnet)",
        "Java (slow startup)",
        "Clojure",
        "C/C++ (reference finding issues)",
        "Ruby (experimental)",
        "Kotlin (experimental)",
        "Dart (experimental)"
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
# Run linter before committing
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
4. **Run linter** (`./lint.sh` or `npm run lint`)
5. Update documentation
6. Create PR with template
7. Pass all checks (including linting)
8. Code review
9. Merge

## Quality Gates

### Pre-commit
- Linting passes
- Tests pass
- Type checking passes (if applicable)
- No console.logs

### Pre-push
- All tests pass
- Coverage maintained
- Build succeeds
- Linting passes
- No merge conflicts

### PR Checks
- CI/CD passes
- Linting passes
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

**FILE 7: setup-project-linter.sh**
Automatic language detection and linter setup:

```bash
#!/bin/bash

# Colors for output
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m'

echo -e "${GREEN}Detecting project language and setting up appropriate linter...${NC}"

# Detect the project's primary language
detect_project_language() {
    # Python
    if [ -f "requirements.txt" ] || [ -f "pyproject.toml" ] || [ -f "setup.py" ]; then
        echo "python"
        return
    fi
    
    # TypeScript
    if [ -f "tsconfig.json" ]; then
        echo "typescript"
        return
    fi
    
    # JavaScript
    if [ -f "package.json" ]; then
        echo "javascript"
        return
    fi
    
    # PHP
    if [ -f "composer.json" ]; then
        echo "php"
        return
    fi
    
    # Go
    if [ -f "go.mod" ]; then
        echo "go"
        return
    fi
    
    # Rust
    if [ -f "Cargo.toml" ]; then
        echo "rust"
        return
    fi
    
    # C#
    if ls *.csproj 1> /dev/null 2>&1 || ls *.sln 1> /dev/null 2>&1; then
        echo "csharp"
        return
    fi
    
    # Java
    if [ -f "pom.xml" ] || [ -f "build.gradle" ]; then
        echo "java"
        return
    fi
    
    # Clojure
    if [ -f "project.clj" ] || [ -f "deps.edn" ]; then
        echo "clojure"
        return
    fi
    
    # C/C++
    if [ -f "CMakeLists.txt" ] || ([ -f "Makefile" ] && (ls *.c *.cpp 2>/dev/null | head -1)); then
        echo "cpp"
        return
    fi
    
    # Ruby
    if [ -f "Gemfile" ]; then
        echo "ruby"
        return
    fi
    
    # Kotlin
    if [ -f "build.gradle.kts" ] || ls *.kt 1> /dev/null 2>&1; then
        echo "kotlin"
        return
    fi
    
    # Dart
    if [ -f "pubspec.yaml" ]; then
        echo "dart"
        return
    fi
    
    echo "unknown"
}

PROJECT_LANGUAGE=$(detect_project_language)

if [ "$PROJECT_LANGUAGE" = "unknown" ]; then
    echo -e "${RED}Could not detect project language.${NC}"
    echo "Please specify your project language manually."
    exit 1
fi

echo -e "${GREEN}Detected project language: $PROJECT_LANGUAGE${NC}"
echo ""

# Install and configure ONLY the relevant linter
case $PROJECT_LANGUAGE in
    python)
        echo "Setting up Python linter (Ruff)..."
        pip install ruff mypy
        
        # Create ruff configuration
        cat > pyproject.toml << 'EOF'
[tool.ruff]
line-length = 100
target-version = "py39"

[tool.ruff.lint]
select = ["E", "F", "I", "N", "UP", "B", "C4", "T10", "RUF"]

[tool.mypy]
python_version = "3.9"
warn_return_any = true
EOF
        
        # Update CLAUDE.md
        echo -e "\n## Linting\n- **Linter**: Ruff + mypy\n- **Run**: \`ruff check . && mypy .\`" >> CLAUDE.md
        echo -e "${GREEN}✓ Python linter configured${NC}"
        ;;
        
    typescript)
        echo "Setting up TypeScript linter (ESLint)..."
        echo -e "${YELLOW}Note: TypeScript has known instability with Serena${NC}"
        
        npm install --save-dev eslint prettier @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-prettier
        
        # Create ESLint config
        cat > .eslintrc.json << 'EOF'
{
  "parser": "@typescript-eslint/parser",
  "extends": ["eslint:recommended", "plugin:@typescript-eslint/recommended", "prettier"],
  "rules": {
    "no-console": "error",
    "@typescript-eslint/no-explicit-any": "error"
  }
}
EOF
        
        npm pkg set scripts.lint="eslint src --ext .ts,.tsx"
        npm pkg set scripts.lint:fix="eslint src --ext .ts,.tsx --fix"
        
        echo -e "${GREEN}✓ TypeScript linter configured${NC}"
        ;;
        
    javascript)
        echo "Setting up JavaScript linter (ESLint)..."
        
        npm install --save-dev eslint prettier eslint-config-prettier
        
        # Create ESLint config
        cat > .eslintrc.json << 'EOF'
{
  "extends": ["eslint:recommended", "prettier"],
  "env": {
    "node": true,
    "es2022": true
  },
  "rules": {
    "no-console": "error",
    "no-unused-vars": ["error", { "argsIgnorePattern": "^_" }]
  }
}
EOF
        
        npm pkg set scripts.lint="eslint src"
        npm pkg set scripts.lint:fix="eslint src --fix"
        
        echo -e "${GREEN}✓ JavaScript linter configured${NC}"
        ;;
        
    go)
        echo "Setting up Go linter (golangci-lint)..."
        echo -e "${YELLOW}Checking Go and gopls...${NC}"
        
        if ! command -v go &> /dev/null; then
            echo -e "${RED}Go is not installed. Please install Go first.${NC}"
            exit 1
        fi
        
        # Install golangci-lint
        curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin
        
        # Create config
        cat > .golangci.yml << 'EOF'
run:
  timeout: 5m

linters:
  enable:
    - errcheck
    - gosimple
    - govet
    - ineffassign
    - staticcheck
    - unused
EOF
        
        echo -e "${GREEN}✓ Go linter configured${NC}"
        echo "Run: golangci-lint run"
        ;;
        
    rust)
        echo "Setting up Rust linter (Clippy)..."
        
        rustup component add clippy rustfmt
        
        # Add to Cargo.toml
        echo "" >> Cargo.toml
        echo "[workspace.metadata.scripts]" >> Cargo.toml
        echo 'lint = "cargo clippy -- -D warnings"' >> Cargo.toml
        echo 'format = "cargo fmt"' >> Cargo.toml
        
        echo -e "${GREEN}✓ Rust linter configured${NC}"
        echo "Run: cargo clippy"
        ;;
        
    php)
        echo "Setting up PHP linter (PHP CodeSniffer + PHPStan)..."
        
        composer require --dev squizlabs/php_codesniffer phpstan/phpstan
        
        # Create PHPStan config
        cat > phpstan.neon << 'EOF'
parameters:
  level: 6
  paths:
    - src
EOF
        
        echo -e "${GREEN}✓ PHP linter configured${NC}"
        echo "Run: vendor/bin/phpcs && vendor/bin/phpstan analyse"
        ;;
        
    csharp)
        echo "Setting up C# linter (dotnet format)..."
        echo -e "${YELLOW}Note: C# recently changed language servers in Serena${NC}"
        
        if ! command -v dotnet &> /dev/null; then
            echo -e "${RED}dotnet SDK is required. Please install it first.${NC}"
            exit 1
        fi
        
        dotnet tool install -g dotnet-format
        
        # Create .editorconfig
        cat > .editorconfig << 'EOF'
[*.cs]
dotnet_diagnostic.CA1062.severity = warning
csharp_style_var_when_type_is_apparent = true:warning
EOF
        
        echo -e "${GREEN}✓ C# linter configured${NC}"
        echo "Run: dotnet format"
        ;;
        
    java)
        echo "Setting up Java linter (Checkstyle)..."
        echo -e "${YELLOW}Warning: Java has slow startup with Serena${NC}"
        
        if [ -f "pom.xml" ]; then
            echo "Add maven-checkstyle-plugin to your pom.xml"
        else
            echo "Add checkstyle plugin to your build.gradle"
        fi
        
        echo -e "${GREEN}✓ Java linter configuration provided${NC}"
        ;;
        
    clojure)
        echo "Setting up Clojure linter (clj-kondo)..."
        
        # Add to deps.edn or project.clj
        if [ -f "deps.edn" ]; then
            echo "Add clj-kondo alias to deps.edn"
        fi
        
        echo -e "${GREEN}✓ Clojure linter configured${NC}"
        ;;
        
    cpp)
        echo "Setting up C/C++ linter (clang-tidy)..."
        echo -e "${YELLOW}Note: C/C++ has issues with finding references in Serena${NC}"
        
        # Create .clang-tidy
        cat > .clang-tidy << 'EOF'
Checks: 'bugprone-*,performance-*,readability-*'
EOF
        
        echo -e "${GREEN}✓ C/C++ linter configured${NC}"
        ;;
        
    ruby|kotlin|dart)
        echo -e "${YELLOW}Warning: $PROJECT_LANGUAGE support in Serena is experimental${NC}"
        echo "Basic linter setup for $PROJECT_LANGUAGE..."
        
        case $PROJECT_LANGUAGE in
            ruby)
                gem install rubocop
                echo -e "${GREEN}✓ Ruby linter installed (RuboCop)${NC}"
                ;;
            kotlin)
                echo "Download ktlint from GitHub releases"
                ;;
            dart)
                echo "Dart analyzer comes with the SDK"
                ;;
        esac
        ;;
esac

# Create universal lint command
echo ""
echo "Creating project lint command..."

# Add to package.json, Makefile, or create shell script
if [ -f "package.json" ]; then
    # Already handled in npm scripts above
    echo "Lint command: npm run lint"
elif [ -f "Makefile" ]; then
    # Add to existing Makefile
    echo "" >> Makefile
    echo "lint:" >> Makefile
    case $PROJECT_LANGUAGE in
        python) echo "	ruff check . && mypy ." >> Makefile ;;
        go) echo "	golangci-lint run" >> Makefile ;;
        rust) echo "	cargo clippy -- -D warnings" >> Makefile ;;
        *) echo "	# Add your lint command here" >> Makefile ;;
    esac
else
    # Create a lint script
    cat > lint.sh << 'EOF'
#!/bin/bash
echo "Running project linter..."
EOF
    
    case $PROJECT_LANGUAGE in
        python) echo "ruff check . && mypy ." >> lint.sh ;;
        go) echo "golangci-lint run" >> lint.sh ;;
        rust) echo "cargo clippy -- -D warnings" >> lint.sh ;;
        php) echo "vendor/bin/phpcs && vendor/bin/phpstan analyse" >> lint.sh ;;
        csharp) echo "dotnet format --verify-no-changes" >> lint.sh ;;
        java) echo "mvn checkstyle:check" >> lint.sh ;;
        clojure) echo "clj -M:lint" >> lint.sh ;;
        cpp) echo "clang-tidy src/*.cpp --" >> lint.sh ;;
        ruby) echo "rubocop" >> lint.sh ;;
        kotlin) echo "./ktlint" >> lint.sh ;;
        dart) echo "dart analyze" >> lint.sh ;;
    esac
    
    chmod +x lint.sh
    echo "Lint command: ./lint.sh"
fi

# Setup pre-commit hook
echo ""
echo "Setting up pre-commit hook..."

mkdir -p .git/hooks
cat > .git/hooks/pre-commit << 'EOF'
#!/bin/bash
echo "Running linter before commit..."

EOF

# Add appropriate lint command to pre-commit
case $PROJECT_LANGUAGE in
    python) echo "ruff check . && mypy ." >> .git/hooks/pre-commit ;;
    typescript|javascript) echo "npm run lint" >> .git/hooks/pre-commit ;;
    go) echo "golangci-lint run" >> .git/hooks/pre-commit ;;
    rust) echo "cargo clippy -- -D warnings" >> .git/hooks/pre-commit ;;
    php) echo "vendor/bin/phpcs" >> .git/hooks/pre-commit ;;
    csharp) echo "dotnet format --verify-no-changes" >> .git/hooks/pre-commit ;;
    *) echo "# Add lint command" >> .git/hooks/pre-commit ;;
esac

chmod +x .git/hooks/pre-commit

echo ""
echo -e "${GREEN}✅ Linter setup complete for $PROJECT_LANGUAGE!${NC}"
echo ""
echo "Summary:"
echo "- Linter installed and configured"
echo "- Pre-commit hook created"
echo "- Run linting with: $([ -f "package.json" ] && echo "npm run lint" || echo "./lint.sh")"
echo ""

# Update todo.md
echo "- [x] Set up project-specific linter ($PROJECT_LANGUAGE)" >> todo.md
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

2. **Initialize npm project** (if applicable):
   ```bash
   npm init -y
   npm pkg set type="module"
   ```

3. **Run linter setup**:
   ```bash
   chmod +x setup-project-linter.sh
   ./setup-project-linter.sh
   ```

4. **Create initial commit**:
   ```bash
   git add .
   git commit -m "chore: initial project setup with workflow automation and linter"
   ```

5. **Update memory server** with project context:
   - Project name and description
   - Key architectural decisions
   - Workflow preferences
   - Team conventions
   - Linter configuration

**STEP 4: Configure CI/CD with Linting**

Create GitHub Actions workflow with linting:

```yaml
# .github/workflows/ci.yml
name: CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main, develop ]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      
      - name: Setup environment
        run: |
          # Language-specific setup
          if [ -f "package.json" ]; then
            npm ci
          elif [ -f "requirements.txt" ]; then
            pip install -r requirements.txt
          elif [ -f "go.mod" ]; then
            go mod download
          fi
      
      - name: Run linter
        run: |
          if [ -f "lint.sh" ]; then
            ./lint.sh
          elif [ -f "package.json" ]; then
            npm run lint
          fi

  test:
    needs: lint
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run tests
        run: |
          # Add test commands
```

**VERIFICATION CHECKLIST:**
- [ ] All 7 files created successfully
- [ ] Git repository initialized
- [ ] Directory structure created
- [ ] Language detected and linter configured
- [ ] Pre-commit hook installed
- [ ] MCP servers verified
- [ ] Memory server updated
- [ ] Export tool tested
- [ ] Initial commit made

The project infrastructure is now complete with automatic language-specific linter configuration!
```