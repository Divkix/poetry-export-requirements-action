# Poetry export requirements.txt file

This action prints exports the pyproject.toml and poetry.lock file to the requirements.txt file.

## Inputs

None

## Outputs

The current working directory will have a `requirements.txt` file generated from the pyproject.toml and poetry.lock files.

## Example usage

```yaml
name: pre-commit

on:
  pull_request:
  push:
    branches: [main]

jobs:
  export-requirements-txt:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-python@v3
    - uses: DivideProjects/poetry-export-requiremets-txt@v1
```

Make sure to use `actions/setup-python@3` as the first action in your pipeline.
