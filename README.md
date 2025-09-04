# Setup Codee

Set up a Codee Formatter & Analyser on Linux and Windows runners.

- [Usage](#usage)
- [Options](#options)
- [Environment variables](#environment-variables)
- [Runner compatibility](#runner-compatibility)
- [License](#license)


## Usage

```yaml
jobs:
  test:
    runs-on: ${{ matrix.os }}
    strategy:
      fail-fast: false
      matrix:
        os: [ubuntu-latest, windows-latest, ubuntu-24.04-arm]

    steps:
      - uses: foxtran/setup-codee@v1

      - run: |
          codee format --help
```


## Options

- *version*: Version of the Codee tools. See [Codee Changelog](https://docs.codee.com/changelog/) to pick the latest.


## Environment variables

Action updates PATH environment variable for allowing to use `codee` command.


## Runner compatibility

Codee tools are available for Windows x86\_64, Linux x86\_64 and Linux AArch64 platforms.


## License

Setup Codee is [MIT licensed](./LICENSE).
