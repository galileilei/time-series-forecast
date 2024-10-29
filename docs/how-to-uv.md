# uv whirlwind guide 

this project use `uv` to manage python code, because `brew install python@3.12` took too long.

official website here: https://github.com/astral-sh/uv

in short, **everything** goes through `uv`.

|task|old way |new way|
|---|---|---|
|init project virtual environment | `python3.10 -m venv .venv` | `uv init` |
|add a project dependency | `{$VENV}/bin/python -m pip install foo`| `uv add foo`|
|running a script |`python hack/download.py`| `uv run hack/download.py`|
|specify script dependency | impossible. has to be a project dependency. | `uv add --script hack/download.py 'foo'`|

# getting the data

these steps are done outside of shell:
- get `~/.kaggle/kaggle.json` ready. follow [instruction here](https://github.com/Kaggle/kaggle-api/blob/main/docs/README.md#api-credentials)
- accept the competition rules on [official website](https://www.kaggle.com/competitions/jane-street-real-time-market-data-forecasting).

In a terminal:
```shell
cd ${path-to-this-project}
uv init
uv pip install kaggle
uv tool run kaggle competitions download -c jane-street-real-time-market-data-forecasting
```
