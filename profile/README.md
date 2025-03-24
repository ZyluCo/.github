# New Developer Guide

Welcome to the team! This guide will help you get started with our development workflow, including how to create branches, follow commit conventions, and raise pull requests (PRs).

## 1. Branching Strategy
We follow a structured branching model to keep our development organized:

- **dev**: This is the main working branch where all feature development and bug fixes happen.
- **main**: This is the production branch. No direct changes should be made to this branch.

### Creating a New Branch
When working on a new feature or fix, create a branch from `dev`:
```
git checkout dev   # Switch to dev branch
git pull origin dev # Ensure you have the latest code
git checkout -b feature/your-feature-name  # Create a new branch
```

- Use `feature/your-feature-name` for new features.
- Use `fix/your-fix-name` for bug fixes.
- Use `chore/task-name` for maintenance tasks.

Once your branch is created, make your changes and commit them following our commit convention.

## 2. Conventional Commits
This repository follows the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0) specification to ensure consistent commit messages and easy tracking of changes.

### Commit Message Format
```
type(scope): description [CU-<clickup_task_id>]
```
- **type**: Describes the purpose of the change.
- **scope** (optional): Specifies the affected module or feature.
- **description**: A concise summary of the change.
- **ClickUp task ID** (optional but recommended): Links the commit to a specific ClickUp task.

### Common Types
- **feat**: A new feature  
- **fix**: A bug fix  
- **docs**: Documentation changes  
- **style**: Code style changes (formatting, missing semi-colons, etc.)  
- **refactor**: Code restructuring without changing functionality  
- **perf**: Performance improvements  
- **test**: Adding or updating tests  
- **chore**: Maintenance tasks, dependencies updates, etc.  
- **ci**: Changes to CI/CD configuration  

### Example Commits
```
feat(auth): add Google login support [CU-12345]
fix(api): resolve issue with token expiration [CU-67890]
chore(deps): update Laravel to 10.x [CU-11223]
```

## 3. Raising a Pull Request (PR)
Once your changes are committed, push them to the remote repository and create a pull request:

### Pushing Your Branch
```
git push origin feature/your-feature-name
```

### Creating a Pull Request
1. Go to the repository on GitHub/GitLab.
2. Navigate to the "Pull Requests" section.
3. Click "New Pull Request."
4. Select `dev` as the base branch and your feature branch as the compare branch.
5. Add a meaningful title and description.
6. Link the ClickUp task (if applicable).
7. Request a review from the appropriate team members.

### PR Review and Merging
- The PR must be reviewed and approved by at least one other developer.
- Once approved, it can be merged into `dev`.
- Do **not** merge directly into `main`. `main` is updated only through release processes.

## 4. Keeping Your Branch Updated
To avoid conflicts, regularly sync your branch with `dev`:
```
git checkout dev
git pull origin dev
git checkout feature/your-feature-name
git merge dev
```
Resolve any conflicts if necessary and commit the changes.

---

By following these guidelines, we maintain a clean, structured, and efficient development workflow. If you have any questions, feel free to ask your team lead or refer to the documentation.
