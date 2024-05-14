# GHA to create a GitHub release

## how to use

### prerequisites

You need a config yaml in your `.github/` folder.
The file should be named `release.yml`.
The file should look like this:

```yaml
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
