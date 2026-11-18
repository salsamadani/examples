# CLAUDE.md

This file provides guidance to Claude Code when working with code in this repository.

## Project Overview

This is an **examples and starter templates** repository. It is designed to house runnable example applications, each self-contained in its own directory. Examples may use various languages and frameworks.

## Repository Structure

- Each top-level directory is a self-contained example project
- Examples should be independent — they have their own dependencies and configuration
- A `README.md` in each example explains what it demonstrates and how to run it

## Development Guidelines

### Code Style
- Follow the language conventions of each example (e.g., gofmt for Go, Prettier for TypeScript)
- Keep files focused and under 400 lines where possible
- Prefer immutability — create new objects rather than mutating existing ones
- Functions should be under 50 lines; nesting should be 4 levels or fewer

### Each Example Should Be Self-Contained
- Every example must work independently with its own configuration
- Include a `README.md` in each example explaining what it demonstrates and how to run it
- List all dependencies explicitly — don't rely on shared or global installs

### Security
- Never commit secrets, API keys, or credentials
- Use environment variables or dedicated secrets management for sensitive values
- Validate all user input at API boundaries
- Use parameterized queries for SQL — never interpolate user input into queries
- Error messages must not leak sensitive data

### Testing
- Include tests for non-trivial examples
- Write tests first when fixing bugs (TDD: red, green, refactor)
- Aim for meaningful coverage of the example's core functionality

### Git Workflow
- Use conventional commit format: `<type>: <description>` (feat, fix, docs, refactor, test, chore)
- Keep commits focused on a single change
- Write clear PR descriptions explaining what the example demonstrates

## Adding a New Example

1. Create a new directory at the repo root with a descriptive, kebab-case name
2. Add all project configuration (package.json, go.mod, etc.) inside that directory
3. Write a `README.md` covering: what the example shows, prerequisites, how to run, and how to test
4. Ensure the example runs successfully in isolation
