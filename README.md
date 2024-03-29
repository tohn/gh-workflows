# gh-workflows

Define [reusable workflows][workflows]/[composite actions][actions] to
use in my projects.

## Usage of composite actions

Insert as a step into your workflow:

```yml
---
name: my workflow
on: push  # yamllint disable-line rule:truthy
jobs:
  build_and_deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Prepare
        uses: tohn/gh-workflows@main
```

## Usage of reusable workflows

Insert as a job into your workflow:

```yml
---
name: my workflow
on: push  # yamllint disable-line rule:truthy
jobs:
  linting:
    uses: tohn/gh-workflows/.github/workflows/linting.yml@main
    with:
      config-file: .markdownlintrc
```

## Sources

* <https://stackoverflow.com/q/59757355>
* <https://stackoverflow.com/q/75274644>
* <https://earthly.dev/blog/composite-actions-github/>

[actions]: https://docs.github.com/en/actions/creating-actions/creating-a-composite-action
[workflows]: https://docs.github.com/en/actions/using-workflows/reusing-workflows
