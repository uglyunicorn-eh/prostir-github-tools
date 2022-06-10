# Prostir GitHub Tools

Set of GitHub tools, workflows, etc:

* Workflows:
    * [python-chalice-deploy](#python-chalice-deploy)
    * [python-pylint](#python-pylint)
    * [python-pylint-pkg](#python-pylint-pkg)
    * [python-pytest](#python-pytest)

## Workflows

### python-chalice-deploy

Deploys Chalice application to AWS

**Inputs:**

* `stage` — Stage to deploy (Required)
* `aws-region` — AWS region (Default: `"us-west-2"`)
* `python-version` — Python version (Default: `"3.9"`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)
* `AWS_ACCESS_KEY_ID` — AWS Access Key ID (Required)
* `AWS_SECRET_ACCESS_KEY` — AWS Secret Access Key (Required)

Example:

```yaml
jobs:
  analize:
    uses: uglyunicorn-eh/prostir-github-tools/.github/workflows/python-chalice-deploy.yml@main
    secrets: inherit
    with:
      stage: prod
```

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


### python-pylint-pkg

Analizes packages code with pylint.

**Inputs:**

* `python-version` — Python version (Default: `"3.9"`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)

Example:

```yaml
jobs:
  analize:
    uses: uglyunicorn-eh/prostir-github-tools/.github/workflows/python-pylint-pkg.yml@main
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
