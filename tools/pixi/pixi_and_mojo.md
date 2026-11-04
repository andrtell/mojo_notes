[Up](../pixi.md) | [Prev](pixi_workspaces.md)

# Pixi and Mojo

We can use `pixi` to manage `mojo`.

Create a new `mojo` project:
```bash
$ pixi init hello-world \
  -c https://conda.modular.com/max/ -c conda-forge
  
$ cd hello-world

$ pixi add mojo
```
Write some mojo code:
```python
# hello.mojo

def main():
    print("hello world")
```
Start a new shell:
```bash
$ pixi shell
```
Compile and run:
```bash
(hello-world) $ mojo hello.mojo
hello world
```
## Configure Pixi

It can be convenient to add the Mojo channel to the list of default channels for new `pixi` workspaces.

Update `~/.config/pixi/config.tml` to add the Mojo channel to the default `pixi` channels:
```toml
default-channels = ["conda-forge", "https://conda.modular.com/max/"]
```
When creating a new `mojo` project you can now skip the `-c` flag.
```Bash
$ pixi init hello-world
$ cd hello-world
$ pixi add mojo
```
---
**Links**

[Mojo page](https://mojolang.org/)

[Pixi configuration](https://pixi.prefix.dev/latest/reference/pixi_configuration/)
