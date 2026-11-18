---
description: Run tests for an example project
---

Run tests for the specified example directory. Detect whether it's a Go or TypeScript example and run the appropriate test command.

For Go examples (has `go.mod`):
```bash
cd $ARGUMENTS && go test ./...
```

For TypeScript examples (has `package.json`):
```bash
cd $ARGUMENTS && npm test
```

If no argument is provided, ask which example to test.

Report the test results clearly, noting any failures.
