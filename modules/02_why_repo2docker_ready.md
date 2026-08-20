# Why make a repository Jupyter4NFDI-ready?

## Learning objectives

After this section, you will be able to:

- explain the gains from using repo2docker;
- differentiate between a source repository and the environment built from it;
- identify which kinds of repository sources can be launched with Jupyter4NFDI.

repo2docker makes it possible for anyone to run the code in a repository without first reconstructing your software setup. In order for that to happen, the repository needs to contain both the research or teaching material and enough information to build the software environment it needs.

That can help with:

- **reproducibility** ;
- **shareability** (another person can launch the same project from a link);
- **zero-install demonstrations and teaching**;
- **interactive research objects**.

Jupyter4NFDI can build repo2docker environments from sources such as GitHub, GitLab and Zenodo. The same general repo2docker mechanism is also used by Binder services. 

Think of the repository as a recipe:

1. the notebooks and code say **what to run**;
2. configuration files say **what software is needed**;
3. repo2docker turns those instructions into an interactive environment.

The repository is therefore the source from which the environment can be rebuilt.

## Further reading

- [Jupyter4NFDI: Repo2Docker (Binder)](https://nfdi-jupyter.de/users/jupyterlab/repo2docker/)
- [repo2docker documentation](https://repo2docker.readthedocs.io/)
