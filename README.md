# GHA to create a GitHub release

## how to use

### prerequisites

You need a config yaml in your `.github/` folder.
The file should be named `release.yml`.
The file should look like this:

```yaml
# .github/release.yml
---
# https://docs.github.com/en/repositories/releasing-projects-on-github/automatically-generated-release-notes

changelog:
  exclude:
    labels:
      - skip-changelog

  categories:
    - title: Breaking Changes 🛠
      labels:
        - backwards-incompatible

    - title: New Features 🎉
      labels:
        - enhancement

    - title: Other Changes
      labels:
        - "*"
```

### usage

```yaml
# .github/workflows/release.yml
---
on:
  push:
    tags:
      - '*'

name: Create GitHub release 🚀

jobs:
  release:
    name: Release
    runs-on: ubuntu-latest
    steps:
      - name: Create GitHub release
        uses: voxpupuli/gha-create-a-github-release@v1
```
