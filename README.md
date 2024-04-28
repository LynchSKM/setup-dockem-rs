![Dockem](docs/logo.png)

This is the Github Action used to install the [dockem](https://github.com/kerren/dockem) `cli`.

# Usage

Below is an example of a Github Action that pulls in the `cli`,

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

      - name: Setup Dockem
        uses: kerren/setup-dockem@v2

      - name: Run Dockem
        run: dockem --version
```

You are able to track a specific version or the lastest within that major version number. For instance, you can use `v2.1.0` like so,

```yaml
      - name: Setup Dockem
        uses: kerren/setup-dockem@v2.1.0

      - name: Run Dockem
        run: dockem --version
```

Or use the latest of version `2` like so,
```yaml
      - name: Setup Dockem
        uses: kerren/setup-dockem@v2

      - name: Run Dockem
        run: dockem --version
```