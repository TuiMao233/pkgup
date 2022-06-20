# ptsup

[![npm version](https://badgen.net/npm/v/ptsup)](https://npm.im/ptsup) [![npm downloads](https://badgen.net/npm/dm/ptsup)](https://npm.im/ptsup)

[tsup](https://github.com/egoist/tsup) is similar but focuses more on packet processing, powered by [esbuild](https://github.com/evanw/esbuild).


## what's the difference?

- A more casual package directory
- carry meta options
- carry assets options(.png, .html,...more)

## carry meta

use command `--meta` It works well on some monorepo (pnpm,yarn,npm) applications

- carry package info (`LICENSE`, `README.md`, `CHANGELOG.md`)
- handle `package.publishConfig` and carry package.json
- create `node_modules` lnk file to output

## Using custom configuration

Like tsup, you can use the config file to configure

Supported file formats

- `ptsup.config.ts`
- `ptsup.config.js`
- `ptsup.config.cjs`
- `ptsup.config.json`

### TypeScript / JavaScript

```ts
import { defineConfig } from 'ptsup'

export default defineConfig({
  entry: ['src/index.ts'],
  splitting: false,
  sourcemap: true,
  clean: true,
})
```
## Available command line options

```sh
Usage:
  $ ptsup [...files]

Commands:
  [...files]  Bundle files

For more info, run any command with the `--help` flag:
  $ ptsup --help

Options:
  --entry <directory|file>   Use a key-value pair as entry directory|files (default: ./)
  -r, --root <dir>           Root directory (default: .)
  -o, --outdir <outdir>      Output directory (default: dist)
  -f, --format <format>      Bundle format, "cjs", "iife", "esm" (default: cjs)
  --sourcemap [inline]       Generate external sourcemap, or inline source: --sourcemap inline
  --minify                   Minify bundles only for iife
  --target <target>          Bundle target, "es20XX" or "esnext" (default: esnext)
  --dts [entry]              Generate declaration file
  --dts-only                 Emit declaration files only
  --global-name <name>       Global variable name for iife format (default: package.name in pascal-case)
  --clean                    Clean output directory
  --meta                     helper and carry package.json/*.md
  --assets [files]           carry some static resources
  --jsxFactory <jsxFactory>  Name of JSX factory function (default: React.createElement)
  --platform <node|browser>  platform determines the format of the output (default: node)
                             platform->node:    cjs,esm
                             platform->browser: cjs,esm,iife
  -h, --help                 Display this message
```


## License

MIT &copy; [EGOIST](https://github.com/sponsors/egoist)