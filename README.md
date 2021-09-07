# gdb-ctest
gdb-ctest - run _ctest_ inside _gdb_, including fixtures and environment

## Dependencies
- jq
- ctest

## Installation
- The script should work by itself - just copy it somewhere to your disk
- There is a PKGBIULD for Arch linux - https://github.com/syyyr/gdb-ctest-aur

## Usage
```
gdb-ctest <test_name>
```

## Options
```
<test_name>  Test to be ran. The same for 'ctest -R <test_name>'
```

## Information/caveats
- Run this in the same directory where you would run _ctest_.
- The script supports the `ENVIRONMENT` property.
- The test must have at most one `FIXTURES_REQUIRED`.
- The fixture must have at most one `FIXTURES_SETUP` and at most one `FIXTURES_CLEANUP`.
- That means that you can run tests that have `ENVIRONMENT`, but no fixtures.
- The script shows exactly what commands will it run for the setup, cleanup, and for the actual test command. It will
  prompt you for confirmation before it runs anything.
- You can use `run` inside _gdb_ repeatedly, if your test doesn't depend on redoing fixtures on every run.
