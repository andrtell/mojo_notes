[Up](../python_and_uv.md)

# Python scripts

Execute python script using `uv run`
```python
import sys

print(" ".join(sys.argv[1:]))
```
```Bash
$ uv run script.py 1 2 3
1 2 3
```
Or use a `#!` 
```python
#!/usr/bin/env -S uv run --script
import sys

print(" ".join(sys.argv[1:]))
```
```bash
$ chmod +x script.py

$ ./script.py 1 2 3
1 2 3
```
Use `--with` to use a dependency.
```python
import time
from rich.progress import track

for i in track(range(20), description="For example:"):
    time.sleep(0.05)
```
```Bash
$ uv run --with rich script.py
For example: ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:01
```
Or use [inline script metadata](https://packaging.python.org/en/latest/specifications/inline-script-metadata/#inline-script-metadata).
```Bash
$ uv init --script script.py --python 3.12
$ uv add  --script script.py 'rich'
```
```python
# /// script
# requires-python = ">=3.12"
# dependencies = [
#     "rich>=15.0.0",
# ]
# ///

def main() -> None:
    print("Hello from script.py!")

if __name__ == "__main__":
    main()
```
```python
# /// script
# requires-python = ">=3.12"
# dependencies = [
#     "requests<3",
#     "rich>=15.0.0",
# ]
# ///

import time
from rich.progress import track

def main() -> None:
    for i in track(range(20), description="For example:"):
        time.sleep(0.05)

if __name__ == "__main__":
    main()
```
```bash
$ uv run script.py
Installed 4 packages in 14ms
For example: ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 100% 0:00:01
```
**Links**

[docs.astral.sh/uv/guides/scripts/](https://docs.astral.sh/uv/guides/scripts/)