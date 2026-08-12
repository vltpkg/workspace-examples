# workspace-examples

Two workspace publishing examples: `pnpm-workspace/` and `npm-workspace/`. Each has 2 packages (`utils`, `cli`).

## Structure

- **pnpm-workspace/** — Uses `pnpm-workspace.yaml`
- **npm-workspace/** — Uses `workspaces` in `package.json`

Both use `packages/{utils,cli}/` with matching structure. Config files: `.npmrc` at workspace root.

## Key Points

- All packages use `@YOUR-ACCOUNT` placeholder (replace with account slug)
- Registry: `https://registry.vlt.io/YOUR-ACCOUNT/main/`
- Each package has independent version (no monorepo-wide versioning)
- No auth tokens stored (users configure via login/env)

## Commands

```bash
# pnpm-workspace
pnpm install
pnpm build
pnpm -r publish              # Publish all
cd packages/utils && pnpm publish  # Publish one

# npm-workspace
npm install
npm run build
npm publish --workspaces     # Publish all
cd packages/utils && npm publish   # Publish one
```
