# Introduction

This lesson introduces repo2docker, a tool that can build a computational environment from a source repository. It can be used with JupyterHub and other interactive computing services, such as is used by Binder. Jupyter4NFDI provides access to repo2dock, allowing users to build and launch an interactive environment from a repository.

We will look at what repo2docker does, why it can be useful for reproducible research, and what a repository needs in order to be ready for using repo2docker at Jupyter4NFDI.

## What is  repo2docker

repo2docker is a tool for building and running a user environment container from a source repository. It looks at the repository, identifies configuration files describing the environment, builds a container image, and can then launch that environment for interactive use. It can work with different types of source repositories, including Git repositories and open-science repositories such as Zenodo. (for details see: https://repo2docker.readthedocs.io/)

## Using repo2docker for reproducible research

Simply listing package names is not always enough to guarantee that an environment will remain identical over time. A project may work today and fail later because dependencies have changed. For reproducible environments, it is therefore important to think about versions and dependency management, not just package names.
