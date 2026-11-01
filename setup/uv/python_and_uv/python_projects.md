[Up](../python_and_uv.md)

# Python projects

Use `uv init` to create a new project
```bash
$ uv init hello-world
$ cd hello-world

# or

$ mkdir hello-world
$ cd hello-world
$ uv init
```
_Project files_
```bash
.
├── pyproject.toml
├── .python-version
├── README.md
└── src
    └── hello_world
        └── __init__.py
```
The `pyproject.toml` defines a `hello-world` entrypoint.

_pyproject.toml_
```toml
[project.scripts]
hello-world = "hello_world:main"
```
_src/hello_world/\_\_init\_\_.py_
```python
def main() -> None:
    print("Hello from hello-world!")
```
Use `uv run` to execute the entrypoint.
```bash
$ uv run hello-world
Hello from hello-world!
```
If needed a virtual environment `.venv` and a lock file `uv.lock` will be created.

_Project files_
```
.
├── ...
├── uv.lock
└── .venv
```
Use `uv add` to add a package.
```bash
$ uv add cowsay
```
_pyproject.toml_
```toml
[project]
dependencies = [
    "cowsay>=6.1",
]
```
Use `uv run` to run scripts in your project environment.
```bash
$ uv run -- cowsay -t 'hello'
```
Use  `uv sync` to update the environment before activating it.
```bash
$ uv sync
$ source .venv/bin/activate
(hello world) $ cowsay -t 'hello'
```

**Links**

[docs.astral.sh/uv/guides/projects/](https://docs.astral.sh/uv/guides/projects/)

[docs.astral.sh/uv/concepts/projects/](https://docs.astral.sh/uv/concepts/projects/)

[packaging.python.org/en/latest/guides/writing-pyproject-toml/](https://packaging.python.org/en/latest/guides/writing-pyproject-toml/)
