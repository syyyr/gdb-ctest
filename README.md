# gdb-ctest
gdb-ctest - run _ctest_ inside gdb, including fixtures and environment

## Dependencies
- jq
- ctest

## Usage
```
gdb-ctest <test_name>
```

## Options
```
<test_name>  Test to be ran. The same for 'ctest -R <test_name>'
```

## Information/caveats
- Run this in the same directory where you would run ctest.
- The test must have at most one `FIXTURES_REQUIRED`.
- The fixture must have at most one `FIXTURES_SETUP` and at most one `FIXTURES_CLEANUP`.
- That means that you can run tests that have `ENVIRONMENT` but no fixtures.
- You can run gdb repeatedly (before ending it), if your test doesn't depend on redoing fixtures on every run.
