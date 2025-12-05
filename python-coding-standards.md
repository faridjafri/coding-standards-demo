# Python Coding Standards

## 1. Function Length

**Rule:** `function-length`

**Description:** Functions should not exceed 20 lines of code

**Details:**
- Maximum allowed lines: 20
- Excludes docstrings, comments, and blank lines from the count
- Applies to both regular functions (`def`) and async functions (`async def`)

**Suggestion:** Consider breaking this function into smaller, focused functions with single responsibilities.

---

## 2. Naming Conventions

**Rule:** `naming-conventions`

**Description:** Follow PEP 8: snake_case for functions/variables, PascalCase for classes

**Details:**

### Classes
- Must use **PascalCase** (e.g., `MyClass`, `UserAccount`)
- Pattern: `^[A-Z][a-zA-Z0-9]*$`

### Functions
- Must use **snake_case** (e.g., `my_function`, `get_user_data`)
- Pattern: `^[a-z][a-z0-9_]*$`
- Exception: Dunder methods (`__init__`, `__str__`, etc.) are allowed

### Parameters
- Must use **snake_case** (e.g., `user_id`, `max_count`)
- Pattern: `^[a-z][a-z0-9_]*$`
- Exception: `self` and `cls` are allowed

### Variables
- Must use **snake_case** (e.g., `total_count`, `user_name`)
- Pattern: `^[a-z][a-z0-9_]*$`
- Exception: Constants in **UPPER_SNAKE_CASE** are allowed (e.g., `MAX_SIZE`, `DEFAULT_VALUE`)
- Exception: Names starting with underscore are allowed (private variables)