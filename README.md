## Description

A monorepo setup for k6 tests project and a local library to include
into the tests project with tree-shaking not set up.

## Reproduction steps

- `yarn`
- `cd libs/helpers`
- `yarn build`
- `cd ../../tests`
- `yarn bundle`
- Check `tests\dist\get-200-status-test.js` and search for `Test `. It will
  include both `Test 1` and `Test 2`, even though `Test 2` is not used.
- Expected result - enable tree-shaking if possible so that only relevant parts
  are included into the resulting .js file.
