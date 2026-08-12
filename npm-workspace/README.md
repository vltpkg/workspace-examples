# npm-workspace-example

Example npm monorepo with multiple publishable packages.

## Packages

- `@YOUR-ACCOUNT/utils` — Utility functions
- `@YOUR-ACCOUNT/cli` — CLI tools

## Setup

1. Update `@YOUR-ACCOUNT` in `.npmrc` and all `package.json` files with your account slug
2. Configure authentication:
   ```bash
   npm login --registry=https://registry.vlt.io/YOUR-ACCOUNT/main/ --scope=@YOUR-ACCOUNT
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Build packages:
   ```bash
   npm run build
   ```

## Publishing

To publish all packages:
```bash
npm publish --workspaces
```

To publish a specific package:
```bash
cd packages/utils
npm publish
```

See the [vlt publishing guide](/guides/publish-packages-from-workspace) for more details.
