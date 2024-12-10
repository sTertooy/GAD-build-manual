# gda-manual

This GitHub action builds the manual(s) of the GAP package located in the current directory. Based on [gap-actions/build-pkg-docs](https://github.com/gap-actions/build-pkg-docs).


## Usage

This action can optionally be called in the workflow of a GAP package to build its manual(s).


### Example

```yaml
name: CI

on:
  - push
  - pull_request
  - workflow_dispatch

jobs:
  test:
    name: "Test the GAP package"
    runs-on: ubuntu-latest

    container:
      image: ghcr.io/stertooy/gda-image:tex-slim

    steps:
      - uses: actions/checkout@v4
      - uses: stertooy/gda-build-pkg@v1
      - uses: stertooy/gda-manual@v1
```
