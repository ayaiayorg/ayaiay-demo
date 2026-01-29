# My Awesome Pack

A comprehensive demonstration pack for ayaiay.org showcasing the power of AI-driven automation and code quality tools with GitHub Copilot Agent Skills.

## Overview

This pack provides a complete suite of AI agents, instructions, prompts, and skills designed to enhance your development workflow through intelligent automation and thorough code review.

## Features

### Agents

#### 1. Code Reviewer
Reviews your code for:
- Best practices and coding standards
- Security vulnerabilities
- Potential bugs and edge cases
- Performance optimizations
- Code maintainability

#### 2. Task Automator
Automates common development tasks:
- Repetitive code generation
- Boilerplate creation
- Configuration setup
- Workflow optimization

### Instructions

- **Review Guidelines**: Comprehensive standards for conducting thorough code reviews
- **Automation Best Practices**: Guidelines for effective task automation and workflow design

### Prompts

- **Review Prompt**: Structured template for code review requests
- **Automation Prompt**: Template for defining automation tasks

### Skills (NEW!)

GitHub Copilot Agent Skills enhance Copilot's ability to perform specialized tasks. This pack includes:

#### 1. GitHub Actions Debugging
Systematic approach to debugging failing GitHub Actions workflows:
- List and analyze workflow runs
- Get AI-powered failure summaries
- Deep dive into detailed logs when needed
- Reproduce and fix issues systematically

#### 2. Code Quality Enhancement
Structured methodology for improving code:
- Assess readability and maintainability
- Identify and fix code smells
- Apply refactoring techniques
- Optimize performance
- Follow best practices by language

#### 3. Security Review
Comprehensive security analysis framework:
- Input validation and injection prevention
- Authentication and authorization review
- Data protection and encryption
- Dependency security scanning
- OWASP Top 10 vulnerability assessment

Skills are automatically loaded by GitHub Copilot when relevant to improve its performance in specialized tasks.

## Installation

```bash
ayaiay install username/my-awesome-pack@1.1.0
```

## Usage

### Using the Code Reviewer Agent

```bash
ayaiay run code-reviewer --file ./src/main.js
```

### Using the Task Automator Agent

```bash
ayaiay run task-automator --task "Create React component"
```

### Using Prompts

```bash
ayaiay prompt review-prompt --language python --file ./app.py
```

### Using Skills

Skills are automatically detected and used by GitHub Copilot coding agent, CLI, and VS Code Insiders when relevant to your task. They are stored in `.github/skills/` and work seamlessly with:
- Copilot coding agent (in pull requests)
- GitHub Copilot CLI (`gh copilot` commands)  
- VS Code Insiders agent mode

No manual invocation needed - Copilot will load the appropriate skill based on your prompt and the skill's description.

## Pack Contents

- 2 AI Agents (code-reviewer, task-automator)
- 2 Instruction Sets (review-guidelines, automation-best-practices)
- 2 Prompt Templates (review-prompt, automation-prompt)
- 3 Agent Skills (github-actions-debugging, code-quality-enhancement, security-review)

## Requirements

- ayaiay CLI version 1.0.0 or higher
- Valid API key for your chosen AI model

## Configuration

All agents can be configured through the `ayaiay.yaml` manifest. Customize:
- Model selection (GPT-4, Claude, etc.)
- Temperature settings
- Additional parameters

## Contributing

Contributions are welcome! Please submit pull requests or open issues for suggestions.

## License

MIT License - see LICENSE file for details

## Support

For issues or questions:
- GitHub Issues: https://github.com/username/my-awesome-pack/issues
- Documentation: https://ayaiay.org/docs

## Changelog

### Version 1.1.0
- **NEW**: Added GitHub Copilot Agent Skills support
- Added three sample skills:
  - `github-actions-debugging`: Debug failing CI/CD workflows
  - `code-quality-enhancement`: Improve code quality systematically
  - `security-review`: Comprehensive security analysis
- Updated ayaiay.yaml with skills section
- Enhanced README with skills documentation

### Version 1.0.1
- Updated demo with latest information from ayaiay.org documentation
- Verified compatibility with current pack structure and specifications

### Version 1.0.0
- Initial release
- Code Reviewer agent
- Task Automator agent
- Review and automation guidelines
- Prompt templates
