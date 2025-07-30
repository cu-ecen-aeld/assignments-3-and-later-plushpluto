# GitHub Actions Automated Testing

This repository includes automated testing using GitHub Actions workflows.

## Workflows

### CI Workflow (`.github/workflows/ci.yml`)
- Runs on push and pull requests to main/master branches
- Uses Ubuntu latest environment
- Installs build dependencies (cmake, gcc, g++)
- Builds the project using CMake
- Runs unit tests and full test suite

### Unit Test Workflow (`.github/workflows/unit-test.yml`)
- Runs on push and pull requests to main/master branches
- Includes two jobs:
  1. **unit-test**: Uses the `cuaesd/aesd-autotest:unit-test` container for consistent testing environment
  2. **build-test**: Uses Ubuntu latest with manual dependency installation

Both workflows ensure that:
- All unit tests pass (`./unit-test.sh`)
- Full test suite passes (`./full-test.sh`)
- Assignment-specific tests run (if configured in `conf/assignment.txt`)

## Test Coverage

The automated tests cover:
- **systemcalls implementation**: Tests for `do_system()`, `do_exec()`, and `do_exec_redirect()` functions
- **Build verification**: Ensures the project compiles successfully
- **Assignment validation**: Runs assignment-specific tests based on configuration

## Manual Testing

You can also run tests manually:
```bash
# Run unit tests only
./unit-test.sh

# Run full test suite (includes unit tests + assignment tests)
./full-test.sh
```

## Status

All tests are currently passing for Assignment 3 Part 1 implementation.