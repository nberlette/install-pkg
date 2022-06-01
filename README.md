# 🚧 `@brlt/install`

[![NPM version](https://img.shields.io/npm/v/@brlt/install?color=a1b858&label=)](https://www.npmjs.com/package/@brlt/install)

## Features

- [x] Installs [**npm packages**](https://npmjs.com) programmatically with an async API.
- [x] Installs appropriate `@types/*` packages from [**DefinitelyTyped**](https://github.com/DefinitelyTyped), if they exist.
- [x] Determines package manager (`npm`, `yarn`, `pnpm`) with two different strategies:
 -  **preferred**: `packageManager` in `package.json` — e.g. `pnpm@7.1.7` or `yarn@1.22.17`
 -  **fallback**:   lockfile name - `package-lock.json`, `yarn.lock`, or `pnpm-lock.yaml`

> **Note**: if using `yarn` or `pnpm`, it is **strongly** recommended to use `packageManager` in your projects.

<br>

## Install

```bash
pnpm add @brlt/install
```

```bash
yarn add @brlt/install
```

```bash
npm i --save @brlt/install
```

<br>

## Usage

```ts
import install from '@brlt/install'
```

```ts
await install('vite', { silent: true, dev: true })
// "vite@latest", "@types/vite@latest" -> "devDependencies"
```

```ts
await install('pnpm@6.32.6', { types: false, dev: true })
// "pnpm@6.32.6" -> "devDependencies"
```

```ts
await install('next@12.1.0')
// "next@12.1.0" -> "dependencies"
// "@types/next@^12.1.0" -> "devDependencies"
```

<br>

### License and Prior Art

[MIT](https://mit-license.org, "MIT License © 2022 Nicholas Berlette and Anthony Fu") © 2022 [Nicholas Berlette](https://github.com/nberlette) and [Anthony Fu](https://github.com/antfu). Based on the [`install-pkg`](https://github.com/antfu/install-pkg) project.
