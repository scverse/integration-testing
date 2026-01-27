# scverse-integration-testing

This repository contains integration tests for the [scverse](https://github.com/scverse) core packages.
We currently do not accept ecosystem packages but may change our mind in the future.

## Overview

The integration tests are run automatically via GitHub Actions on a daily schedule, as well as on pushes and pull requests to the `main` branch. The workflow installs each package, applies constraints, and runs the test suite to detect breaking changes early.

## Tested Packages

The following packages are tested:
- mudata
- spatialdata
- scirpy
- muon
- scanpy
- squidpy
- scvi-tools
- pertpy
- decoupler
- SnapATAC2

## How it Works

- Each package is checked out and tested in isolation.
- AnnData (from the main branch) is installed with test dependencies.
- Constraints from [`constraints.txt`](constraints.txt) are applied to avoid known incompatibilities.
- Failures are reported automatically, and issues are opened if the daily scheduled run fails.

See the workflow file at [`.github/workflows/integration-test.yml`](.github/workflows/integration-test.yml) for details.

## License

This project is licensed under the [MIT License](LICENSE).
