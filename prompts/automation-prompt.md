# Task Automation Prompt Template

Use this template to request task automation from the Task Automator agent.

## Variables

- `{task_description}` - Clear description of the task to automate
- `{context}` - Project context (framework, language, existing patterns)
- `{requirements}` - Specific requirements or constraints

## Prompt Template

```
I need help automating the following task:

## Task Description

{task_description}

## Project Context

{context}

## Requirements

{requirements}

## Expected Deliverables

Please provide:

1. **Generated Files**: List of files to create or modify
2. **Code Implementation**: Complete, production-ready code
3. **Configuration**: Any configuration files or environment variables needed
4. **Documentation**: Usage instructions and examples
5. **Testing**: Test cases or testing instructions
6. **Next Steps**: Recommended follow-up actions

## Quality Expectations

- Follow existing code patterns and conventions
- Include comprehensive error handling
- Add appropriate logging
- Include input validation
- Write maintainable, well-documented code
- Consider edge cases
```

## Usage Examples

### Example 1: API Endpoint Generation

```
I need help automating the following task:

## Task Description

Create a complete REST API endpoint for managing blog posts with CRUD operations (Create, Read, Update, Delete).

## Project Context

- **Framework**: Express.js (Node.js)
- **Database**: PostgreSQL with Sequelize ORM
- **Authentication**: JWT-based, already implemented
- **Existing Patterns**: Controllers in `controllers/`, routes in `routes/`, models in `models/`

## Requirements

- All endpoints should require authentication
- Include input validation
- Add pagination for list endpoint
- Include proper error handling
- Follow REST best practices
- Add appropriate HTTP status codes

## Expected Deliverables

Please provide:

1. **Generated Files**: List of files to create or modify
2. **Code Implementation**: Complete, production-ready code
3. **Configuration**: Any configuration files or environment variables needed
4. **Documentation**: Usage instructions and examples
5. **Testing**: Test cases or testing instructions
6. **Next Steps**: Recommended follow-up actions
```

### Example 2: Test Suite Generation

```
I need help automating the following task:

## Task Description

Generate a comprehensive test suite for an existing authentication module.

## Project Context

- **Framework**: Jest (JavaScript)
- **Module**: `auth.js` with functions: login(), register(), verifyToken(), resetPassword()
- **Test Location**: `tests/auth.test.js`
- **Existing Setup**: Jest is configured, test database available

## Requirements

- Test all functions in the auth module
- Include happy path tests
- Test error scenarios
- Test edge cases (invalid inputs, missing fields, etc.)
- Use appropriate mocking for database and email service
- Achieve >90% code coverage

## Expected Deliverables

Please provide:

1. **Generated Files**: Complete test file
2. **Code Implementation**: All test cases
3. **Configuration**: Any additional test setup needed
4. **Documentation**: How to run tests
5. **Testing**: Coverage report interpretation
6. **Next Steps**: Additional test scenarios to consider
```

### Example 3: Docker Configuration

```
I need help automating the following task:

## Task Description

Create Docker configuration for a full-stack application.

## Project Context

- **Frontend**: React (port 3000)
- **Backend**: Node.js/Express (port 5000)
- **Database**: PostgreSQL
- **Redis**: For caching
- **Existing Setup**: npm-based project

## Requirements

- Development environment with hot-reload
- Production-ready multi-stage builds
- Docker Compose for local development
- Environment variable configuration
- Health checks for all services
- Volume mounts for development
- Network isolation

## Expected Deliverables

Please provide:

1. **Generated Files**:
   - Dockerfile for frontend
   - Dockerfile for backend
   - docker-compose.yml
   - .dockerignore
2. **Code Implementation**: Complete Docker configurations
3. **Configuration**: Environment variable templates
4. **Documentation**: Setup and usage instructions
5. **Testing**: How to verify the setup works
6. **Next Steps**: Deployment considerations
```

### Example 4: CI/CD Pipeline

```
I need help automating the following task:

## Task Description

Set up a complete CI/CD pipeline for automated testing and deployment.

## Project Context

- **Platform**: GitHub Actions
- **Project**: Node.js web application
- **Deployment Target**: AWS (EC2)
- **Existing Setup**: Jest for testing, ESLint for linting

## Requirements

- Run tests on every pull request
- Run linting on every commit
- Deploy to staging on merge to develop branch
- Deploy to production on merge to main branch
- Include security scanning
- Notify team on Slack for deployment status
- Automatic rollback on health check failure

## Expected Deliverables

Please provide:

1. **Generated Files**: GitHub Actions workflow files
2. **Code Implementation**: Complete CI/CD configuration
3. **Configuration**: Secrets and variables needed
4. **Documentation**: Setup instructions and workflow explanation
5. **Testing**: How to test the pipeline
6. **Next Steps**: Monitoring and alerting setup
```

