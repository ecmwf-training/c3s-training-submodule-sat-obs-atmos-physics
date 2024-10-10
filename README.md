# c3s-satellite-observations-lot1
A repository for storing the Satellite Observations training material


## Developer instructions


### CONDA environment for testing the build

To create an environment for building Jupyter Books, run the following:

```
conda create -y -n JUPYTER-BUILD -c conda-forge python=3.11 
conda activate JUPYTER-BUILD
pip install jupyter-book
```

### Testing the JupyterBook Build

With your JUPYTER-BUILD environment activated the following line will build the jupyterbook locally

```
rm -rf _build
jupyter-book build --all .
```

## Troubleshooting notes

1. Multiple Level 1 Headers (#) in a notebook seems to break the _toc definition of title. It is also bad practice so discourage.