# RISE RISC-V Runner - Sample Test2

This repository demonstrates how to use the [RISE RISC-V Runner](https://github.com/apps/rise-risc-v-runners) GitHub App to run GitHub Actions workflows on RISC-V hardware.

The RISE RISC-V Runner app provides hosted RISC-V runners for GitHub Actions, allowing open-source projects to build and test on real RISC-V hardware with no infrastructure setup required.

## Setup

1. Install the [RISE RISC-V Runner](https://github.com/apps/rise-risc-v-runners) GitHub App on your repository or organization.
2. In your workflow files, use `runs-on: ubuntu-24.04-riscv` to target RISC-V runners.

## Usage

Create a workflow file under `.github/workflows/` (e.g. `.github/workflows/ci.yml`):

```yaml
name: CI

on:
  push:
  pull_request:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-24.04-riscv
    steps:
      - uses: actions/checkout@v4
      - run: echo "Running on $(uname -m)"
```

The `runs-on` label `ubuntu-24.04-riscv` routes the job to a RISE-provided RISC-V runner with Ubuntu 24.04.

## Example

See [`.github/workflows/hello.yml`](.github/workflows/hello.yml) for a minimal working example.
