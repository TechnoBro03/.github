## .github

Default GitHub files for [TechnoBro03](https://github.com/TechnoBro03)

For more information, please see the article on [creating a default community health file for your organization](https://help.github.com/en/articles/creating-a-default-community-health-file-for-your-organization).

## Reusable Workflows

Shared workflows live in `.github/workflows` and can be called from any repository in the organization.

### .NET

```yaml
name: .NET

on:
  pull_request:
    branches: [main]
  push:
    branches: [main]
    tags: ['v*']

jobs:
  dotnet:
    uses: TechnoBro03/.github/.github/workflows/dotnet.yml@main
    with:
      dotnet-version: 10.x
      test: true
      pack: ${{ startsWith(github.ref, 'refs/tags/') }}
      publish-nuget: ${{ startsWith(github.ref, 'refs/tags/') }}
    secrets: inherit
```

### Python

```yaml
name: Python

on:
  pull_request:
    branches: [main]
  push:
    branches: [main]
    tags: ['v*']

jobs:
  python:
    uses: TechnoBro03/.github/.github/workflows/python.yml@main
    with:
      python-version: '3.12'
      test: true
      build-package: ${{ startsWith(github.ref, 'refs/tags/') }}
      publish-testpypi: ${{ github.event_name == 'pull_request' || startsWith(github.ref, 'refs/tags/') }}
      publish-pypi: ${{ startsWith(github.ref, 'refs/tags/') }}
```

### Docker

```yaml
name: Docker

on:
  pull_request:
    branches: [main]
  push:
    branches: [main]
    tags: ['v*']

jobs:
  dotnet:
    uses: TechnoBro03/.github/.github/workflows/dotnet.yml@main
    with:
      test: true

  docker:
    needs: dotnet
    uses: TechnoBro03/.github/.github/workflows/docker.yml@main
    with:
      dockerfile: Dockerfile
      context: .
      push: ${{ github.event_name != 'pull_request' }}
```

Package versions come from each repository's project files. NuGet publishing requires `NUGET_API_KEY` in the consuming repository when `secrets: inherit` is used. PyPI publishing is configured for trusted publishing through repository environments. Docker images are tagged from Git refs and SHAs by `docker/metadata-action`.
