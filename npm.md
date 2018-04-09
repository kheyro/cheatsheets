# NPM Cheat Sheet

Last updated: 04/09/2018

### Commands

| Command                                   | Description                                                           |
| ---                                       | ---                                                                   |
| `npm init`                                | Generate package.json                                                 |
| `npm config set init-author-name "Your name"`<br/>`npm config set init-author-email "your@email.com"`<br/>`npm config set init-license MIT`                                | To set default values for `npm init`                                                |
| `npm config ls -l`                        | List all npm configuration flags                                      |
| `npm docs <module-name>`                  | Display documentation of a given library                              |
| `npm install <module-name> --save`        | Install package, update package.json                                  |
| `npm install <module-name> --save-dev`    | Install package, update package.json into devDependencies section     |
| `npm uninstall <module_name>`             | Uninstall package                                                     |
| `npm edit <module_name>`                  | Locally edit dependency                                               |
| `npm config set editor "sublime"`         | Setup editor for `npm edit`                                           |
| `npm test`                                | Run test suite, package.json: `"scripts" : {"test" : "node ..."}`     |                                           |
| `npm outdated`                            | List outdated libraries     |                                           |

## Also see
* https://www.npmjs.com/package/npm-check - better `npm outdated`