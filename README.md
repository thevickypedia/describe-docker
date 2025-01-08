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
name: Docker Hub Description

on:
  push:
  workflow_dispatch:

jobs:
  describe-docker:
    runs-on: ubuntu-latest
    steps:
      - uses: thevickypedia/describe-docker@v1
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}
          summary: "Short description to summarize the docker image"
          repository: "vaultapi"
          filename: "README.md"
```

- Commit your changes to trigger the workflow or run the workflow manually.

### Action inputs

- `username` - Docker hub username.
- `password` - Docker hub password.
- `registry` - Docker hub registry URL (defaults to https://hub.docker.com/v2)
- `repository` - Name of the docker image repository. _Docker hub username is prefixed automatically_.
- `summary` - Docker repository overview (100-character limit)
- `filename` - Filename to read the full description for the docker image.

## License & copyright

&copy; Vignesh Rao

Licensed under the [MIT License][license]

[marketplace]: https://github.com/marketplace/actions/describe-docker
[license]: https://github.com/thevickypedia/describe-docker/blob/main/LICENSE
