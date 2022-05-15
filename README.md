# nx-redwoodjs

Example of a monorepo with multiple [Redwood](https://github.com/redwoodjs/redwood) projects managed by [nx](https://github.com/nrwl/nx).

## Steps to reproduce

### Create nx workspace

``` bash
npx create-nx-workspace@latest --pm yarn --preset core nx-redwoodjs
```

### Create redwood projects

``` bash
cd packages
yarn create redwood-app project-one --no-yarn-install
yarn create redwood-app project-two --no-yarn-install
```

- Rename the `name` property within the `package.json` in `web` and `api` modules within the respective redwood apps to something unique
- Rename the `name` property within the `packages.json` in `project-one` and `project-two` to something unique
- Move/migrate .yarn, .vscode, .editorconfig, .nvmrc and .yarnrc.yml to the top level folder
- Add a custom webpack config
- Customize the ports within one of the `redwood.toml` files to unique non reserved ports
- Run `yarn install` in the top-level folder

### Run both redwood project

``` bash
yarn nx run-many --target=dev --all
```
