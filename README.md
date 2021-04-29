# gdb-ctest
Run ctest in gdb with fixtures and environment.

## Dependencies
- jq

```
gdb-ctest - runs a ctest inside gdb, including fixtures and environment

Usage: gdb-ctest <test_name>

Options:
    <test_name>  Test to be ran. The same for 'ctest -R <test_name>'

Information:
    - Run this in the same directory where you would run ctest.
    - The test must have at most one FIXTURES_REQUIRED.
    - The fixture must have at most one FIXTURES_SETUP and at most one FIXTURES_CLEANUP.
    - That means that you can run tests that have ENVIRONMENT but no fixtures.
    - You can run gdb repeatedly, if your test doesn't depend on redoing you fixtures on every run.
```
