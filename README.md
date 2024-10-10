# c3s-satellite-observations-lot1

A repository for storing the Satellite Observations training material. This repository will automatically 
build a develop version of the Jupyter Book that can be used for review purposes.


## Notebook provider instructions

Notebook providers are responsible for ensuring that the github actions succesfully build and deploy the
JupyterBook. It is advisable to test run the build commands locally before pushing to the repository as this
will save you time and effort.

### GitHub actions

There are two github actions in place for this repository:

The **`Build`** action builds the JupyterBook using the same proceedure as local build described below.
It is activated when a pull request to the `develop` branch is opened, or when any change is made to the 
develop branch (e.g. after merging a pull request). A pull request can only be merged
into the develop branch if the `Build` action is successful.


The **`Deploy`** action deploys the build JupyterBook to the github pages associated with this repository.
This action is activated when a change is made to the develop branch, after the build action.


### Building the JupyterBook locally

The following instructions are for Linux and MacOS users.

It is recommended that you test the build locally prior to creating your pull request to develop,
this will address many of the minor issues you may face and provide you with more readable output.
To ensure that you have the same software installed required to build the JupyterBook,
and that you are not using any unsupported software packages during a local build, it is recommended
that you create an conda-forge environment for building Jupyter Books:

```
conda create -y -n JUPYTER-BUILD -c conda-forge python=3.12
conda activate JUPYTER-BUILD
pip install jupyter-book
```

With your JUPYTER-BUILD environment activated the following line will build the jupyterbook locally:

```
rm -rf _build
jupyter-book build --all .
```

This will create all the html files used to create the JupyterBook in the untracked `_build/` folder.
You can open the homepage of this local build with:

```
open _build/html/index.html
```

## Troubleshooting notes

1. Multiple Level 1 Headers (#) in a notebook seems to break the _toc definition of title. It is also bad practice so discourage.