# yarn_workspaces_upgrade_example
A small example repo showing `yarn upgrade` not behaving as expected.


```
➜  yarn_upgrade_example git:(master) yarn outdated
yarn outdated v1.19.1
info Color legend :
 "<red>"    : Major Update backward-incompatible updates
 "<yellow>" : Minor Update backward-compatible features
 "<green>"  : Patch Update backward-compatible bug fixes
Package Current Wanted Latest Workspace Package Type URL
webpack 4.29.3  4.41.2 4.41.2 package-1 dependencies https://github.com/webpack/webpack
✨  Done in 0.46s.
```

Notice we want the latest..

```
➜  yarn_upgrade_example git:(master) yarn upgrade webpack --force
yarn upgrade v1.19.1
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Rebuilding all packages...
success Saved lockfile.
success Saved 0 new dependencies.
✨  Done in 1.07s.
```

Running upgrade in root does nothing.

```
➜  package-1 git:(master) yarn upgrade webpack --force
yarn upgrade v1.19.1
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Rebuilding all packages...
success Saved lockfile.
success Saved 0 new dependencies.
✨  Done in 1.09s.
```

Running upgrade in `package-1` does nothing.
