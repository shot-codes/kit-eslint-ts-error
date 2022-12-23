# Reproduction of ESLint issues in typescript files

```bash
pnpm create svelte@latest app
```

```
✔ Which Svelte app template? › Skeleton project
✔ Add type checking with TypeScript? › Yes, using TypeScript syntax
✔ Add ESLint for code linting? … No / Yes
✔ Add Prettier for code formatting? … No / Yes
✔ Add Playwright for browser testing? … No / Yes
✔ Add Vitest for unit testing? … No / Yes
```

```bash
cd app
pnpm i
echo "import { foo } from 'bar';" > src/routes/+server.ts
```

So, `/routes/+server.ts`, contains an erroneous import `import { foo } from 'bar';`. Running the app with `pnpm run dev` understandably reveals the error. However, running `pnpm run lint` only warns of the unused import, and does not throw any error.