### Example 5: Database Migration Script

```
I need help automating the following task:

## Task Description

Create a database migration script to add user roles and permissions.

## Project Context

- **Database**: PostgreSQL
- **ORM**: Sequelize
- **Existing Tables**: users, sessions
- **Migration Tool**: Sequelize CLI

## Requirements

- Add roles table (id, name, description)
- Add permissions table (id, name, resource, action)
- Add role_permissions junction table
- Add user_roles junction table
- Create indexes for performance
- Include rollback capability
- Seed with default roles (admin, user, moderator)

## Expected Deliverables

Please provide:

1. **Generated Files**: Migration files with up/down functions
2. **Code Implementation**: Complete migration code
3. **Configuration**: Any database configuration changes
4. **Documentation**: How to run migrations
5. **Testing**: How to verify migrations worked
6. **Next Steps**: How to use roles in application code
```

## Tips for Effective Automation Requests

### 1. Be Specific
- Clearly describe what you want to automate
- Include specific requirements and constraints
- Mention any standards or conventions to follow

### 2. Provide Context
- Explain your tech stack
- Describe existing architecture
- Mention related systems or integrations

### 3. Define Success
- What should the automation do?
- What are the acceptance criteria?
- How will you measure success?

### 4. Mention Constraints
- Performance requirements
- Security considerations
- Compatibility needs
- Resource limitations

### 5. Request Complete Solutions
- Don't just ask for snippets
- Request production-ready code
- Ask for documentation and tests
- Include error handling

## Common Automation Scenarios

### Development Workflows
- Project scaffolding and boilerplate
- Code generation from templates
- API client generation from OpenAPI specs
- Database migrations

### Testing and Quality
- Test suite generation
- Mock data generation
- Load testing scripts
- Code quality checks

### Deployment and Operations
- CI/CD pipeline setup
- Infrastructure as Code
- Monitoring and alerting setup
- Backup and restore scripts

### Documentation
- README generation
- API documentation
- Code comment generation
- Changelog generation

## Integration Examples

### CLI Usage
```bash
# Using the automation prompt
ayaiay prompt automation-prompt \
  --task_description "Create REST API for users" \
  --context "Express.js, MongoDB" \
  --requirements "JWT auth, validation, tests"
```

### Programmatic Usage
```javascript
const ayaiay = require('ayaiay-sdk');

const result = await ayaiay.prompt('automation-prompt', {
  task_description: 'Generate CI/CD pipeline',
  context: 'GitHub Actions, Node.js project',
  requirements: 'Test, lint, deploy to AWS'
});

console.log(result.generatedFiles);
```

### Interactive Usage
```bash
# Interactive mode prompts for each variable
ayaiay prompt automation-prompt --interactive
```

## Troubleshooting

### Generated Code Doesn't Work
- Review project context for accuracy
- Check if requirements were too vague
- Verify existing code patterns were described correctly
- Test in isolated environment first

### Code Doesn't Match Existing Style
- Provide examples of existing code
- Be explicit about coding standards
- Reference style guides
- Include linter configurations

### Automation Too Generic
- Be more specific in requirements
- Include concrete examples
- Mention edge cases to handle
- Provide sample data

## Advanced Usage

### Chaining Automations
```bash
# Generate model, then controller, then tests
ayaiay prompt automation-prompt --task "Generate User model" \
  && ayaiay prompt automation-prompt --task "Generate User controller" \
  && ayaiay prompt automation-prompt --task "Generate User tests"
```

### Custom Variables
You can extend this template with custom variables for your specific use cases:

```markdown
## Additional Variables

- `{framework_version}` - Specific version requirements
- `{team_conventions}` - Team-specific coding conventions
- `{performance_targets}` - Performance benchmarks to meet
- `{security_requirements}` - Security compliance needs
```

## Best Practices

1. **Start Small**: Begin with simple automation, then expand
2. **Review Generated Code**: Always review before using in production
3. **Test Thoroughly**: Test automation in safe environment first
4. **Document Custom Changes**: Note any modifications you make
5. **Share Learnings**: Document successful patterns for team
6. **Iterate**: Refine automation based on results

---

*Good automation requests lead to great automation results.*
