This is a repository of reusable Github workflows

Currently the following workflows are provided:

# Necessary permissions

See [EnricoMi/publish-unit-test-result-action/#permissions](https://github.com/EnricoMi/publish-unit-test-result-action/?tab=readme-ov-file#permissions)

# gradle-build.yml

Performs checkout, build and test of a Gradle based project.

```yaml
    jobs:
      build-and-test:
        uses: centic9/actions/.github/workflows/gradle-build.yml@3
```

A sample full workflow file is as follows

```yaml
    # This workflow will perform a build of the project and run tests

    name: Build and check

    on:
      push:
        branches: [ master ]
      pull_request:
        branches: [ master ]
      # Allows to run from the Actions tab
      workflow_dispatch:

    jobs:
      build-and-test:
        uses: centic9/actions/.github/workflows/gradle-build.yml@5
```

It can also call `installDist` via the following

```yaml
        uses: centic9/actions/.github/workflows/gradle-build.yml@5
        with:
          isApplication: true
```

If you require a full git-checkout, you can use

```yaml
        uses: centic9/actions/.github/workflows/gradle-build.yml@5
        with:
          fullCheckout: true
```

If additional Ubuntu/Debian packages are required, use the following

```yaml
        uses: centic9/actions/.github/workflows/gradle-build.yml@5
        with:
          addPackage: libfuse2
```

# maven-build.yml

Performs checkout, build and test of a Maven based project.

```yaml
    jobs:
      build-and-test:
        uses: centic9/actions/.github/workflows/gradle-build.yml@3
```

A sample full workflow file is as follows

```yaml
# This workflow will perform a build of the project and run tests

name: Build and check

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]
  # Allows to run from the Actions tab
  workflow_dispatch:

jobs:
  build-and-test:
    uses: centic9/actions/.github/workflows/maven-build.yml@5
```

If you require a full git-checkout, you can use

```yaml
        uses: centic9/actions/.github/workflows/maven-build.yml@5
        with:
          fullCheckout: true
```

If additional Ubuntu/Debian packages are required, use the following

```yaml
        uses: centic9/actions/.github/workflows/maven-build.yml@5
        with:
          addPackage: libfuse2
```

# License

These scripts are licensed under the [BSD 2-Clause License].

[BSD 2-Clause License]: https://www.opensource.org/licenses/bsd-license.php
