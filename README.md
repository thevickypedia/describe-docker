[![made-with-gha](https://img.shields.io/badge/Made%20with-Github_Actions-black?style=for-the-badge&logo=GitHub)][marketplace]

# Describe Docker
`describe-docker` is a GitHub action designed to update docker image description.

## Install Guide

#### Add `describe-docker` action to your build workflow

- In your GitHub repository, select the Actions tab and either add or edit a workflow.
- Search for `describe-docker` from the [Marketplace][marketplace] tab on the right.
- Copy and paste the yaml into your workflow.

**[OR]**

Copy & paste the following workflow definition into your project `.github/workflows/describe-docker.yml`

```yaml
name: Validate hyperlinks in markdown files

on:
  push:
  workflow_dispatch:

jobs:
  describe-docker:
    runs-on: ubuntu-latest  # Can run on multiple operating systems
    steps:
      - uses: thevickypedia/describe-docker@v1
```

- Commit your changes to trigger the workflow or run the workflow manually.

### Action inputs

- `docker_username` - Docker hub username.
- `docker_password` - Docker hub password.
- `docker_registry` - Docker hub registry URL (defaults to https://hub.docker.com/v2)
- `repository_name` - Name of the docker image repository.
- `summary` - Docker repository overview (character limit enforced)
- `description_file` - Filename to read the full description for the docker image.
- `summary_limit` - Summary limit for docker hub overview (defaults to 100 for hub.docker.com)

## License & copyright

&copy; Vignesh Rao

Licensed under the [MIT License][license]

[marketplace]: https://github.com/marketplace/actions/describe-docker
[license]: https://github.com/thevickypedia/describe-docker/blob/main/LICENSE
