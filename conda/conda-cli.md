# Conda Commands

**A list of my commonly used [[conda]] commands.**

## Conda Basics

| Command                             | Description                                                                         |
|:----------------------------------- |:----------------------------------------------------------------------------------- |
| `conda --version`                   | Show the conda version                                                              |
| `conda info`                        | Display information about current conda install                                     |
| `conda update --all -c conda-forge` | Updates conda packages to the latest compatible version through conda-forge channel |
| `conda env list`                    | List all conda environments                                                         |

## Creating envs

| Command                                      | Description                                                      |
|:-------------------------------------------- |:---------------------------------------------------------------- |
| `conda create -n ENV, --name ENV`            | Create an environment ENV                                        |
| `conda create -n ENV python=3.11`            | Create an environment with a python 3.11 installed               |
| `conda create -p PATH, --prefix PATH`        | Full path to environment location                                |
| `conda create -n ENV --clone NEW_ENV`        | Create an environment as a copy of an existing local environment |
| `conda env create -f environment.yml -n ENV` | Create an environment based on an environment definition file.   |

- If anaconda is installed in the directory `$CONDADIR`, `conda create -n myenv` will seek to create an environment at `$CONDADIR/envs/myenv` . This is fine, if you own the directory and the directory is large enough for the contents of the complete environment. Otherwise, you may find it better to use `conda create -p $MyConda/envs/myenv python=3.11` followed by the appropriate `activate` command.

> Personally, I like to do this inside the folder of the project I'll be working on. The command will be `conda create -p ./env python=3.11`

- Unless you are in the directory containing the environment definition file, use `-f` to specify the file path of the environment definition file you want to use.

## Removing envs

| Command                            | Description                   |
|:---------------------------------- |:----------------------------- |
| `conda env remove --name ENV_NAME` | Delete an environment by name |
