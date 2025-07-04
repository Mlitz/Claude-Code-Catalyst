# Contributing to Claude Code Catalyst

Thank you for your interest in contributing to Claude Code Catalyst! This document provides guidelines for contributing to the project.

## 🎯 Our Mission

Claude Code Catalyst aims to revolutionize AI-assisted development by providing a comprehensive, test-driven workflow system that ensures quality, maintainability, and rapid delivery. Every contribution should align with these core principles:

- **Quality First**: All code must follow strict TDD practices
- **AI-Enhanced**: Leverage Claude Code and MCP servers effectively
- **Developer Experience**: Make the workflow intuitive and powerful
- **Production Ready**: Everything should be enterprise-grade

## 🚀 How to Contribute

### Types of Contributions

We welcome several types of contributions:

1. **🐛 Bug Reports**: Found an issue? Help us fix it!
2. **✨ Feature Requests**: Ideas for new functionality
3. **📚 Documentation**: Improve guides, examples, and explanations
4. **🧪 Examples**: Real-world implementations using the workflow
5. **🔧 Prompt Improvements**: Enhance the workflow templates
6. **🎨 UX Improvements**: Better developer experience
7. **🔒 Security Enhancements**: Strengthen security practices

### Before You Start

1. **Read the Documentation**: Understand the workflow by reading the README and trying the prompts
2. **Check Existing Issues**: Look for existing discussions on your topic
3. **MCP Server Setup**: Ensure you have the required MCP servers configured
4. **Follow TDD**: All contributions must follow test-driven development

## 📋 Getting Started

### 1. Fork and Clone

```bash
# Fork the repository on GitHub
# Then clone your fork
git clone https://github.com/your-username/claude-code-catalyst.git
cd claude-code-catalyst
```

### 2. Set Up Development Environment

```bash
# Create a new branch for your work
git checkout -b feature/your-feature-name

# If adding code examples, ensure you have Node.js and dependencies
npm install

# Set up MCP servers following prompts/00-mcp-server-setup.md
```

### 3. Make Your Changes

Follow our development workflow:

#### For Documentation Changes
- Update relevant files in clear, concise language
- Include examples where helpful
- Test any code snippets you include
- Update table of contents if needed

#### For Prompt Template Changes
- Follow the existing structure and format
- Include comprehensive validation steps
- Test the prompt with actual Claude Code sessions
- Document any new MCP server integrations
- Ensure TDD enforcement remains strict

#### For Example Projects
- Use the complete workflow system
- Include full documentation
- Demonstrate best practices
- Follow TDD strictly
- Include tests with 100% coverage

### 4. Testing Your Changes

#### Documentation Testing
```bash
# Verify markdown formatting
# Check all links work
# Ensure code examples are correct
```

#### Prompt Testing
```bash
# Test with actual Claude Code sessions
# Verify MCP server integration works
# Confirm all validation steps pass
# Test with different project types
```

#### Code Testing (for examples)
```bash
# Follow TDD: write tests first
npm test

# Ensure linting passes
npm run lint

# Verify type checking
npm run type-check

# Check coverage
npm run test:coverage
```

## 🎨 Style Guidelines

### Documentation Style

- **Clear and Concise**: Use simple, direct language
- **Action-Oriented**: Start sections with verbs (Create, Configure, Run)
- **Consistent Formatting**: Follow existing markdown conventions
- **Code Examples**: Include working, tested examples
- **Visual Aids**: Use mermaid diagrams where helpful

### Prompt Template Style

- **Structured Format**: Follow the established template structure
- **Validation Steps**: Include comprehensive verification
- **MCP Integration**: Specify which servers to use
- **TDD Enforcement**: Make test-first development mandatory
- **Time Estimates**: Provide realistic time expectations

### Code Style (for examples)

- **TypeScript First**: Use TypeScript with strict mode
- **100% Test Coverage**: No exceptions
- **ESLint + Prettier**: Follow automated formatting
- **Meaningful Names**: Clear, descriptive variable/function names
- **Error Handling**: Comprehensive error management

## 📝 Commit Guidelines

### Commit Message Format

```
type(scope): subject

body

footer
```

#### Types
- `feat`: New features
- `fix`: Bug fixes
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or fixing tests
- `chore`: Maintenance tasks

