npm creates a dependency on the current package with version `file:` when installing via prefixed npm script.

# Reproduction Steps

- Run `npm install`
  - Note 0 changed files.
- Run `npm run custom-install`
  - Note 0 changed files.
- Run `npm run --prefix="." custom-install`
  - Note the added dependency on itself `"my-unique-package": "file:"` and the updated `package-lock.json`.

In projects with more dependencies, the `package-lock.json` size gets increased by ~50%.
