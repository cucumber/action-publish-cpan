[![Test](https://github.com/cucumber/action-publish-cpan/actions/workflows/test.yaml/badge.svg)](https://github.com/cucumber/action-publish-cpan/actions/workflows/test.yaml)

# action-publish-cpan

Publishes a Perl module to https://cpan.org using `Dist::Zilla`

## Inputs

* `cpan-user`
* `cpan-password`
* `working-directory` (optional, default `.`)

## Example

```yaml
name: Publish to CPAN

on:
  push:
    branches:
      - "release/*"

jobs:
  publish-ui:
    name: Publish to CPAN
    runs-on: ubuntu-latest
    environment: Release
    steps:
      - uses: actions/checkout@v2
      - uses: cucumber/action-publish-cpan@v1.0.0
        with:
          cpan-user: ${{ secrets.CPAN_USER }}
          cpan-password: ${{ secrets.CPAN_PASSWORD }}
          working-directory: "perl"
```
