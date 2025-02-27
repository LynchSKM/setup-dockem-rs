![Dockem-RS](docs/logo.png)

This is the GitHub Action used to install the [dockem-rs](https://github.com/LynchSKM/dockem-rs) `cli`.

# Usage

Below is an example of a GitHub Action that pulls in the `cli`,

```yaml
name: "Run Action"

on:
  push:
    branches:
      - main
      - develop

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup dockem-rs
        uses: LynchSKM/setup-dockem-rs@v1

      - name: Run dockem-rs
        run: dockem-rs --version
```

You are able to track a specific version or the latest within that major version number. For instance, you can use `v1.1.1` like so,
```yaml
      - name: Setup dockem-rs
        uses: LynchSKM/setup-dockem-rs@v1.1.1

      - name: Run dockem-rs
        run: dockem-rs --version
```

Or use the latest of version `1` like so,
```yaml
      - name: Setup dockem-rs
        uses: LynchSKM/setup-dockem-rs@v1

      - name: Run dockem-rs
        run: dockem-rs --version
```