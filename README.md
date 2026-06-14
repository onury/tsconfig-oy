# tsconfig-oy

Shared TypeScript base config.

## Installation

```
$ npm install --save-dev tsconfig-oy
```

## Usage

```jsonc
// tsconfig.json
{
  "extends": "tsconfig-oy",
  "compilerOptions": {
    "outDir": "lib",
    "declarationDir": "lib",
    "rootDir": ".",
    "types": ["node", "vitest/globals"]
  },
  "include": ["src/**/*.ts", "test/**/*.ts"]
}
```

## v2.0.1 — modernization (breaking)

Future-proofed for TypeScript 6/7 and ESM:

- **Removed deprecated options** that error in TS 6 and are removed in TS 7:
  `baseUrl`, `downlevelIteration`, `alwaysStrict`. Consumers no longer need
  `"ignoreDeprecations"`.
- **Added** `isolatedModules` and `verbatimModuleSyntax` (modern single-file
  transpilation + explicit `import type`).
- **Dropped** project-specific bits that don't belong in a shared base:
  `jsx`/`jsxFactory`, `experimentalDecorators`/`emitDecoratorMetadata`,
  `paths` (`@cutepilot/*`), `incremental`, and the `types`/`typeRoots`
  (set these per-project).
- Kept the established strictness convention: `strict: true` with
  `noImplicitAny: false`, `strictBindCallApply: false`, `noUnusedParameters: false`.
- `module`/`moduleResolution` set to `NodeNext` (PascalCase is fine in TS 6).

Projects set `outDir`, `declarationDir`, `rootDir`, `types`, and `include`
themselves.


### Related projects
- [`biome-config-oy`](https://github.com/onury/biome-config-oy)
- [`eslint-config-oy`](https://github.com/onury/eslint-config-oy)
