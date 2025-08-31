# setup-mono

A composite GitHub Action that ensures Mono is installed on Ubuntu runners, including Ubuntu 24.04 and later (where Mono is no longer preinstalled).

## Usage

```yaml
- uses: xtadex/setup-mono@v1
```

Or for internal use in your repo:

```yaml
- uses: ./.github/actions/setup-mono
```

## What it does

- Adds the official Mono repository and GPG key
- Installs `mono-complete`
- Verifies Mono installation

## Example Workflow

```yaml
name: Build with Mono

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: xtadex/setup-mono@v1  # Or ./.github/actions/setup-mono for local
      - run: mono --version
```

## License

MIT
