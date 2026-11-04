[Up]()

# Direnv

`direnv` is an extension for your shell that can load and unload environment variables depending on the current directory.

## Install

Install `direnv`:
```bash
$ pacman -S direnv
```
Add  the following line to the end of your `.bashrc`
```
eval "$(direnv hook bash)"
```
## Direnv and Pixi

Add a `.envrc` to your Pixi workspace root and allow `direnv` to load: 
```Bash
$ cd the_workspace
$ echo 'layout pixi' > .envrc
$ direnv allow

direnv: loading ~/the_workspace/.envrc
direnv: export +CONDA_DEFAULT_ENV +CONDA_PREFIX +CONDA_SHLVL +MODULAR_HOME +PIXI_ENVIRONMENT_NAME +PIXI_ENVIRONMENT_PLATFORMS +PIXI_EXE +PIXI_IN_SHELL +PIXI_PROJECT_MANIFEST +PIXI_PROJECT_NAME +PIXI_PROJECT_ROOT +PIXI_PROJECT_VERSION +PIXI_PROMPT +PIXI_WORKSPACE_MANIFEST +PIXI_WORKSPACE_NAME +PIXI_WORKSPACE_ROOT +PIXI_WORKSPACE_VERSION ~PATH

$ cd ..
direnv: unloading
```
---
**Links**

[direnv](https://direnv.net/)

[Pixi integration with direnv](https://pixi.prefix.dev/latest/integration/third_party/direnv/)
