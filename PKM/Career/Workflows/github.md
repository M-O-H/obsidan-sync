
# Branch Strategies
## Trunk-Based Development

```markdown
main (protected — never push here directly)
  ↑
feature/what-you-are-building
fix/what-you-are-fixing
chore/what-you-are-maintaining
```

The rules you enforce on yourself:

Never push directly to main. Always branch, always PR, even alone
Branch names follow a prefix pattern — feature/, fix/, chore/. This is what triggers different CI behavior and generates clean changelogs automatically
PRs must pass CI before you merge. You are both the developer and the reviewer
Delete the branch after merging. Keep the repo clean
## Gitflow

# Ci/CD Pipeline
## Continuous Integration 

My **Quality Gate**: Runs on every push to every branch and every PR. Blocks merging if anything fails.
When it triggers: Always. Every push, every PR, every branch

example config `ci.yml` file
- Quality check (lint, type check, format)
- Test (unit, integration, e2e, smoke tes, etc)
- Build
```
name: CI

on:
  push:
    branches: ['**']
  pull_request:
    branches: [main]

concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true

jobs:
  quality:
    name: Lint & Typecheck
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20', cache: 'npm' }
      - run: npm ci
      - run: npm run lint
      - run: npm run typecheck

  test:
    name: Tests
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20', cache: 'npm' }
      - run: npm ci
      - run: npm test -- --coverage

  build:
    name: Build
    runs-on: ubuntu-latest
    needs: [quality, test]
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20', cache: 'npm' }
      - run: npm ci
      - run: npm run build	
```
## Continuous Delivery

What it does: Deploys frontend to Vercel and backend to Render, but only after code reaches main. Then smoke tests that the deploy actually worked.
When it triggers: Only on merge to main. Never on feature branches.

example config `cd.yml` file
```
name: CD

on:
  push:
    branches: [main]

jobs:
  deploy-frontend:
    name: Deploy Frontend → Vercel
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with: { node-version: '20', cache: 'npm' }
      - run: npm ci
      - run: npm run build
      - name: Trigger Vercel deploy
        run: curl -X POST ${{ secrets.VERCEL_DEPLOY_HOOK }}

  deploy-backend:
    name: Deploy Backend → Render
    runs-on: ubuntu-latest
    steps:
      - name: Trigger Render deploy
        run: curl -X POST ${{ secrets.RENDER_DEPLOY_HOOK }}

  smoke-test:
    name: Smoke Test
    runs-on: ubuntu-latest
    needs: [deploy-frontend, deploy-backend]
    steps:
      - name: Wait for services to be live
        run: sleep 45
      - name: Check frontend
        run: curl -f ${{ secrets.FRONTEND_URL }}
      - name: Check backend health
        run: curl -f ${{ secrets.BACKEND_URL }}/health
```