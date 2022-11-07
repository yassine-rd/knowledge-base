# Introduction to Conda

![Conda illustration](../conda/images/conda-logo.png)

**What is Conda ?**

**Conda** is a multi-platform open-source package management system. It was initially created to solve package management problems for Python data scientists and is now a popular package manager for Python and R packages. Like all package management systems, Conda helps you create, find, and install packages you need.

> With conda, you can create, export, list, remove, and update environments that have different versions of Python and/or packages installed in them. Switching or moving between environments is called activating the environment. You can also share an environment file.

**What does Conda Offer?**

- Conda provides prebuilt packages or binaries (which generally avoids the need to deal with compiling packages from source). [TensorFlow](https://www.tensorflow.org/) is an example of a tool widely used by data scientists which is difficult to install source (particularly with GPU support), but that can be installed using Conda in a single step.
- Conda is cross platform, with support for Windows, MacOS, GNU/Linux, and support for multiple hardware platforms, such as x86 and aarch64.
- Where a library or tools is not already packaged for install using `conda`, Conda allows for using other package management tools (such as `pip`) inside Conda environments.

**What problem is Conda trying to solve ?**

When you start learning Python, it is a good starting point to install the newest Python version with the latest versions of the packages you need or want to play around with. Then, most likely, you immerse yourself in this world, and download Python applications from [GitHub](https://github.com/search?l=Python&q=python&type=Repositories&utf8=%E2%9C%93), [Kaggle](https://www.kaggle.com/) or other sources. These applications may need other versions of Python/packages than the ones you have been currently using

In this case, you need to set up different so-called **environments**.

## Miniforge

[Miniforge](https://github.com/conda-forge/miniforge) a minimal installer for conda specific to [conda-forge](https://conda-forge.org/). It allows you to install the conda package manager with the following features pre-configured

- conda-forge set as the default (and only) channel.
  - Packages in the base environment are obtained from the [conda-forge channel](https://anaconda.org/conda-forge).
- An emphasis on supporting various CPU architectures (x86_64, ppc64le, and aarch64 including Apple M1).

> With Apple’s new M1 architecture based on ARM64, Anaconda does not support M1 natively yet. So to utilize full performance of M1, we’re to install conda with miniforge which has native support on M1.

### Set up

1. Install Homebrew [The Missing Package Manager for macOS (or Linux) — Homebrew](https://brew.sh/)
2. Download [Miniforge3](https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)
    - You can also download Miniforge with Homebrew using `brew install --cask miniforge`
3. Install Miniforge3 and restart your terminal as soon as the installation finishes:

```bash
chmod +x ~/Downloads/Miniforge3-MacOSX-arm64.sh
sh ~/Downloads/Miniforge3-MacOSX-arm64.sh
source ~/miniforge3/bin/activate
```
