# Scala Coding Standards

## 1. Method Length

**Rule:** `method-length`

**Description:** Methods should not exceed 15 lines of code

**Details:**
- Maximum allowed lines: 15
- Excludes comments (single-line `//` and multi-line `/* */`) and blank lines from the count
- Detects methods defined with `def` keyword

**Suggestion:** Consider extracting logic into helper methods or using higher-order functions like map, filter, fold.

---

## 2. Naming Conventions

**Rule:** `naming-conventions`

**Description:** Follow Scala conventions: camelCase for methods/vals, PascalCase for classes

**Details:**

### Classes, Traits, Objects
- Must use **PascalCase** (e.g., `MyClass`, `UserService`, `DataProcessor`)
- Pattern: `^[A-Z][a-zA-Z0-9]*$`
- Applies to: `class`, `trait`, `object`, `case class`, `sealed class`, `abstract class`, `final class`

### Methods
- Must use **camelCase** (e.g., `getUserData`, `processItems`, `calculateTotal`)
- Pattern: `^[a-z][a-zA-Z0-9]*$`
- **Do not use snake_case** for methods
- Exception: Names starting with underscore are allowed

### Values and Variables (val/var)
- Must use **camelCase** (e.g., `userName`, `totalCount`, `maxRetries`)
- Pattern: `^[a-z][a-zA-Z0-9]*$`
- Exception: Constants in **UPPER_SNAKE_CASE** are allowed (e.g., `MAX_SIZE`, `DEFAULT_TIMEOUT`)
- Exception: Names starting with underscore are allowed

---

## 3. Immutability

**Rule:** `immutability`

**Description:** Prefer val over var and immutable collections

**Details:**

### Avoid `var`
- Using `var` introduces mutable state
- **Suggestion:** Consider using `val` with a functional approach. If mutation is needed, isolate it in a local scope.

### Avoid Mutable Collections
The following mutable collections should be avoided:
- `mutable.ArrayBuffer`
- `mutable.ListBuffer`
- `mutable.HashMap`
- `mutable.HashSet`
- `mutable.Map`
- `mutable.Set`
- `mutable.Queue`
- `mutable.Stack`
- `mutable.ArrayDeque`
- `ArrayBuffer`
- `ListBuffer`

### Immutable Alternatives
| Mutable Collection | Immutable Alternative |
|-------------------|----------------------|
| `ArrayBuffer` | `Vector` or `List` |
| `ListBuffer` | `List` |
| `HashMap` | `Map` |
| `HashSet` | `Set` |
| `mutable.Map` | `immutable.Map` |
| `mutable.Set` | `immutable.Set` |
| `mutable.Queue` | `immutable.Queue` |
| `mutable.Stack` | `List` (as a stack) |
| `ArrayDeque` | `Vector` |

**Suggestion:** Consider using immutable collections with functional operations (map, filter, fold).