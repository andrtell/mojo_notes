[Up](../uv.md)

# Python and uv

By default, `uv` will download Python versions when required.
```Bash
$ wich python
/usr/bin/python  # (managed by the OS)

$ python --version
3.14.8

$ uvx python@3.12 -c "print('hello world')"
# uv downloads python 3.12 ...
hello world
```
**See**

* [Python scripts](python_and_uv/python_scripts.md) | `uv run`
* [Python tools](python_and_uv/python_tools.md) | `uvx`
* [Python projects](python_and_uv/python_projects.md) | `uv init`

**Links**

[docs.astral.sh/uv/guides/install-python/](https://docs.astral.sh/uv/guides/install-python/)

[docs.astral.sh/uv/concepts/python-versions/](https://docs.astral.sh/uv/concepts/python-versions/)

