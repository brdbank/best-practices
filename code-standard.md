### Coding Standards – Naming Conventions
Follow this guide to ensure **clean**, **readable**, and **consistent** code across the project.

### 1. Variables
- Use `camelCase` for all variables.
- Use meaningful, descriptive names.
- Avoid short or ambiguous names like `x`, `data`, or `temp`.

```ts
// ✅ Correct
let userEmail = 'example@email.com';
const maxRetryCount = 3;

// ❌ Incorrect
let User_email;
const MAXRETRYCOUNT;
```

### 2. Functions / Methods
- Use `camelCase` for function and method names.
- Function names should be verbs or action-based.

```ts
// ✅ Correct
function getUserInfo() {}
function validateInput(data: any) {}

// ❌ Incorrect
function Get_user_info() {}
function validation_input() {}
```

### 3. Classes & Interfaces
- Use PascalCase for class and interface names.
- Prefix interfaces with I (optional, but if used, use it consistently).

```ts
// ✅ Correct
class UserService {}
interface IUser {}

// ❌ Incorrect
class user_service {}
interface user {}
```

### 4. Folders / Backend
- Use `kebab-case` for folders.
- Folders should be named by `feature`, not by type (when using feature-based structure).

```bash
# ✅ Correct
/user-profile
/authentication
/loan-application

# ❌ Incorrect
/UserProfile
/services
/controllers
```

### 5. Files / Backend
- Use `kebab-case` for file names.
- Files should reflect the content or role.

```bash
# ✅ Correct
user.service.ts
loan.controller.ts
auth.module.ts

# ❌ Incorrect
UserService.ts
LoanController.ts
authModule.ts
```

### 6. Constants
- Use `UPPER_SNAKE_CASE` for constants.

```ts
// ✅ Correct
const MAX_LOGIN_ATTEMPTS = 5;

// ❌ Incorrect
const maxLoginAttempts = 5;
```

### 7. Tests
- Test files should follow the pattern: `filename.spec.ts` or `filename.test.ts`
- Place test files next to the code they test or in a dedicated `__tests__` or `test/` folder.

```bash
user.service.ts
user.service.spec.ts
```

### 8. Enums
- Use `PascalCase` for the enum name.
- Use `UPPER_SNAKE_CASE` for enum members.

```ts
// ✅ Correct
enum UserRole {
  ADMIN = 'ADMIN',
  USER = 'USER',
}
```
