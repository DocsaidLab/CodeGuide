# Git Commit Rule

This document outlines the recommended commit rules and guidelines for Git in large-scale projects. It includes commit categories and versioning rules.

## Commit Message Format

A commit message should consist of a brief summary, an optional body, and a footer. The summary and footer must adhere to specific guidelines.

### Summary

The commit summary should provide a concise description of the changes introduced by the commit. It should follow these guidelines:

- Keep the summary short and descriptive (around 50 characters or less).
- Use the imperative mood (e.g., "Add feature," "Fix bug") to describe the action performed by the commit.
- Start the summary with a capital letter and avoid ending it with a period.
- Include the appropriate category tag from the provided list in square brackets.

Example commit summaries:

```bash
[A] Add authentication feature
[F] Fix null pointer exception
```

### Body (Optional)

The commit body provides additional details about the changes, their motivations, and any relevant information. Use the body when a summary alone is not sufficient to describe the changes.

### Footer

The commit footer is used to reference issues, provide additional context, or include relevant metadata. Use the footer when necessary.

## Commit Categories

To maintain consistency and organization in the commit history, use the provided commit categories as a guideline:

- `[A]` Added: For new features.
- `[C]` Changed: For changes in existing functionality.
- `[D]` Deprecated: For soon-to-be-removed features.
- `[R]` Removed: For now removed features.
- `[F]` Fixed: For bug fixes.
- `[S]` Security: For addressing vulnerabilities.

When making a commit, choose an appropriate category and include it at the beginning of the commit message summary, within square brackets.

## Git Versioning Rules

Git versioning follows a three-level version format: `a.b.c`, where:

- `a` represents a structural breaking change that affects usage, implementation, or other significant aspects.
- `b` represents functional additions or partial usage adjustments.
- `c` represents bug fixes.

Use this versioning scheme to track and communicate changes effectively within your project.

## Branch Naming

To maintain a well-structured branching model, use the following naming conventions:

- `main`: The main branch representing the stable production code.
- `release/{...}`: Release branches for version releases.
- `refactor/{...}`: Refactoring branches for code restructuring.
- `feat/{...}`: Feature branches for implementing new features.
- `bugfix/{...}`: Bugfix branches for fixing bugs found in the main branch.
- `hotfix/{...}`: Hotfix branches for fixing bugs found in release branches.
- `dev/{...}`: Development branches for long-term development or experimentation.
- `infra/{...}`: Infrastructure branches for infrastructure-related changes, such as package updates or CI/CD adjustments.

These branch names provide clarity and structure to your Git repository, making it easier to understand the purpose and scope of each branch.

Following these guidelines for commit messages, versioning, and branch naming will contribute to a clean commit history, efficient collaboration, and effective project management within your Git repository.
