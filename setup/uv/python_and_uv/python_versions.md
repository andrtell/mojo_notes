[Up](../python_and_uv.md)

# Python Versions

By default, `uv` will automatically download Python versions when they are required.
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

[docs.astral.sh/uv/guides/install-python/](https://docs.astral.sh/uv/guides/install-python/)