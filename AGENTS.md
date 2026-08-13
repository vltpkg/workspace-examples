# workspace-examples

Three workspace publishing examples: `vlt-workspace/`, `pnpm-workspace/`, and `npm-workspace/`. Each has 2 packages (`utils`, `greeting`).

## Structure

- **vlt-workspace/** — Uses `vlt.json`
- **pnpm-workspace/** — Uses `pnpm-workspace.yaml`
- **npm-workspace/** — Uses `workspaces` in `package.json`

All use `packages/{utils,greeting}/` with matching structure.

## Key Points

- All packages use `@YOUR-ACCOUNT` placeholder (replace with account slug)
- Registry: `https://registry.vlt.io/YOUR-ACCOUNT/main/`
- Each package has independent version (no monorepo-wide versioning)
- No auth tokens stored (users configure via login/env)

## Commands

```bash
# vlt-workspace
vlt install
vlt build
vlt publish --recursive      # Publish all
cd packages/utils && vlt publish   # Publish one

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
