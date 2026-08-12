# workspace-examples

Workspace publishing examples — demonstrates publishing multiple packages from monorepos using pnpm and npm workspaces.

## Structure

Two separate workspace examples, each showing how to organize and publish multiple packages:

### pnpm-workspace/

Uses `pnpm-workspace.yaml` to define workspace packages:

```
packages/
├── utils/      (@YOUR-ACCOUNT/utils)
└── cli/        (@YOUR-ACCOUNT/cli)
```

Configuration:
- `pnpm-workspace.yaml` — Workspace definition
- `.npmrc` — Scoped registry for `@YOUR-ACCOUNT`
- Each package has its own `package.json`, `tsconfig.json`, `index.ts`

Publishing:
```bash
pnpm install
pnpm build
pnpm -r publish
```

### npm-workspace/

Uses `workspaces` field in root `package.json` to define workspace packages:

```
packages/
├── utils/      (@YOUR-ACCOUNT/utils)
└── cli/        (@YOUR-ACCOUNT/cli)
```

Configuration:
- Root `package.json` with `workspaces` array
- `.npmrc` — Scoped registry for `@YOUR-ACCOUNT`
- Each package has its own `package.json`, `tsconfig.json`, `index.ts`

Publishing:
```bash
npm install
npm run build
npm publish --workspaces
```

## Usage

Each workspace example serves as a template for the [publishing packages from workspaces guide](https://docs.vlt.io/guides/publish-packages-from-workspace/). Users:

1. Clone the appropriate workspace example (pnpm or npm)
2. Replace `YOUR-ACCOUNT` with their vlt account slug in:
   - All `package.json` files (name fields)
   - `.npmrc` file
3. Update package versions as needed
4. Configure authentication
5. Follow the publishing guide for their workspace tool

## Key Differences

| Aspect | pnpm | npm |
|--------|------|-----|
| Workspace config | `pnpm-workspace.yaml` | `workspaces` in package.json |
| Install | `pnpm install` | `npm install` |
| Build all | `pnpm build` | `npm run build` |
| Publish all | `pnpm -r publish` | `npm publish --workspaces` |
| Publish one | `cd packages/utils && pnpm publish` | `cd packages/utils && npm publish` |

## Development Notes

- Both examples use the same package structure (utils + cli) for consistency
- Each package is independent and can be published separately
- Version management per package (not monorepo-wide versioning)
- `@YOUR-ACCOUNT` scope must match the account publishing packages
- No auth tokens stored in examples (users configure via login or environment)
