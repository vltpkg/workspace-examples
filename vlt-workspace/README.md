# vlt-workspace-example

Example vlt monorepo with multiple publishable packages.

## Packages

- `@YOUR-ACCOUNT/utils` — Utility functions
- `@YOUR-ACCOUNT/greeting` — Greeting utilities

## Setup

1. Update `@YOUR-ACCOUNT` in `vlt.json` and all `package.json` files with your account slug
2. Configure authentication:
   ```bash
   vlt login --registry=https://registry.vlt.io/YOUR-ACCOUNT/main/
   ```
3. Install dependencies:
   ```bash
   vlt install
   ```
4. Build packages:
   ```bash
   vlt build
   ```

## Publishing

To publish all packages:
```bash
vlt publish --recursive
```

To publish a specific package:
```bash
cd packages/greeting
vlt publish
```

See the [vlt publishing guide](/guides/publish-packages-from-workspace) for more details.
