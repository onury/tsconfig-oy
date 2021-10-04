## `tsconfig-oy`

Shared [TypeScript config](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) for my projects.

This module embraces:
- ESM
- Node v12+
- ES2019, ES2020


### Installation

```
$ npm install --save-dev tsconfig-oy
```

### Usage

`tsconfig.json`

```jsonc
{
    "extends": "tsconfig-oy",
    "compilerOptions": {
        "baseUrl": ".",
        "declarationDir": "lib",
        "outDir": "lib",
        // ...
    },
    // ...
}
```

When you are targeting a higher version of Node.js, check the relevant ECMAScript version and add it as `target`:

```jsonc
{
    "extends": "tsconfig-oy",
    "compilerOptions": {
        "target": "ES2021",
        // ...
    },
    // ...
}
```

### Related projects
- [`eslint-config-oy`](https://github.com/onury/eslint-config-oy) *(Use this instead of `tslint`.)*
