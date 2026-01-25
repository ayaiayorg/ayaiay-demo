# My Awesome Pack

A comprehensive demonstration pack for ayaiay.org showcasing the power of AI-driven automation and code quality tools.

## Overview

This pack provides a complete suite of AI agents, instructions, and prompts designed to enhance your development workflow through intelligent automation and thorough code review.

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

## Installation

```bash
ayaiay install username/my-awesome-pack@1.0.1
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

## Pack Contents

- 2 AI Agents (code-reviewer, task-automator)
- 2 Instruction Sets (review-guidelines, automation-best-practices)
- 2 Prompt Templates (review-prompt, automation-prompt)

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

### Version 1.0.1
- Updated demo with latest information from ayaiay.org documentation
- Verified compatibility with current pack structure and specifications

### Version 1.0.0
- Initial release
- Code Reviewer agent
- Task Automator agent
- Review and automation guidelines
- Prompt templates
