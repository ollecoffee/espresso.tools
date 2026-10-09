# espresso.tools

[My espresso setup and wishlist](https://espresso.tools): what I use, what I
want next, and the beans I am drinking. Built with
[Astro](https://astro.build), Tailwind and daisyUI, and deployed to GitHub
Pages.

## Development

```sh
pnpm install   # CI installs with --frozen-lockfile
pnpm dev       # localhost:4321
pnpm build
```

## Structure

It is one page, `src/pages/index.astro`. Site title and links live in
`src/data/config.json`.

Part of [olle.coffee](https://olle.coffee), alongside
[pour.coffee](https://pour.coffee).

## Why there is a pnpm-workspace.yaml

This is not a workspace. pnpm blocks dependency build scripts by default, and
the Astro build fails unless esbuild is allowed to run its postinstall, which
links its platform binary. pnpm 11 moved that setting out of `package.json`, so
`allowBuilds` has to live in this file.
