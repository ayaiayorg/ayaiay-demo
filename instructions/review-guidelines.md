# Code Review Guidelines

## Purpose

Code reviews are a critical part of maintaining code quality, sharing knowledge, and preventing bugs from reaching production. These guidelines help ensure reviews are thorough, constructive, and efficient.

## Core Principles

### 1. Review with Purpose
Every review should have clear objectives:
- Ensure code correctness
- Maintain code quality standards
- Share knowledge across the team
- Catch potential issues early
- Validate design decisions

### 2. Be Thorough but Efficient
- Review in focused sessions (30-60 minutes max)
- Review smaller changes more frequently
- Focus on high-impact areas first
- Don't let perfect be the enemy of good

### 3. Communicate Effectively
- Be specific and actionable
- Explain the "why" behind suggestions
- Distinguish between required changes and suggestions
- Use a respectful, collaborative tone

## Review Checklist

### Functionality
- [ ] Does the code do what it's supposed to do?
- [ ] Are edge cases handled properly?
- [ ] Is error handling appropriate?
- [ ] Are there any logical errors?
- [ ] Do changes match the requirements?

### Code Quality
- [ ] Is the code readable and maintainable?
- [ ] Are names descriptive and consistent?
- [ ] Is complexity kept to a minimum?
- [ ] Is the code DRY (Don't Repeat Yourself)?
- [ ] Are functions/methods single-purpose?

### Security
- [ ] Is user input validated and sanitized?
- [ ] Are authentication/authorization checks present?
- [ ] Is sensitive data protected?
- [ ] Are there SQL injection risks?
- [ ] Are XSS vulnerabilities addressed?
- [ ] Are dependencies up-to-date and secure?

### Performance
- [ ] Are algorithms efficient?
- [ ] Is database access optimized?
- [ ] Are there memory leaks?
- [ ] Is caching used appropriately?
- [ ] Are resources properly released?

### Testing
- [ ] Are there appropriate tests?
- [ ] Do tests cover edge cases?
- [ ] Are tests maintainable?
- [ ] Do all tests pass?
- [ ] Is test coverage adequate?

### Documentation
- [ ] Are complex sections commented?
- [ ] Is public API documented?
- [ ] Are assumptions stated?
- [ ] Is the README updated if needed?
- [ ] Are breaking changes documented?

### Architecture
- [ ] Does the code fit the existing architecture?
- [ ] Are design patterns used appropriately?
- [ ] Is separation of concerns maintained?
- [ ] Are dependencies well-managed?
- [ ] Is the code modular?

## Review Priorities

### P0 - Critical (Must Fix)
- Security vulnerabilities
- Data corruption risks
- Breaking changes without migration path
- Critical performance issues
- Incorrect functionality

### P1 - Important (Should Fix)
- Code quality issues affecting maintainability
- Missing error handling
- Performance problems
- Inadequate test coverage
- Violations of established patterns

### P2 - Suggestions (Nice to Have)
- Minor refactoring opportunities
- Style improvements
- Additional edge case handling
- Documentation enhancements
- Code organization improvements

## How to Give Feedback

### Use Clear Labels
- **Critical**: Must be fixed before merge
- **Important**: Should be addressed
- **Suggestion**: Consider this improvement
- **Question**: Seeking clarification
- **Nit**: Minor style/preference issue
- **Praise**: Highlighting good work

### Provide Context
Bad: "This is wrong"
Good: "This might cause a race condition when multiple users access simultaneously. Consider using a lock or transaction."

### Suggest Solutions
Bad: "This is inefficient"
Good: "This O(n²) loop could be optimized to O(n) using a hash map. Example: [code snippet]"

### Be Respectful
Bad: "Why would you do it this way?"
Good: "I'm curious about the approach here. Have you considered [alternative]? It might help with [benefit]."

## How to Receive Feedback

### Assume Positive Intent
- Reviewers are trying to help improve the code
- Questions are opportunities to explain your reasoning
- Suggestions are learning opportunities

### Respond Constructively
- Thank reviewers for their time
- Explain your reasoning when disagreeing
- Ask for clarification when unclear
- Update code or respond to each comment

### Know When to Discuss Offline
- Complex architectural debates
- Extensive back-and-forth
- Emotional situations
- Teaching moments

## Common Anti-Patterns

### Reviewer Anti-Patterns
- ❌ Nitpicking without explaining why
- ❌ Requesting rewrites without clear rationale
- ❌ Reviewing superficially to "get through it"
- ❌ Being inconsistent with feedback
- ❌ Approving without actually reviewing

### Author Anti-Patterns
- ❌ Getting defensive about feedback
- ❌ Making PRs too large
- ❌ Not testing changes before requesting review
- ❌ Ignoring feedback without discussion
- ❌ Rushing reviewers

## Best Practices

### For Authors
1. **Self-Review First**: Review your own code before requesting review
2. **Keep Changes Focused**: One logical change per PR
3. **Write Good Descriptions**: Explain what, why, and how
4. **Add Tests**: Include relevant tests with your changes
5. **Respond Promptly**: Address feedback in a timely manner

### For Reviewers
1. **Review Promptly**: Don't block others' work
2. **Be Thorough**: Take time to understand the changes
3. **Provide Examples**: Show, don't just tell
4. **Balance Speed and Quality**: Know when "good enough" is acceptable
5. **Acknowledge Good Work**: Call out clever solutions and improvements

## Review Workflow

1. **Initial Scan** (5 minutes)
   - Read PR description
   - Check CI/CD status
   - Scan changed files
   - Identify high-risk areas

2. **Deep Review** (20-40 minutes)
   - Review code line by line
   - Test locally if needed
   - Check related code
   - Verify tests

3. **Feedback** (5-10 minutes)
   - Organize comments by priority
   - Provide clear, actionable feedback
   - Approve, request changes, or comment

4. **Follow-up**
   - Respond to author questions
   - Re-review after changes
   - Approve when satisfied

## Tools and Automation

### Automated Checks
- Linters for code style
- Static analysis for security
- Test coverage reports
- Performance benchmarks
- Dependency vulnerability scans

### Focus Human Review On
- Business logic correctness
- Architecture and design
- Security implications
- Edge cases and error handling
- Code clarity and maintainability

## Continuous Improvement

- Retrospect on review effectiveness
- Share learnings from caught bugs
- Update guidelines based on experience
- Celebrate successful catches
- Learn from missed issues

## Resources

- [Google Engineering Practices](https://google.github.io/eng-practices/review/)
- [Conventional Comments](https://conventionalcomments.org/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Clean Code by Robert C. Martin](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

---

*Remember: The goal of code review is not perfection, but continuous improvement.*
