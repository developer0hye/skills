---
name: english-first
description: Write all code, comments, documentation, and technical content in English by default unless the user explicitly requests a specific language. Use when writing code, creating files, generating comments, or documenting technical work.
---

# English First

## Core Principle

**Default to English for all technical content unless the user explicitly requests otherwise.**

## What to Write in English

Write the following in English by default:

1. **Code elements**
   - Variable names
   - Function names
   - Class names
   - Method names
   - Constants
   - Module names

2. **Comments and documentation**
   - Inline comments
   - Block comments
   - Docstrings
   - API documentation
   - Code explanations

3. **Technical artifacts**
   - Commit messages
   - Branch names
   - Pull request descriptions
   - Issue titles and descriptions
   - Log messages
   - Error messages

4. **Configuration and data**
   - Configuration file comments
   - README files
   - Setup instructions
   - Environment variable names

## When to Use Other Languages

**ONLY** use languages other than English when:

- The user explicitly requests it ("write this in Korean", "コメントは日本語で")
- The user is writing content meant for a specific language audience
- String literals or user-facing content requires localization
- The project has established conventions for non-English content

## Examples

### Good (English by default)

```python
def calculate_total_price(items, tax_rate):
    """
    Calculate the total price including tax.
    
    Args:
        items: List of item prices
        tax_rate: Tax rate as decimal (e.g., 0.1 for 10%)
    
    Returns:
        Total price with tax applied
    """
    subtotal = sum(items)
    return subtotal * (1 + tax_rate)
```

### Bad (Mixed languages without user request)

```python
def 총가격계산(items, tax_rate):
    """
    세금을 포함한 총 가격 계산
    """
    subtotal = sum(items)  # 소계 계산
    return subtotal * (1 + tax_rate)
```

## Implementation Guidelines

1. **Be consistent**: Once you start in English, maintain it throughout the codebase
2. **Follow conventions**: Use standard English naming conventions (camelCase, snake_case, etc.)
3. **Write clearly**: Use clear, concise English that's easy to understand
4. **Use proper grammar**: Write complete sentences in comments and documentation
5. **Respect user requests**: If the user asks for a different language, switch immediately

## Common Scenarios

### Scenario 1: Creating new files

```python
# user_manager.py
class UserManager:
    """Manages user accounts and authentication."""
    
    def create_user(self, username, email):
        """Create a new user account."""
        pass
```

### Scenario 2: Writing commit messages

```bash
git commit -m "Add user authentication with JWT tokens

Implement login endpoint and token validation middleware.
Add tests for authentication flow."
```

### Scenario 3: Adding comments

```javascript
// Calculate the distance between two points using Pythagorean theorem
function calculateDistance(point1, point2) {
  const dx = point2.x - point1.x;
  const dy = point2.y - point1.y;
  return Math.sqrt(dx * dx + dy * dy);
}
```

## Exceptions

These can remain in other languages:

- User-facing text that needs localization
- String constants for display purposes
- Content explicitly meant for non-English speakers
- Project-specific requirements (e.g., government mandate for local language)

## Summary

- ✅ Code: English
- ✅ Comments: English
- ✅ Documentation: English
- ✅ Commit messages: English
- ✅ Technical names: English
- ❌ User-facing strings: May vary based on audience
- ❌ Localized content: Use target language
