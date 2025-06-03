npm creates a dependency on the current package with version `file:` when installing via prefixed npm script.

# Reproduction Steps

- Run `npm install`
  - Note 0 changed files.
- Run `npm run custom-install`
  - Note 0 changed files.
- Run `npm run --prefix="." custom-install`
  - Note:
	  - `"my-unique-package": "file:"` added to `package.json`
		- Changes to `package-lock.json`
		- `my-unique-package` installed in `node_modules`
