# Knip reproduction

This is a small svelte kit project to reproduce an issue with dymanic imports in Knip.

Knip version: ^5.66.4

## Issue description

I've created an `Error.svelte` component that is lazy loaded in the `src/routes/+page.svelte` component:

```svelte
{#await import("./Error.svelte") then Err}
  <Err.default />
{/await}
```

When running `npm run knip` it says that `Error.svelte` is an unused file.

## Steps to reproduce

1. Clode this repo
1. Install dependencies (`npm install`)
1. Run `npm run knip`
