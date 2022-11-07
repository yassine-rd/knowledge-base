# Managing conda environments using _yaml_ files

![YAML llogo](../conda/images/yaml-logo.png)

## Building an environment

If you want to be more organized and efficient by separating environments for different projects that might require specific libraries, [[conda]] allows you to easily create environments through _yaml_ files. [Yaml](https://en.wikipedia.org/wiki/YAML) is a recursive acronym for “YAML Ain’t Markup Language” and it is a format commonly used for configuration files. The _yaml_ file contains information on the environment you want to build such as:

- **Name of environment**, such as `name: myenv`
- **Channels**, the locations where packages are stored. They serve as the base for hosting and managing packages. The `conda-forge` channel is free for all to use.
- **Dependencies**, such as the libraries you want available for import and their versions. Note that if you substitute any of the version fields with an , the most recent version of that field will be installed. An eventual pip list for the libraries that normally need to be installed through `pip install` might be needed here.

Here is what a _yaml_ file looks like:

``` yaml
name: myenv
channels:
 - apple
 - conda-forge
dependencies:
 - python=3.9
 - pip>=19.0
 - jupyter
 - tensorflow-deps
 - scikit-learn
 - numpy
 - pandas
 - matplotlib
 - ipykernel
 - pip:
  - tensorflow-macos
  - tensorflow-metal
```

A new environment can be built in any folder as long as you are aware of the path to the _yaml_ file you want to use. From within your terminal, type:

`conda env create -f <path_to_yaml_file>`
`conda activate <environment_name>`

### Creating a basic env with Tensorflow for arm64 architectures

We will be creating a basic conda environment with Tensorflow library for Deep Learning applications using a `.yaml` file. This environment can be used to run the Bird Classifier application.

1. `conda env create -f tf-arm64-env.yml -n tensorflow-arm64`
2. `conda activate tensorflow-arm64`

## Updating an environment

While in a certain environment you can still install new packages that will be part of the environment, but **will not** be part of the _yaml_ file. This procedure is not advisable because you can easily lose track of what libraries and what versions you are working with. To add a library or modify a version of a package in an existing environment, you need to:

1. First make all the wanted changes to the _yaml_ file
2. Deactivate the environment you are in by typing in the terminal: `conda deactivate`(this step is necessary only if you are currently in the environment you want to update)
3. Then type `conda env update -f <path_to_yaml_file>`
4. Reactivate the environment by `conda activate <environment_name>`

To simply **switch** between environments, all you need to do is run steps 2 and 4.

## Exporting an environment

Saving your existing environment dependencies

1. `conda activate <env_name>`
2. `conda env export > environment.yml`

> If we want to avoid version numbers, we can use the following command instead: `conda env export | cut -f 1 -d '=' > environment.yml`

## Deleting an environment

Finally, if you want to do some housekeeping by removing an environment that is no longer useful, type `conda env remove -name <environment_name>`
