# tsc-paths
Replace absolute paths to relative paths after typescript compilation (tsc) during compile-time.

[![npm version](https://badge.fury.io/js/tsc-paths.svg)](https://badge.fury.io/js/tsc-paths)


## Getting Started
First, install tsc-paths as devDependency using npm or yarn.

```sh
npm i -D tsc-paths
# or
yarn add -D tsc-paths
```

## Add it to your build scripts in package.json
```json
"scripts": {
  "build": "tsc --project tsconfig.json && tsc-paths -p tsconfig.json -s ./src -o ./out",
}
```

### Options
| flag         | description                                        |
| ------------ | -------------------------------------------------- |
| -p --project | project configuration file (tsconfig.json)         |
| -s --src     | source code root directory                         |
| -o --out     | output directory of transpiled code (tsc --outDir) |

You need to provide -s (--src) and -o (--out), because it's hard to predict source and output paths based on tsconfig.json.

I've tried a little and failed. :(

`tsc` does some magic to determine source and output paths and I haven't dived too deep to mimic it.

For now, it's simpler to provide the paths manually.

If you know how, Pull Requests are welcome!
