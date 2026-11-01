[Up](../uv.md)

# Mojo and uv

Use `uv init` to start a new mojo project.
```bash
$ uv init hello-world
$ cd hello-world
$ uv add mojo
```
_hello.mojo_
```python
def main():
    print("hello world")
```
Use `uv run mojo <file>` to execute _hello.mojo_.
```bash
$ uv run mojo hello.mojo
hello world
```
Or activate _the environment_
```bash
$ uv sync
$ source .venv/bin/activate
(hello-world) $ mojo hello.mojo
```
**See**

[Python projects](python_and_uv/python_projects.md)

**Links**

[mojolang.org/docs/manual/quickstart/](https://mojolang.org/docs/manual/quickstart/)







