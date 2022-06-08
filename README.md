# Prostir GitHub Tools

Set of GitHub tools, workflows, etc:

* Workflows:
    * [python-pylint](#python-pylint)
    * [python-pytest](#python-pytest)

## Workflows

### python-pylint

Analizes code with pylint.

**Inputs:**

* `python-version` — Python version (Default: `"3.9"`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)

Example:

```yaml
jobs:
  analize:
    uses: uglyunicorn-eh/prostir-github-tools/.github/workflows/python-pylint.yml@main
    secrets: inherit
```

### python-pytest

Runs unit tests with pytest. If specified, uploads code coverage to https://codecove.io/

**Inputs:**

* `python-version` — Python version (Default: `"3.9"`)
* `upload-codecov` — Whenever it should upload coverage to Codecov. If `true` requires a secret `CODECOV_TOKEN` (Default: `false`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)
* `CODECOV_TOKEN` — Codecov token. Required if `upload-codecov` is `true`

Example:

```yaml
jobs:
  test:
    uses: uglyunicorn-eh/prostir-github-tools/.github/workflows/python-pytest.yml@main
    secrets: inherit
    with:
      upload-codecov: true
```
