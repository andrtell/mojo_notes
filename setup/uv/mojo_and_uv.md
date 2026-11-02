[Up](../uv.md)

# Mojo and uv

To create a new `mojo` project; first create a new `uv` project; then add `mojo`.
```bash
$ uv init hello-world
$ cd hello-world
$ uv add mojo
```
Add some `mojo` code. Here an example `hello.mojo` is provided.
```python
def main():
    print("hello world")
```
To compile and execute you `mojo` code invoke:
```bash
$ uv run mojo hello.mojo
hello world
```
Or activate the `.venv` environment and run `mojo` in it.
```bash
$ uv sync
$ source .venv/bin/activate
(hello-world) $ mojo hello.mojo
```
**See**

[Python projects](python_and_uv/python_projects.md)

**Links**

[mojolang.org/docs/manual/quickstart/](https://mojolang.org/docs/manual/quickstart/)







