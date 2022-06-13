# Poetry export requirements.txt file

This action prints exports the pyproject.toml and poetry.lock file to the requirements.txt file.

## Inputs

| Name           | Required | Description                                                          | Default          |
| -------------- | -------- | -------------------------------------------------------------------- | ---------------- |
| without-hashes | false    | If you want to use '--without-hashes' option when exporting the file | true             |
| outfile-name   | false    | Custom name for exported file                                        | requirements.txt |

## Outputs
`custom-file-name`: Name of the output file

The current working directory will have a `requirements.txt` file generated from the pyproject.toml and poetry.lock files.

## Example usage

```yaml
name: poetry export requirements.txt

on:
  pull_request:
  push:
    branches: [main]

jobs:
  export-requirements-txt:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: divideprojects/poetry-export-requirements-action@v1
      with:
        without-hashes: true
        outfile-name: requirements.txt
```

Make sure to use `actions/checkout@3` as the first action in your pipeline.
