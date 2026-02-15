---
name: lint-and-validate
description: Validation tools for code quality (linting, type checking)
version: 1.0.0
author: Colossus Team (Adapted)
tags: [development, quality, validation]
tools:
  - name: lint_runner
    description: Runs linters (eslint, ruff, etc.) on the project.
    parameters:
      - name: path
        type: string
        required: false
        default: "."
        description: Path to the project root.
    return_type: string
  - name: type_coverage
    description: Checks type coverage for the project.
    parameters:
      - name: path
        type: string
        required: false
        default: "."
        description: Path to the project root.
    return_type: string
---

# Lint and Validate Skill

This skill provides tools to validate code quality.

## Tools

### lint_runner

Runs the appropriate linter for the project type (Node.js, Python, etc.).

**Usage:**
```bash
python scripts/lint_runner.py .
```

### type_coverage

Checks the type coverage of the project.

**Usage:**
```bash
python scripts/type_coverage.py .
```
