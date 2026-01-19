# Code Review Prompt Template

Use this template to request structured code reviews from the Code Reviewer agent.

## Variables

- `{language}` - Programming language (e.g., Python, JavaScript, Go)
- `{file_path}` - Path to the file being reviewed
- `{code}` - The code to review
- `{focus_areas}` - Specific areas to focus on (optional)

## Prompt Template

```
Please review the following {language} code from {file_path}.

## Code to Review

```{language}
{code}
```

## Review Focus

{focus_areas}

## Review Checklist

Please evaluate the code based on:

1. **Functionality**: Does the code work as intended?
2. **Code Quality**: Is it readable, maintainable, and well-structured?
3. **Security**: Are there any security vulnerabilities?
4. **Performance**: Are there any performance issues?
5. **Best Practices**: Does it follow {language} best practices?
6. **Testing**: Is the code testable and are tests needed?

## Expected Output

Please provide:

### Critical Issues
List any critical problems that must be fixed (security, bugs, breaking changes)

### Important Issues
List significant issues that should be addressed (performance, maintainability)

### Suggestions
List optional improvements and refactoring opportunities

### Positive Feedback
Highlight any particularly good aspects of the code

For each issue, please include:
- **Location**: Specific line numbers
- **Severity**: Critical/Important/Suggestion
- **Explanation**: Why this is an issue
- **Recommendation**: How to fix it (with code examples if possible)
```

## Usage Examples

### Example 1: General Code Review

```
Please review the following JavaScript code from src/utils/validation.js.

## Code to Review

```javascript
function validateEmail(email) {
  return email.includes('@');
}

function validatePassword(password) {
  return password.length > 6;
}
```

## Review Focus

Focus on security and validation completeness.

## Review Checklist

Please evaluate the code based on:

1. **Functionality**: Does the code work as intended?
2. **Code Quality**: Is it readable, maintainable, and well-structured?
3. **Security**: Are there any security vulnerabilities?
4. **Performance**: Are there any performance issues?
5. **Best Practices**: Does it follow JavaScript best practices?
6. **Testing**: Is the code testable and are tests needed?
```

### Example 2: Database Code Review

```
Please review the following Python code from models/user.py.

## Code to Review

```python
def get_user_by_id(user_id):
    query = f"SELECT * FROM users WHERE id = {user_id}"
    cursor.execute(query)
    return cursor.fetchone()

def update_user_email(user_id, new_email):
    query = f"UPDATE users SET email = '{new_email}' WHERE id = {user_id}"
    cursor.execute(query)
    connection.commit()
```

## Review Focus

Focus on security (SQL injection) and error handling.

## Review Checklist

Please evaluate the code based on:

1. **Functionality**: Does the code work as intended?
2. **Code Quality**: Is it readable, maintainable, and well-structured?
3. **Security**: Are there any security vulnerabilities?
4. **Performance**: Are there any performance issues?
5. **Best Practices**: Does it follow Python best practices?
6. **Testing**: Is the code testable and are tests needed?
```

### Example 3: API Endpoint Review

```
Please review the following TypeScript code from routes/api.ts.

## Code to Review

```typescript
app.post('/api/process', async (req, res) => {
  const data = req.body;
  const result = await processData(data);
  res.json(result);
});

async function processData(data: any): Promise<any> {
  return data.map((item: any) => item.value * 2);
}
```

## Review Focus

Focus on type safety, error handling, and input validation.

## Review Checklist

Please evaluate the code based on:

1. **Functionality**: Does the code work as intended?
2. **Code Quality**: Is it readable, maintainable, and well-structured?
3. **Security**: Are there any security vulnerabilities?
4. **Performance**: Are there any performance issues?
5. **Best Practices**: Does it follow TypeScript best practices?
6. **Testing**: Is the code testable and are tests needed?
```

## Tips for Effective Reviews

1. **Be Specific**: Include the actual code, not just descriptions
2. **Provide Context**: Explain what the code is supposed to do
3. **Focus Areas**: Highlight specific concerns or areas of interest
4. **Include Related Code**: If the code interacts with other parts, include them
5. **Specify Constraints**: Mention any performance, security, or compatibility requirements

## Customization

You can customize this template by:

- Adding language-specific checkpoints
- Including project-specific coding standards
- Specifying framework or library requirements
- Adding performance benchmarks or constraints
- Including security compliance requirements

## Integration with CI/CD

This prompt can be used in automated code review workflows:

```yaml
# Example GitHub Actions integration
- name: AI Code Review
  run: |
    ayaiay prompt review-prompt \
      --language python \
      --file_path "${{ github.event.pull_request.files }}" \
      --code "$(cat changed_files)" \
      --focus_areas "Security and performance"
```
