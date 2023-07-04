# gdb-ctest
gdb-ctest - run _ctest_ inside _gdb_, including fixtures and environment

## Dependencies
- ctest
- gdb
- jq

## Installation
- The script should work by itself - just copy it somewhere to your disk
- There is a PKGBUILD for Arch Linux - https://aur.archlinux.org/packages/gdb-ctest-git

## Usage
```
gdb-ctest <test_name>
```

## Options
```
<test_name>  Test to be ran. The same for 'ctest -R <test_name>'. Specifying more than one test is an error.
-h,--help    Shows help."
-X           Other arguments starting with a single dash are ignored.
--XXX        Other arguments starting with a double dash are ignored.
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
