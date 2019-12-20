# Jupyter Notebook

## Executing Jupyter Notebook from Command Line
```bash
jupyter nbconvert --ExecutePreprocessor.timeout=None --to notebook --execute <noteboo_name>.ipynb
```

The `--ExecutePreprocessor.timeout=None` is important to turn off the
timeout for the maximum time (in seconds) each notebook cell is allowed
to run.

also see: <https://nbconvert.readthedocs.io/en/latest/execute_api.html#executing-notebooks-from-the-command-line>

If you have timeout problems - this might help: `pip install git+https://github.com/jupyter/nbconvert.git`

## View Jupyter Notebook online
This can be done here: <https://nbviewer.jupyter.org/>
