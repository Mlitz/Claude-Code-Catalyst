# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Claude Code Catalyst is a comprehensive 8-step workflow system for AI-powered development using Claude Code with strict Test-Driven Development (TDD) practices. This is not a traditional software project but rather a collection of prompt templates and methodologies.

## Repository Structure

- `prompts/` - Contains the 8 sequential workflow prompts (v2.0-v3.1)
  - `prompt-0-v2.0.md` - MCP Server Setup
  - `prompt-0.5-v2.1.md` - Automated Workflow Setup
  - `prompt-1-v2.0.md` - Interactive Requirements Discovery
  - `prompt-2-v3.1.md` - Comprehensive Specification Generation
  - `prompt-3-v2.1.md` - Claude Code Plan Generation
  - `prompt-4-v2.1.md` - Project Setup & Todo Management
  - `prompt-5-v2.1.md` - Development Session Initialization
  - `prompt-6-v2.1.md` - TDD Feature Development
  - `prompt-7-v2.0.md` - TDD Enforcement Template
- `docs/` - Documentation directory
- `examples/` - Example implementations (coming soon)

## Key Workflow Principles

### TDD Enforcement
- **RED phase first**: Always write failing tests before any production code
- **GREEN phase**: Write minimal code to pass tests
- **REFACTOR phase**: Improve code quality while keeping tests green
- **100% coverage target**: No exceptions without explicit approval
- **Zero tolerance policy**: No linting errors, TypeScript errors, or console.logs

### MCP Server Integration
The workflow requires 5 MCP servers:
1. **Serena**: Semantic code analysis and refactoring
2. **Context7**: Real-time documentation lookup
3. **Memory**: Persistent context across sessions
4. **Filesystem**: Secure file operations
5. **GitHub**: Version control integration

### Workflow Execution Order
1. MCP Server Setup (one-time)
2. Workflow Automation (one-time)
3. Requirements Discovery
4. Specification Generation
5. Development Planning
6. Project Setup
7. Session Initialization (daily)
8. Feature Development (repeat as needed)

## Working with Prompts

When modifying prompts:
- Maintain the version numbering scheme (e.g., v2.0, v2.1, v3.1)
- Preserve the sequential workflow nature
- Keep TDD principles non-negotiable
- Ensure MCP server commands are accurate

## Important Context

- This repository provides a methodology, not executable code
- No build/test commands are needed for this repository itself
- The prompts are designed to be copied into Claude Code sessions
- Each prompt builds upon the previous ones in sequence
- The workflow enforces quality gates at each step