## 📘 Code Commenting Guidelines
A guide to writing meaningful, maintainable, and clean comments in codebases.

---
## ❌ Avoid Using Inline Comments Everywhere
Inline comments placed beside every line of code can lead to:
- **Cluttered code**: Too many comments make it harder to read the actual code.
- **Redundancy**: When the comment simply restates what the code already says.
- **Maintenance** overhead: Outdated comments can mislead developers.

##### 🔴 Bad Example:

```ts
let user = 'John'; // Set the user
let age = 30; // Set the age
let isAdmin = true; // Set admin flag
```

#### ✅ Preferred:
```ts
// Set initial user information for login session
let user = 'John';
let age = 30;
let isAdmin = true;
```

## ✅ When to Use Inline Comments
Use inline comments sparingly and purposefully in the following cases:
- To explain **non-obvious logic** or edge cases.
- To clarify **"why"** something is done, not **"what"** (the code shows the "what").
- To mark **TODOs**, **FIXMEs**, or warnings.

## 🟨 Use JSDoc for Structured Documentation
JSDoc is a standardized way to document functions, parameters, return values, and expected behavior in JavaScript or TypeScript.

✨ Benefits of Using JSDoc:
- Helps editors (like VS Code) show **tooltips** and **type hints**.
- Makes it easier to generate documentation automatically.
- Provides context for new developers without needing to read full function code.

##### ✅ Example:
```ts
/**
 * Calculates the loan interest.
 *
 * @param {number} principal - The initial loan amount.
 * @param {number} rate - Annual interest rate (e.g., 0.05 for 5%).
 * @param {number} years - Duration of the loan in years.
 * @returns {number} - Total interest to be paid.
 */
function calculateInterest(principal, rate, years) {
  return principal * rate * years;
}
```

## 🧠 Summary
| Practice              | Use Case                                                  |
| --------------------- | --------------------------------------------------------- |
| Inline Comments       | To explain **why**, clarify complex logic, or flag TODOs. |
| Block Comments        | To describe sections of logic or multiple lines.          |
| JSDoc                 | For **functions, classes, parameters, and return types**. |
| Avoid over-commenting | Let clean code and naming do the work.                    |

>✅ **Clean code is self-documenting. Comment only when it adds clarity or context.**




