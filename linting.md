This document outlines our linting rules, tooling setup, and workflow to maintain clean, consistent, and error-free code across the entire codebase.

---

## ✅ Why Linting Matters

Linting helps us:
- Enforce consistent coding style
- Prevent common programming errors
- Improve code readability and maintainability
- Reduce time spent on code reviews

---

## 🛠️ Tools We Use

| Language / Stack       | Tool(s)                              |
|------------------------|--------------------------------------|
| JavaScript / TypeScript| ESLint, Prettier                     |
| React                  | ESLint + React plugin                |
| Node.js                | ESLint + Node plugin                 |
| CSS / SCSS             | Stylelint                            |
| Markdown               | markdownlint                         |
| YAML                   | yamllint (optional)                  |

> We use **Prettier** for formatting and **ESLint** for code quality.

---

## ⚙️ Setup Instructions

### 1. Install Dependencies (example: JavaScript/TypeScript)

```bash
npm install --save-dev eslint prettier eslint-config-prettier eslint-plugin-react eslint-plugin-import @typescript-eslint/eslint-plugin @typescript-eslint/parser
```

### 2. ESLint Config (`.eslintrc.json`)

```json
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "prettier"
  ],
  "plugins": ["react", "@typescript-eslint"],
  "parser": "@typescript-eslint/parser",
  "env": {
    "browser": true,
    "es2021": true
  },
  "rules": {
    "react/react-in-jsx-scope": "off"
  }
}
```

### 3. Prettier Config (`.prettierrc`)

```json
{
  "semi": true,
  "singleQuote": true,
  "printWidth": 100,
  "tabWidth": 2,
  "trailingComma": "es5"
}
```

---

## 🚦 Workflow Guidelines

- ✅ Run `npm run lint` before committing
- ✅ Fix all lint and format errors before opening a PR
- ✅ Enable linting in your code editor (VSCode recommended)
- ✅ Lint and format are **enforced via CI**

---

## 📦 NPM Scripts

Add the following to your `package.json`:

```json
"scripts": {
  "lint": "eslint . --ext .ts,.tsx,.js",
  "format": "prettier --write ."
}
```

---

## 🔁 Pre-commit Hooks (Optional but Recommended)

Use [Husky](https://typicode.github.io/husky/) and [lint-staged](https://github.com/okonet/lint-staged) to prevent bad code from being committed.

```bash
npm install --save-dev husky lint-staged
npx husky install
```

In `package.json`:

```json
"lint-staged": {
  "*.{js,ts,tsx}": ["eslint --fix", "prettier --write"]
}
```

---

## 🛡️ CI Integration

Ensure that the CI pipeline runs:

```bash
npm run lint
```

If the lint step fails, the PR must be fixed before merging.

---

## 📘 Editor Extensions

Install these VSCode extensions:
- ESLint
- Prettier – Code formatter
- Stylelint (for CSS/SCSS)
- markdownlint

---

## 🔚 Summary

Linting is not optional. All code must:
- Pass all ESLint checks
- Be properly formatted with Prettier
- Comply with the team's shared rules and standards

Failure to follow linting standards will block PR merges.