#### Examples
```bash
feat(prompts): add automated testing validation to TDD template

- Add comprehensive test verification steps
- Include coverage requirements
- Ensure strict TDD enforcement

Closes #123

docs(readme): improve MCP server setup instructions

- Add troubleshooting section for common server issues
- Include verification steps for each server
- Add links to official documentation

fix(workflow): resolve memory server context persistence

- Fix session context not being saved properly
- Add validation for memory server responses
- Include recovery procedures for context loss

Resolves #456
```

### Git Workflow

1. **Branch Naming**: Use descriptive names
   - `feature/improve-tdd-template`
   - `fix/mcp-server-connection`
   - `docs/add-api-examples`

2. **Commit Frequency**: Commit early and often
   - Each logical change should be a separate commit
   - Squash commits before submitting PR if needed

3. **Pull Request Process**: See section below

## 🔍 Pull Request Process

### Before Submitting

- [ ] Changes follow the style guidelines
- [ ] Documentation is updated if needed
- [ ] All tests pass (for code contributions)
- [ ] Commit messages follow the convention
- [ ] Branch is up to date with main

### PR Template

When creating a pull request, include:

```markdown
## Description
Brief description of changes and motivation.

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation update
- [ ] Prompt template improvement
- [ ] Example project

## Testing
Describe how you tested your changes:
- [ ] Manual testing with Claude Code
- [ ] Automated tests (if applicable)
- [ ] Documentation review
- [ ] MCP server integration verified

## Checklist
- [ ] I have followed the TDD workflow for any code
- [ ] My changes follow the project style guidelines
- [ ] I have updated documentation as needed
- [ ] My commits follow the commit message convention
- [ ] I have tested my changes thoroughly
```

### Review Process

1. **Automated Checks**: CI will run basic validation
2. **Peer Review**: At least one maintainer will review
3. **Testing**: Changes will be tested in real scenarios
4. **Documentation Review**: Ensure clarity and completeness
5. **Merge**: Approved changes are merged to main

## 🧪 Testing Guidelines

### For Documentation
- Test all code examples in actual environments
- Verify all links work correctly
- Check formatting renders properly
- Ensure instructions are clear and complete

### For Prompt Templates
- Test with multiple project types
- Verify MCP server integration
- Confirm validation steps work
- Test error scenarios and recovery

### For Code Examples
- **100% Test Coverage Required**
- Follow TDD strictly: tests first, always
- Include unit, integration, and e2e tests
- Test error handling and edge cases
- Performance testing for complex features

## 🔒 Security Guidelines

### General Security
- Never include secrets, API keys, or credentials
- Validate all user inputs in examples
- Follow security best practices in code
- Document security considerations

### MCP Server Security
- Ensure filesystem server paths are restricted
- Validate GitHub token permissions
- Document security implications of server access
- Include security verification steps

## 🌍 Community Guidelines

### Code of Conduct

Be respectful, inclusive, and collaborative:

- **Be Welcoming**: Help newcomers feel welcome
- **Be Respectful**: Respect different viewpoints and experiences
- **Be Collaborative**: Share knowledge and help others
- **Be Professional**: Keep discussions focused and constructive

### Communication

- **GitHub Issues**: For bug reports and feature requests
- **Pull Requests**: For code/documentation contributions
- **Discussions**: For general questions and ideas

## 📚 Resources

### Essential Reading
- [README.md](./README.md) - Project overview and quick start
- [Workflow Prompts](./prompts/) - Core workflow templates
- [Examples](./examples/) - Real implementation examples

### External Resources
- [Claude Code Documentation](https://docs.anthropic.com/claude-code)
- [MCP Protocol Specification](https://modelcontextprotocol.io/)
- [Test-Driven Development Guide](https://martinfowler.com/bliki/TestDrivenDevelopment.html)

## ❓ Questions?

If you have questions about contributing:

1. **Check Documentation**: Review existing docs first
2. **Search Issues**: Look for similar questions
3. **Create Discussion**: Start a GitHub Discussion
4. **Contact Maintainers**: Reach out directly if needed

## 🙏 Recognition

Contributors will be recognized in:
- README.md acknowledgments section
- Release notes for significant contributions
- GitHub contributor statistics
- Special recognition for exceptional contributions

Thank you for helping make Claude Code Catalyst better for everyone! 🎉