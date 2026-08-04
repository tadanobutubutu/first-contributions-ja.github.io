```markdown
# first-contributions-ja.github.io Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the `first-contributions-ja.github.io` repository, a TypeScript project built with Next.js. It covers code style conventions, common workflows (such as updating configurations, documentation, and merging branches), and testing patterns. Use this as a reference to ensure consistency and efficiency when working within this codebase.

## Coding Conventions

- **File Naming:** Use camelCase for file names.
  - Example: `contributorList.ts`, `userProfile.tsx`
- **Import Style:** Use relative imports for modules within the project.
  - Example:
    ```typescript
    import { Contributor } from './contributorList';
    ```
- **Export Style:** Use named exports.
  - Example:
    ```typescript
    // contributorList.ts
    export const Contributor = { ... };
    ```
    ```typescript
    import { Contributor } from './contributorList';
    ```
- **Commit Messages:** Freeform, but often use the `chore` prefix for maintenance or non-feature changes.
  - Example: `chore: update dependencies [skip ci]`
- **Average Commit Message Length:** ~41 characters.

## Workflows

### Update Config or Workflow File
**Trigger:** When you need to change build/test settings or CI workflows (e.g., updating `tsconfig.json` or GitHub Actions).
**Command:** `/update-config`

1. Edit the relevant config or workflow file (e.g., `tsconfig.json`, `tsconfig.test.json`, `.github/workflows/jaipilot-generate.yml`).
2. Commit the change, often including `[skip ci]` in the message to avoid triggering CI unnecessarily.
   - Example:
     ```
     chore: update tsconfig paths [skip ci]
     ```

### Create or Update Documentation File
**Trigger:** When adding or revising project documentation (such as `GITAUTO.md`).
**Command:** `/update-docs`

1. Create or edit the documentation file (e.g., `GITAUTO.md`).
2. Commit the new or updated file, optionally with `[skip ci]` in the message.
   - Example:
     ```
     chore: update GITAUTO.md [skip ci]
     ```

### Merge Main into Feature Branch
**Trigger:** When your feature branch needs to be updated with the latest changes from `main`.
**Command:** `/merge-main`

1. Merge the `main` branch into your feature branch.
   - Example:
     ```
     git checkout feature/my-feature
     git merge main
     ```
2. Resolve any merge conflicts, especially in files like `package-lock.json`, `package.json`, `.github/workflows/jaipilot-generate.yml`, and `Contributors.json`.
3. Commit the merge, updating files as needed.
   - Example:
     ```
     chore: merge main into feature/my-feature
     ```

### Empty Commit to Trigger CI
**Trigger:** When you want to manually trigger CI/CD pipelines without changing any files.
**Command:** `/trigger-ci`

1. Create an empty commit with a descriptive message.
   - Example:
     ```
     git commit --allow-empty -m "chore: trigger CI pipeline"
     ```
2. Push the commit to trigger CI.

## Testing Patterns

- **Test File Pattern:** Test files are named using the `*.test.*` convention (e.g., `userProfile.test.ts`).
- **Testing Framework:** Not explicitly detected; refer to project documentation or `package.json` for details.
- **Typical Test Example:**
  ```typescript
  // userProfile.test.ts
  import { render } from '@testing-library/react';
  import { UserProfile } from './userProfile';

  test('renders user profile', () => {
    const { getByText } = render(<UserProfile name="Alice" />);
    expect(getByText('Alice')).toBeInTheDocument();
  });
  ```

## Commands

| Command        | Purpose                                                      |
|----------------|--------------------------------------------------------------|
| /update-config | Update configuration or workflow files (e.g., CI, tsconfig). |
| /update-docs   | Create or update documentation files.                        |
| /merge-main    | Merge the latest main branch into your feature branch.       |
| /trigger-ci    | Create an empty commit to manually trigger CI pipelines.     |
```