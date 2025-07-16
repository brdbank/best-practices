Welcome to the team's Git workflow guide. This document explains how we manage branches, pull requests, and code merges for consistency, clarity, and safety in our development process.

---

## 🔀 Branching Strategy

### `main`
- **Always deployable**: The `main` branch reflects the most stable, tested, and production-ready code.
- **Hotfixes originate from `main`**.
- Only Maintainers or DevOps are allowed to merge into `main`.

### `develop`
- **Staging branch**: Holds completed and approved work that is pending **User Acceptance Testing (UAT)**.
- **Source for all new feature branches**.
- checkout this [link](https://github.com/brdbank/best-practices/wiki/Git-naming-conventions-and-best-practices) for branching conventions
- Only Maintainers or DevOps are allowed to merge into `develop`.

### `ft/*`
- Developers must branch off `develop` using the format as shown [here](https://github.com/brdbank/best-practices/wiki/Git-naming-conventions-and-best-practices)

### `hotfix/*`
- Used for urgent fixes to production.
- Branch off from `main` using the format:  
  `hotfix/<short-description>`  
  _Example_: `hotfix/fix-crash-on-dashboard`
- Once completed:
  - PR is created and reviewed.
  - Merged into both `main` and `develop`.

---

## 🚧 Pull Request Workflow

1. **Branch off the correct base**:
   - `feature/*` → from `develop`
   - `hotfix/*` → from `main`

2. **Push and open a Pull Request**:
   - **Title**: Concise summary of change  
   - **Description**: Include context, screenshots (if applicable), and link to issue/ticket

3. **Request Review**:
   - Assign at least one reviewer.
   - Developers are **not allowed** to merge their own PRs.

4. **Merge Rules**:
   - PR must be approved.
   - PR is merged by the DevOps.
   - PR into `develop` or `main` must pass all CI checks.

5. **After PR merge**:
   - Delete the feature/hotfix branch.
   - Tag the release (if hotfix or release candidate).

---

## 🛡️ Rules & Best Practices

- **Never push directly to `main` or `develop`**.
- **Do not rebase public/shared branches.**
- Feature branches must be kept **up to date** with `develop` via `rebase`.
- Keep PRs **small and focused** — ideally under 400 lines of change.
- Use appropriate **PR labels** 

---

## 🧪 Deployment Pipeline

| Branch       | Environment     | Notes                             |
|--------------|------------------|------------------------------------|
| `main`       | Production       | Auto-deployed or manually triggered |
| `develop`    | Staging / UAT    | Used for QA & business validation  |
| `feature/*`, `hotfix/*` | None            | Use preview environments or local testing |

---

## 🙋 FAQ

- **Q: Can I merge my own PR?**  
  **A:** No. A different team member must approve and merge the PR.

- **Q: What happens after a hotfix?**  
  **A:** It is merged into both `main` and `develop` to keep branches aligned.

- **Q: Who can merge to `main`?**  
  **A:** Only designated maintainers/DevOps.
