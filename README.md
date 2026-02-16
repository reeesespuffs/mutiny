<div align="center">
<h1>
  Mutiny
  
  [![Stars](https://img.shields.io/github/stars/reeesespuffs/mutiny?style=flat-square&logoColor=white)](https://github.com/reeesespuffs/mutiny/stargazers)
  [![Forks](https://img.shields.io/github/forks/reeesespuffs/mutiny?style=flat-square&logoColor=white)](https://github.com/reeesespuffs/mutiny/network/members)
  [![License](https://img.shields.io/github/license/reeesespuffs/mutiny?style=flat-square&logoColor=white)](https://github.com/reeesespuffs/mutiny/blob/main/LICENSE)
</h1>
A unofficial Stoat client that adds QoL features like self-hosted support and plugins! <br> Available on <a href="https://mutiny.chat/app/">mutiny.chat/app</a>
</div>
<br/>

## Development Guide
Before contributing, make yourself familiar with the [contribution guidelines](.github/contributing.md), and the [code style guidelines](./GUIDELINES.md)

Before getting started, you'll want to install:

- Git
- Node.js
- pnpm (run `corepack enable`)

Then proceed to setup:

```bash
# clone the repository
git clone --recursive https://github.com/reeesespuffs/mutiny mutiny
cd mutiny

# update submodules if you pull new changes
# git submodule init && git submodule update

# install all packages
pnpm i --frozen-lockfile

# build deps:
pnpm build:deps

# or build a specific dep (e.g. stoat.js updates):
# pnpm --filter stoat.js run build

# customise the .env
cp packages/client/.env.example packages/client/.env

# run dev server
pnpm dev
```

Finally, navigate to http://local.revolt.chat:5173.

### Pulling in Stoat's brand assets

If you want to pull in Stoat brand assets after pulling, run the following:

```bash
# update the assets
git -c submodule."packages/client/assets".update=checkout submodule update --init packages/client/assets
```

You can switch back to the fallback assets by running deinit and continuing as normal:

```bash
# deinit submodule which clears directory
git submodule deinit packages/client/assets
```

## Deployment Guide

### Build the app

```bash
# install packages
pnpm i --frozen-lockfile

# build dependencies
pnpm build:deps

# build for web
pnpm build

# ... when building for Stoat production
pnpm build:prod
```

You can now deploy the directory `packages/client/dist`.

### Routing Information

The app currently needs the following routes:

- `/login`
- `/pwa`
- `/dev`
- `/discover`
- `/settings`
- `/invite`
- `/bot`
- `/friends`
- `/server`
- `/channel`

This corresponds to [Content.tsx#L33](packages/client/src/index.tsx).
