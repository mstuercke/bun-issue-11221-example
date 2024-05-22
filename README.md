# Example for Bun issue 11221

https://github.com/oven-sh/bun/issues/11221

## Steps to reproduce

1. Install a bun version >= 1.0.31 (previous versions are working fine)
2. Run `bun install`
3. Open the project in IntelliJ
4. Use bun as node interpreter and package manager (`Settings` -> `Language & Frameworks` -> `Node.js`)
5. Enable automatic ESLint configuration (`Settings` -> `Language & Frameworks` -> `Code Quality Tools` -> `ESLint`)
6. Open the `index.ts` file

## Expected Behaviour

The `foo` variable is marked by ESLint with an error (`ESLint: 'foo' is assigned a value but never used.(@typescript-eslint/no-unused-vars)`)

## Actual behaviour

- On the bottom of IntelliJ you can see a background task "Starting ESLint Service" that timeouts after ~1min.
- The `foo` variable is not marked by ESLint as an error
- At the top of the file, the following error message is shown: `ESLint: No results for index.ts after 20 seconds`
