```markdown
# Android_Runtime_Permissions Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill covers the development patterns and conventions used in the `Android_Runtime_Permissions` repository, a TypeScript codebase focused on handling Android runtime permissions. The repository does not use a specific framework and follows custom conventions for file organization, imports, exports, and testing. This guide will help you contribute code consistent with the project's established style and workflows.

## Coding Conventions

### File Naming
- Use **camelCase** for all file names.
  - Example: `permissionHandler.ts`, `requestPermissions.ts`

### Imports
- Use **relative imports** for referencing other files within the project.
  - Example:
    ```typescript
    import { checkPermission } from './permissionHandler';
    ```

### Exports
- Use **named exports** instead of default exports.
  - Example:
    ```typescript
    // In permissionHandler.ts
    export function checkPermission() { ... }
    
    // In another file
    import { checkPermission } from './permissionHandler';
    ```

### Commit Messages
- No strict format; commit messages are freeform and average around 23 characters.
  - Example: `add permission check logic`

## Workflows

### Adding a New Permission Handler
**Trigger:** When you need to support a new Android permission.
**Command:** `/add-permission-handler`

1. Create a new camelCase-named TypeScript file for the handler (e.g., `cameraPermission.ts`).
2. Implement the permission logic using named exports.
3. Import your handler in relevant files using a relative import.
4. Write or update tests in a corresponding `.test.ts` file.
5. Commit your changes with a clear, concise message.

### Running Tests
**Trigger:** When you want to verify code correctness.
**Command:** `/run-tests`

1. Identify test files (pattern: `*.test.*`).
2. Run your preferred TypeScript-compatible test runner (framework is unspecified).
3. Review test output and fix any failures.
4. Commit any necessary fixes or improvements.

## Testing Patterns

- Test files follow the pattern: `*.test.*` (e.g., `permissionHandler.test.ts`).
- The testing framework is not specified; use a TypeScript-compatible runner.
- Tests should cover all exported functions and edge cases.

  Example test file:
  ```typescript
  import { checkPermission } from './permissionHandler';

  describe('checkPermission', () => {
    it('should return true for granted permission', () => {
      // Test logic here
    });
  });
  ```

## Commands
| Command                  | Purpose                                         |
|--------------------------|-------------------------------------------------|
| /add-permission-handler  | Guide for adding a new permission handler       |
| /run-tests               | Steps to run and verify tests                   |
```
