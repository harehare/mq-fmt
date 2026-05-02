<h1 align="center">mq-fmt</h1>

Formatter for [mq](https://github.com/harehare/mq) query language (`.mq`) files. Automatically enforces consistent code style, and integrates as an external subcommand of `mq`.

## Installation

### Quick Install

```sh
curl -sSL https://raw.githubusercontent.com/harehare/mq-fmt/main/bin/install.sh | bash
```

### Cargo

```sh
# Install from crates.io
cargo install mq-fmt

# Install from GitHub
cargo install --git https://github.com/harehare/mq-fmt.git mq-fmt
```

Once installed, `mq-fmt` is automatically available as `mq fmt` because `mq` discovers external subcommands named `mq-*` in `~/.local/bin` and `PATH`.

## Usage

```sh
# Format all .mq files under the current directory
mq-fmt

# Format specific files
mq-fmt file.mq another.mq

# Check formatting without modifying files (exits with non-zero if unformatted)
mq-fmt --check file.mq

# Use 4-space indentation
mq-fmt --indent-width 4 file.mq

# Sort imports and functions
mq-fmt --sort-imports --sort-functions file.mq
```

### Via mq

```sh
mq fmt file.mq
mq fmt --check file.mq
```

## Options

| Option             | Short | Description                              | Default |
| ------------------ | ----- | ---------------------------------------- | ------- |
| `--indent-width`   | `-i`  | Number of spaces for indentation         | `2`     |
| `--check`          | `-c`  | Check formatting without modifying files | `false` |
| `--sort-imports`   |       | Sort import statements                   | `false` |
| `--sort-functions` |       | Sort function definitions                | `false` |
| `--sort-fields`    |       | Sort record fields                       | `false` |

## Exit Codes

| Code | Meaning                                                                     |
| ---- | --------------------------------------------------------------------------- |
| `0`  | All files are formatted (or were successfully formatted)                    |
| `1`  | A file is not formatted (only when `--check` is used), or an error occurred |

## License

Licensed under the MIT License.
