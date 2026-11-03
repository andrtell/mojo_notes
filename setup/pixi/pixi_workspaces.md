[Up](../pixi.md) | [Previous](install_pixi.md)

# Pixi workspaces

A `pixi` workspace is a set of environments.

Create a new `pixi` workspace:
```bash
$ pixi init my_workspace
```
_or_
```bash
$ mkdir my_workspace; cd my_workspace
$ pixi init
```
_Basic workspace structure_
```
.
├── .gitattributes
├── .gitignore
└── pixi.toml
```
_pixi.toml_
```toml
[workspace]
channels = ["conda-forge"]
name = "my_workspace"
platforms = ["linux-64"]
```
## Channels

A **channel** is a repository of [Conda packages](https://anaconda.org/). 

`pixi` fetches dependencies from one or more channels. 

When creating a new `pixi` workspace, channels can be configured:
```bash
$ pixi init my_workspace -c https://conda.modular.com/max/ -c conda-forge
```
Add a channel to an existing workspace:
```bash
$ pixi workspace channel add https://conda.modular.com/max/
```
_pixi.toml_
```toml
[workspace]
channels = ["https://conda.modular.com/max", "conda-forge"]
```
## Managing dependencies

Add a dependency:
```bash
$ pixi add numpy
```
_pixi.toml_
```toml
[dependencies]
numpy = ">=2.5.4,<3"
```
Remove a dependency:
```bash
$ pixi remove numpy
```
_pixi.toml_
```toml
[dependencies]

```
To add dependencies from [PyPI](https://pypi.org).
```bash
$ pixi add --pypi httpx
```
## Environment

`pixi` always creates an environment for your workspace.

Start a new shell in the environment:
```bash
$ pixi shell
(workspace) $ python -VV
Python 3.15.2 | packaged by conda-forge | (main, Oct 26 2026, 11:39:52) [GCC 15.3.0]
(workspace) $ exit
$
```
Run a command in the environment:
```bash
$ pixi run python -VV
Python 3.15.2 | packaged by conda-forge | (main, Oct 26 2026, 11:39:52) [GCC 15.3.0]
```
---
**Links**

[pixi.prefix.dev/latest/first_workspace/](https://pixi.prefix.dev/latest/first_workspace/)

[pixi.prefix.dev/latest/conda_ecosystem/](https://pixi.prefix.dev/latest/conda_ecosystem/)

[docs.conda.io/en/latest/](https://docs.conda.io/en/latest/)

[anaconda.org/](https://anaconda.org/)
