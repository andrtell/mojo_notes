[Up](../pixi.md) | [Prev](install_pixi.md) | [Next](pixi_and_mojo.md)

# Pixi workspaces

A `pixi` workspace is a set of environments.

Create a new `pixi` workspace:
```bash
$ pixi init the_workspace
```
_or_
```bash
$ mkdir the_workspace; cd the_workspace
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
name = "the_workspace"
platforms = ["linux-64"]
```
## Channels

A **channel** is a repository of [Conda packages](https://anaconda.org/). 

`pixi` fetches dependencies from one or more channels. 

When creating a new `pixi` workspace, channels can be configured:
```bash
$ pixi init the_workspace -c https://conda.modular.com/max/ -c conda-forge
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
Add a dependency from [PyPI](https://pypi.org).
```bash
$ pixi add --pypi httpx
```
## Environments

`pixi` always creates an environment for your workspace.

Start a new shell in the environment:
```bash
$ pixi shell

(the_workspace) $ python -VV
Python 3.15.2 | packaged by conda-forge | (main, Oct 26 2026, 11:39:52) [GCC 15.3.0]
```
Run a command in the environment:
```bash
$ pixi run python -VV
Python 3.15.2 | packaged by conda-forge | (main, Oct 26 2026, 11:39:52) [GCC 15.3.0]
```
---
**Links**

[Pixi](https://pixi.prefix.dev/)

[Conda](https://docs.conda.io/en/latest/)

[Anaconda (package search engine)](https://anaconda.org/)
