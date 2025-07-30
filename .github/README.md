# GitHub Actions Automated Testing

This repository includes automated testing using GitHub Actions workflows.

## Workflow

### Assignment Tests Workflow (`.github/workflows/unit-test.yml`)
- Runs on push and pull requests to main/master branches
- Uses self-hosted runners with `cuaesd/aesd-autotest:unit-test` container
- Single job that runs both unit tests and full test suite
- Eliminates duplication by consolidating all testing into one workflow

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