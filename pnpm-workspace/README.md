# pnpm-workspace-example

Example pnpm monorepo with multiple publishable packages.

## Packages

- `@YOUR-ACCOUNT/utils` — Utility functions
- `@YOUR-ACCOUNT/cli` — CLI tools

## Setup

1. Update `@YOUR-ACCOUNT` in `.npmrc` and all `package.json` files with your account slug
2. Configure authentication:
   ```bash
   pnpm login --registry=https://registry.vlt.io/YOUR-ACCOUNT/main/ --scope=@YOUR-ACCOUNT
   ```
3. Install dependencies:
   ```bash
   pnpm install
   ```
4. Build packages:
   ```bash
   pnpm build
   ```

## Publishing

To publish all packages:
```bash
pnpm -r publish
```

To publish a specific package:
```bash
cd packages/utils
pnpm publish
```

See the [vlt publishing guide](/guides/publish-packages-from-workspace) for more details.
