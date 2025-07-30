# GitHub Actions Automated Testing

This repository includes automated testing using GitHub Actions workflows.

## Workflow

### Unit Tests Workflow (`.github/workflows/unit-test.yml`)
- Runs on push and pull requests to main/master branches
- Uses self-hosted runners with `cuaesd/aesd-autotest:unit-test` container
- Focuses on unit tests for systemcalls implementation
- Avoids complex cross-compilation and QEMU tests that require additional toolchain setup

## Test Coverage

The automated tests cover:
- **systemcalls implementation**: Tests for `do_system()`, `do_exec()`, and `do_exec_redirect()` functions
- **Build verification**: Ensures the project compiles successfully with CMake
- **Unity test framework**: Validates all unit test assertions pass

## Manual Testing

You can also run tests manually:
```bash
# Run unit tests only (recommended for CI)
./unit-test.sh

# Run full test suite (includes assignment tests requiring cross-compilation tools)
./full-test.sh
```

## Status

Unit tests are currently passing for Assignment 3 Part 1 implementation. The workflow focuses on unit tests to avoid dependency issues with cross-compilation toolchains and QEMU emulation required for full assignment testing.