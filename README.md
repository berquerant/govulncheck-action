# govulncheck-action

A GitHub Action to run [`govulncheck`](https://pkg.go.dev/golang.org/x/vuln/cmd/govulncheck).

## Features

- Fails the build only when vulnerabilities with available fixes are detected.

## Usage

### Minimal Example

```yaml
name: Vulnerability Scan

on:
  push:
    branches: [ main ]
  pull_request:

jobs:
  govulncheck:
    runs-on: ubuntu-latest
    steps:
      - uses: berquerant/govulncheck-action@v1
```

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| `checkout` | Checkout the repository | `false` | `true` |
| `patterns` | Patterns to scan | `false` | `./...` |
| `chdir` | Change to dir before running govulncheck | `false` | `.` |
| `go-version-file` | Path to the go.mod, go.work, .go-version, or .tool-versions file. | `false` | |
| `check-latest` | Set this option to true if you want the action to always check for the latest available Go version that satisfies the version spec | `false` | `true` |
| `cache` | Used to specify whether caching is needed. Set to true, if you'd like to enable caching. | `false` | `true` |
| `cache-dependency-path` | Used to specify the path to a dependency file (for monorepos) - go.sum | `false` | `""` |
| `version` | The version of govulncheck | `false` | `latest` |
