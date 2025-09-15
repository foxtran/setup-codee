# Setup Codee


[![Test](https://github.com/foxtran/setup-codee/actions/workflows/test.yml/badge.svg)](https://github.com/foxtran/setup-codee/actions/workflows/test.yml)


Set up a Codee Formatter & Analyser on Linux and Windows runners.

- [Usage](#usage)
- [Options](#options)
- [Environment variables](#environment-variables)
- [Runner compatibility](#runner-compatibility)
- [License](#license)


## Usage

One can use this action in the following way to check that `codee format` does not change source code:

```yaml
jobs:
  format:
    runs-on: ${{ matrix.os }}
    strategy:
      fail-fast: false
      matrix:
        os: [ubuntu-latest, windows-latest, ubuntu-24.04-arm]

    steps:
    - uses: actions/checkout@v4
    - uses: foxtran/setup-codee@v1

    - name: Run Fortran formatter
      run: |
        codee format . --verbose

    - name: Check for uncommitted changes
      run: |
        git diff --exit-code
```


## Options

- *version*: Version of the Codee tools. See [Codee Changelog](https://docs.codee.com/changelog/) to pick the latest.


## Environment variables

Action updates PATH environment variable for allowing to use `codee` command.


## Runner compatibility

Codee tools are available for Windows x86\_64, Linux x86\_64 and Linux AArch64 platforms.


## License

Setup Codee is [MIT licensed](./LICENSE).
