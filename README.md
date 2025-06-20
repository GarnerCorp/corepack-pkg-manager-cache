# corepack-pkg-manager-cache

A collection of cached corepack-supported package managers

## Example Workflow
```
name: CI
on:
  push:
  pull_request:

jobs:

  run:
    runs-on: ubuntu-latest
    permissions:
      contents: read
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        
      - name: Get package manager
        uses: GarnerCorp/build-actions/install-package-manager@main
        with:
            cache-repository: https://github.com/GarnerCorp/corepack-pkg-manager-cache

      - name: Run tests
        run: yarn test
```