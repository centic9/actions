This is a repository of reusable Github workflows

Currently the following workflows are provided:

# gradle-build.yml

Performs checkout, build and test of a Gradle based project.

    jobs:
      build-and-test:
        uses: centic9/actions/.github/workflows/gradle-build.yml@3

A sample full workflow file is as follows

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
        uses: centic9/actions/.github/workflows/gradle-build.yml@3

It can also call `installDist` via the following

        uses: centic9/actions/.github/workflows/gradle-build.yml@3
        with:
          isApplication: true

If you require a full git-checkout, you can use

        uses: centic9/actions/.github/workflows/gradle-build.yml@3
        with:
          fullCheckout: true

# License

These scripts are licensed under the [BSD 2-Clause License].

[BSD 2-Clause License]: https://www.opensource.org/licenses/bsd-license.php
