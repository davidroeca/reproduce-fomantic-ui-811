# Reproducing Fomantic-UI issue 811

The following repository aims to reproduce [Fomantic UI #811](https://github.com/fomantic/Fomantic-UI/issues/811).

To reproduce the issue, simply run `yarn install --frozen-lockfile`. The same issue happens when running this command both in the root of this repo, and in [packages/reproduction](./packages/reproduction).

## Tested tool versions

```shell
❯ yarn --version
1.22.4
❯ node --version
v14.4.0
```

Also tested with

```shell
❯ node --version
v12.18.1
```

## Expected behavior

Successfully install dependencies. The `gulp install` doesn't need to execute, because it already ran successfully previously.

## Actual behavoir

```shell
❯ yarn install --frozen-lockfile
yarn install v1.22.4
[1/4] Resolving packages...
[2/4] Fetching packages...
info fsevents@1.2.13: The platform "linux" is incompatible with this module.
info "fsevents@1.2.13" is an optional dependency and failed compatibility check. Excluding it from installation.
[3/4] Linking dependencies...
[4/4] Building fresh packages...
error /home/david/src/reproduction/node_modules/fomantic-ui: Command failed.
Exit code: 130
Command: gulp install
Arguments:
Directory: /home/david/src/reproduction/node_modules/fomantic-ui
Output:
[23:04:56] Using gulpfile ~/src/reproduction/node_modules/fomantic-ui/gulpfile.js
[23:04:56] Starting 'install'...
[23:04:56] Starting 'run setup'...
? Set-up Semantic UI (Use arrow keys)
❯ Automatic (Use default locations and all components)
  Express (Set components and output folder)
  Custom (Customize all src/dist values) [23:04:56] The following tasks did not complete: install, run setup
[23:04:56] Did you forget to signal async completion?
info Visit https://yarnpkg.com/en/docs/cli/install for documentation about this command.
```
