# uv whirlwind guide 

this project use `uv` to manage python code, because `brew install python@3.12` took too long.

official website here: https://github.com/astral-sh/uv

in short, **everything** goes through `uv`.

|task|old way |new way|
|---|---|---|
|init project virtual environment | `python3.10 -m venv .venv` | `uv init` |
|add a project dependency | `{$VENV}/bin/python -m pip install foo`| `uv add foo`|
|running a script |`python hack/download.py`| `uv run hack/download.py`|
|specify script dependency | impossible. has to be a project depedency. | `uv add --script hack/download.py 'foo'`|

