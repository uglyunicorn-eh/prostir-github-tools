# Prostir GitHub Actions

Set of GitHub re-usable actions:

* [python-prepare](#python-prepare.yml)
* [python-prepare-dev](#python-prepare-dev.yml)

## Actions

### python-prepare.yml

Prepares Python environment.

**Inputs:**

* `python-version` — Python version (Default: `"3.9"`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)

### python-prepare-dev.yml

Prepares Python environment including developer requirements (black, pylint, etc).

**Inputs:**

* `python-version` — Python version (Default: `"3.9"`)

**Secrets:**

* `GH_ACTIONS_SSH_PRIVATE_KEY` — Private SSH key to be able to clone the repos using SSH (Required)
