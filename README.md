# Claude Code Catalyst 🚀

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](https://github.com/yourusername/claude-code-catalyst)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TDD Required](https://img.shields.io/badge/TDD-Required-red.svg)](https://github.com/yourusername/claude-code-catalyst)

> **A comprehensive AI-powered development workflow system that transforms how you build production-ready applications with Claude Code and strict Test-Driven Development practices.**

Claude Code Catalyst is a battle-tested, 8-step workflow system that leverages Claude Code's MCP (Model Context Protocol) servers to create a seamless, intelligent development experience. Whether you're building web applications, APIs, or complex systems, this workflow ensures quality, maintainability, and rapid delivery through enforced TDD practices.

## ✨ Key Features

- 🔄 **End-to-End Workflow**: From requirements to deployment, with clear validation gates
- 🧪 **Strict TDD Enforcement**: Non-negotiable test-first development with 100% coverage targets
- 🤖 **MCP Server Integration**: Leverage 5 powerful AI servers for code analysis, documentation, and more
- 📋 **Automated Project Management**: Dynamic todo tracking and progress monitoring
- 🔒 **Security-First**: Built-in security mandates and vulnerability prevention
- 📚 **Comprehensive Documentation**: Auto-generated specs, API docs, and implementation guides
- 🎯 **Quality Gates**: Automated validation at every step ensures production readiness

## 🚀 Quick Start

### Prerequisites

Before using Claude Code Catalyst, ensure you have:

- **Claude Code** installed and running
- **Node.js** >= 16.0.0 and npm >= 8.0.0
- **Python** and `uvx` for Serena server
- **Git** for version control
- **Docker** (optional, for containerized development)

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/claude-code-catalyst.git
cd claude-code-catalyst
```

### 2. Set Up MCP Servers

The foundation of this workflow is the MCP server ecosystem. Start with:

```bash
# Use the first prompt to set up all required MCP servers
# Copy and paste the content from prompts/00-mcp-server-setup.md into Claude Code
```

This sets up 5 essential servers:
- **Serena**: Semantic code analysis and intelligent refactoring
- **Context7**: Real-time documentation and code examples
- **Memory**: Persistent context across sessions
- **Filesystem**: Secure file operations
- **GitHub**: Version control and collaboration

### 3. Initialize Your Project

```bash
# Use the workflow automation setup
# Copy content from prompts/01-automated-workflow-setup.md into Claude Code
```

### 4. Start Building

Follow the sequential prompts to build your application:

1. **Requirements Discovery** (`prompts/02-interactive-requirements-discovery.md`)
2. **Specification Generation** (`prompts/03-comprehensive-specification-generation.md`)
3. **Development Planning** (`prompts/04-claude-code-plan-generation.md`)
4. **Project Setup** (`prompts/05-project-setup-todo-management.md`)
5. **Daily Development** (`prompts/06-development-session-initialization.md`)
6. **Feature Implementation** (`prompts/07-tdd-enforcement-template.md`)

## 📋 Workflow Overview

```mermaid
graph TD
    A[MCP Server Setup] --> B[Workflow Automation]
    B --> C[Requirements Discovery]
    C --> D[Specification Generation]
    D --> E[Development Planning]
    E --> F[Project Setup]
    F --> G[Session Initialization]
    G --> H[Feature Development TDD]
    H --> I{Feature Complete?}
    I -->|No| H
    I -->|Yes| J{Project Complete?}
    J -->|No| G
    J -->|Yes| K[Deployment & Documentation]
    
    style A fill:#e1f5fe
    style B fill:#e8f5e8
    style C fill:#fff3e0
    style D fill:#fce4ec
    style E fill:#f3e5f5
    style F fill:#e0f2f1
    style G fill:#fff8e1
    style H fill:#ffebee
    style K fill:#e8f5e8
```

## 🛠️ Detailed Usage

### Phase 1: Infrastructure Setup (One-time)

#### Step 0: MCP Server Configuration
**File**: `prompts/00-mcp-server-setup.md`
**Duration**: 15-30 minutes
**Purpose**: Install and configure all required MCP servers

This critical first step ensures your Claude Code environment has access to:
- Code analysis and refactoring tools
- Real-time documentation lookup
- Persistent memory across sessions
- Secure filesystem operations
- GitHub integration

#### Step 0.5: Workflow Automation
**File**: `prompts/01-automated-workflow-setup.md`
**Duration**: 10-15 minutes
**Purpose**: Create workflow automation framework

Sets up the intelligent automation system that tracks your progress, validates steps, and maintains project state.

### Phase 2: Project Initialization (Per Project)

#### Step 1: Requirements Discovery
**File**: `prompts/02-interactive-requirements-discovery.md`
**Duration**: 30-60 minutes
**Purpose**: Systematic requirements gathering

Interactive session that builds complete project understanding through:
- Core functionality identification
- User persona development
- Technical constraint analysis
- Success criteria definition

#### Step 2: Specification Generation
**File**: `prompts/03-comprehensive-specification-generation.md`
**Duration**: 30-45 minutes
**Purpose**: Create comprehensive project documentation

Generates production-ready documentation:
- `spec.md`: Complete technical specification
- `CLAUDE.md`: AI development context with TDD rules
- `work-journal.md`: Development tracking system

#### Step 3: Development Planning
**File**: `prompts/04-claude-code-plan-generation.md`
**Duration**: 20-30 minutes
**Purpose**: Create detailed implementation roadmap

Uses Claude Code's planning feature enhanced with:
- TDD methodology integration
- Task granularity and time estimates
- Risk identification and mitigation
- MCP server utilization strategy

#### Step 4: Project Setup
**File**: `prompts/05-project-setup-todo-management.md`
**Duration**: 15-20 minutes
**Purpose**: Establish project infrastructure

Creates complete project management system:
- Dynamic todo tracking (`todo.md`)
- Git repository setup
- Development environment configuration
- Quality gates and automation

### Phase 3: Development Execution (Daily)

#### Step 5: Session Initialization
**File**: `prompts/06-development-session-initialization.md`
**Duration**: 5-10 minutes per session
**Purpose**: Load context and prepare for development

Each development session starts with:
- MCP server health verification
- Context recovery from previous sessions
- Repository status analysis
- Session planning and prioritization

#### Step 6: Feature Development (TDD)
**File**: `prompts/07-tdd-enforcement-template.md`
**Duration**: Variable per feature
**Purpose**: Implement features with strict TDD

The core development template that ensures:
- **RED**: Write failing tests first
- **GREEN**: Implement minimal code to pass
- **REFACTOR**: Improve code quality
- **INTEGRATE**: Connect to system
- **DOCUMENT**: Comprehensive documentation

## 🎯 TDD Enforcement

This workflow system implements **non-negotiable TDD practices**:

### The TDD Contract

- ❌ **NEVER** write production code without a failing test
- ✅ **ALWAYS** write tests first (RED phase)
- 🔄 **FOLLOW** Red-Green-Refactor cycle religiously
- 📊 **MAINTAIN** 100% test coverage targets
- 🚫 **NO EXCEPTIONS** - violations = task failure

### Quality Metrics

- **Test Coverage**: 100% (no exceptions without approval)
- **Build Time**: < 30 seconds
- **Test Execution**: < 100ms per test
- **Zero Tolerance**: No linting errors, TypeScript errors, or console.logs

### Automated Validation

Each step includes automatic validation:
- Test-first enforcement
- Coverage verification
- Code quality checks
- Documentation completeness
- Security compliance

## 🔧 MCP Server Integration

### Serena (Code Analysis)
```bash
# Analyze codebase structure
"Analyze src/services with Serena for code smells"

# Find refactoring opportunities
"Use Serena to identify circular dependencies"
```

### Context7 (Documentation)
```bash
# Research best practices
"use context7 for React 18 testing patterns"

# Find implementation examples
"use context7 to find Express middleware examples"
```

### Memory (Context Preservation)
```bash
# Store decisions
"Remember: We chose PostgreSQL because of ACID requirements"

# Maintain continuity
"Remember: Authentication uses JWT with 1-hour expiry"
```

### GitHub (Version Control)
```bash
# Automated workflows
# Branch management and PR automation
# Issue tracking integration
```

### Filesystem (Secure Operations)
```bash
# All file operations are performed through the filesystem server
# Automatic path validation and security checks
```

## 📁 Project Structure

After running through the workflow, your project will have:

```
your-project/
├── .github/                    # GitHub workflows and templates
├── docs/                       # Generated documentation
│   ├── api/                    # API documentation
│   ├── architecture/           # Architecture decisions
│   └── guides/                 # User and development guides
├── src/                        # Source code (TDD organized)
│   ├── components/             # UI components (if applicable)
│   ├── services/               # Business logic
│   ├── controllers/            # API controllers
│   ├── middleware/             # Express middleware
│   ├── models/                 # Data models
│   ├── utils/                  # Utilities
│   └── types/                  # TypeScript definitions
├── tests/                      # Comprehensive test suite
│   ├── unit/                   # Unit tests
│   ├── integration/            # Integration tests
│   └── e2e/                    # End-to-end tests
├── plan/                       # Workflow automation
│   ├── automation/             # Workflow scripts
│   └── logs/                   # Execution logs
├── spec.md                     # Technical specification
├── CLAUDE.md                   # AI development context
├── todo.md                     # Dynamic task tracking
├── work-journal.md             # Development journal
└── [standard config files]    # Package.json, tsconfig, etc.
```

## 🔍 Examples

### Web Application Development
See `examples/web-app/` for a complete example of building a React + Express application using this workflow.

### API Development
See `examples/api-service/` for a Node.js REST API implementation example.

### CLI Tool Development
See `examples/cli-tool/` for a TypeScript CLI application example.

## 🚨 Troubleshooting

### Common Issues

#### MCP Servers Not Connected
```bash
# Check server status
/mcp

# If servers show disconnected:
# 1. Exit Claude Code completely
# 2. Wait 10 seconds
# 3. Restart Claude Code
# 4. Verify with /mcp again
```

#### Tests Failing After Setup
```bash
# Verify test environment
npm test -- --detectOpenHandles

# Check for configuration issues
npm run type-check
npm run lint
```

#### Context Loss Between Sessions
```bash
# Ensure Memory server is working
# Use Session Initialization prompt to recover context
# Check work-journal.md for last session notes
```

### Getting Help

1. **Check Documentation**: Review the relevant prompt file
2. **Verify MCP Status**: Ensure all servers are connected
3. **Review Work Journal**: Check previous session notes
4. **Export Conversation**: Use `claude-prompts` for context
5. **Create Issue**: Use GitHub Issues for bug reports

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

### Ways to Contribute

- 🐛 **Bug Reports**: Found an issue? Let us know!
- ✨ **Feature Requests**: Ideas for improvements
- 📚 **Documentation**: Help improve our guides
- 🧪 **Examples**: Share your workflow implementations
- 🔧 **Prompt Improvements**: Enhance the workflow templates

### Development Setup

1. Fork the repository
2. Create a feature branch
3. Follow the TDD workflow for any changes
4. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## 🙏 Acknowledgments

- **Anthropic Team**: For Claude Code and MCP server architecture
- **TDD Community**: For establishing test-driven development best practices
- **Open Source Contributors**: For the amazing tools that make this workflow possible

## 📞 Support & Community

- 🐛 **Issues**: [GitHub Issues](https://github.com/yourusername/claude-code-catalyst/issues)
- 💬 **Discussions**: [GitHub Discussions](https://github.com/yourusername/claude-code-catalyst/discussions)
- 📧 **Email**: claude-code-catalyst@example.com
- 📖 **Documentation**: [Full documentation](./docs/)

---

**Ready to revolutionize your development workflow?** Start with the [Quick Start](#quick-start) guide and experience the power of AI-assisted, test-driven development!

*"Quality is not an act, it is a habit." - Aristotle*