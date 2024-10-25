# Linting Bug example

Linting via nx:

```shell
nx lint app
```

Linting via npm:

```shell
npm run lint -w @nx-lint-bug/app
```

Both variants should give the same results, but do not:

Output of `nx lint app`:

```shell
▶ nx lint app                     

> nx run app:lint


Linting "app"...

/path/to/nx-lint-bug/packages/app/src/lib/app.ts
  2:23  error  Unable to resolve path to module '@features/feature-a'  import/no-unresolved

✖ 1 problem (1 error, 0 warnings)

✖ 1 problem (1 error, 0 warnings)

```

Output of `npm run lint -w @nx-lint-bug/app`:

```shell
▶ npm run lint -w @nx-lint-bug/app

> @nx-lint-bug/app@0.0.1 lint
> eslint ./src --config .eslintrc.json
```