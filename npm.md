# NPM Cheat Sheet


### Commands

| Command                                   | Description                                                           |
| ---                                       | ---                                                                   |
| `npm init`                                | Generate package.json (-y skip setup)                                 |
| `npm config set init-author-name "Your name"`<br/>`npm config set init-author-email "your@email.com"`<br/>`npm config set init-license MIT`                                | To set default values for `npm init`                                                |
| `npm config ls -l`                        | List all npm configuration flags                                      |
| `npm docs <module-name>`                  | Display documentation of a given library                              |
| `npm install <module-name> --save`        | Install package, update package.json                                  |
| `npm install <module-name> --save-dev`    | Install package, update package.json into devDependencies section     |
| `npm uninstall <module_name>`             | Uninstall package                                                     |
| `npm edit <module_name>`                  | Locally edit dependency                                               |
| `npm config set editor "sublime"`         | Setup editor for `npm edit`                                           |
| `npm test`                                | Run test suite, package.json: `"scripts" : {"test" : "node ..."}`     |
| `npm outdated`                            | List outdated libraries in current project                            |
| `npm outdated -g --depth 0`               | List outdated global packages                                         |
| `npm list -g --depth 0`                   | List of globally installed packages (--depth 0, don't show dependencies)      |
| `npm update <module-name>`                | Upgrade all packages or single package if <module-name> in current project    |
| `npm update -g <module-name>`             | Upgrade all global packages or single package if <module-name>        |
| `npm info <module-name>`                  | List extensive info of given <module-name>                            |
| `npm info <module-name> peerDependencies` | List <module-name> peer dependencies                                  |
| `npm info <module-name> dependencies`     | List <module-name> dependencies                                       |


### Install modules specific peer dependencies

Install specific version of peerdependencies for a module.

```shell
(
  export PKG=<module-name>;
  npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
)
```

Can also use the module `install-peerdeps`, see [here](https://www.npmjs.com/package/install-peerdeps)

```shell
npm install -g install-peerdeps
cd my-project-directory
install-peerdeps <option> <package>[@<version>]
```

Or use `npx install-peerdeps <option> <module-name>`, ie. `npx install-peerdeps --dev eslint-config-airbnb`


### NPM Check Updates

[npm-check-updates](https://www.npmjs.com/package/npm-check-updates) is a command-line tool that allows you to upgrade your package.json or bower.json dependencies to the latest versions, regardless of existing version constraints.

| Command                                   | Description                                      |
| ---                                       | ---                                              |
| `npm install -g npm-check-updates`        | Install globally                                 |
| `ncu`                                     | Check for updates in the current project folder  |
| `ncu -g`                                  | Check global packages                            |
| `ncu -u`                                  | Upgrade all packages                             |
| `ncu <name>`                              | Shorthand for ncu -f mocha (or --filter), include only package names matching the given string, comma-delimited list, or regex   |


## Also see
* https://www.npmjs.com/package/npm-check - better `npm outdated`