---
description: Run tests for an example project
---

Treat the supplied argument as one repository-relative directory path, not as shell code. If no argument is supplied, ask which example to test.

Before running anything, resolve the path from the repository root and confirm it is an existing directory inside this repository, including after resolving symlinks. Reject absolute paths and paths outside the repository. Do not interpolate the raw argument into a shell command.

Inspect the selected project's test code and scripts before execution:

- If `go.mod` exists and `package.json` does not, run `go test ./...`.
- If `package.json` exists and `go.mod` does not, inspect `pretest`, `test`, `posttest`, and any scripts they invoke. Run `npm test` only if a `test` script exists.
- If both manifests exist, ask which test suite to run.
- If neither exists, report that no supported test project was found and run nothing.

Use the validated directory as the command's working directory when supported. If a shell `cd` is needed, use `cd --` with the resolved path safely shell-quoted as one literal argument.

Do not install dependencies automatically. Report missing prerequisites, commands run, exit status, and failures. Do not report tests as passed unless tests actually ran.
