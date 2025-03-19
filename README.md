# fortitude-pre-commit

A [pre-commit](https://pre-commit.com/) hook for [Fortitude](https://github.com/PlasmaFAIR/fortitude).

Distributed as a standalone repository to enable installing Fortitude via prebuilt
wheels from [PyPI](https://pypi.org/project/fortitude-lint/).


### Using Fortitude with pre-commit

To run [Fortitude](https://fortitude.readthedocs.io/en/stable/) via pre-commit, add the
following to your `.pre-commit-config.yaml`:

```yaml
repos:
- repo: https://github.com/PlasmaFAIR/fortitude-pre-commit
  # Fortitude version.
  rev: v0.6.2
  hooks:
    - id: fortitude
```

Extra arguments may be provided to the lint hook:

```yaml
repos:
- repo: https://github.com/PlasmaFAIR/fortitude-pre-commit
  # Fortitude version.
  rev: v0.6.2
  hooks:
    - id: fortitude
      args: ["--fix", "--unsafe-fixes", "--preview"]
```

When running with `--fix`, Fortitude's lint hook should be placed before any code
formatters in use.

Note that Fortitude will run with the option `--force-exclude` switched on by default.
This will prevent Fortitude from checking files that have been explicitly added to your
exclude list in `fpm.toml` or `fortitude.toml`.

## License

This repository in based on [ruff-pre-commit](https://github.com/astral-sh/ruff-pre-commit),
which is licensed under either of:

- Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE-ruff) or <https://www.apache.org/licenses/LICENSE-2.0>)
- MIT license ([LICENSE-MIT](LICENSE-MIT-ruff) or <https://opensource.org/licenses/MIT>)

It is additionally licensed under the [MIT license](LICENSE) for the PlasmaFAIR project.
