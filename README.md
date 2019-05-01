# deno-starter

https://github.com/denoland/deno

## bash Settings

`.bash_profile`

```bash
# Deno
export DENO_DIR=$HOME/.deno
export PATH=$DENO_DIR/bin:$PATH
```

## VS Code Settings

https://github.com/justjavac/vscode-deno

This extension remove error `An import path cannot end with a '.ts' extension. Consider importing 'https://denopkg.com/xxx/xxx/xxx' instead.`

Set to Disable by default as it affects other projects.

- Disabled > Default
- Enabled > Only deno project

`.vscode/settings/json`

```json
{
  "deno.enable": true
}
```

## Create deno.d.ts

```
$ deno types > ~/.deno/deno.d.ts
```

## tsconfig.json

`baseUrl` writes the relative path of the project.

```
{
  "compilerOptions": {
    "lib": ["es6", "es2018", "dom", "esnext.asynciterable"],
    "target": "es6",
    "module": "commonjs",
    "baseUrl": "../../.deno",
    "paths": {
      "deno": ["deno.d.ts"],
      "http://*": ["deps/http/*"],
      "https://*": ["deps/https/*"],
      "*.ts": ["./*"]
    }
  }
}
```

## Command

```bash
$ deno src/index.ts
```

## about deno 2019/5/1

- It can not use TypeScript Decorators
