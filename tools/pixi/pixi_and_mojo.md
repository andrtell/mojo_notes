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
---
**Links**

[Mojo](https://mojolang.org/)