# Python projects with `requirements.txt`

## Learning objectives

After this section, you will be able to:

- create a minimal `requirements.txt` for a repository with a Jupyter Notebook;
- explain why version constraints matter for reproducibility.

For a Jupyter Notebook, `requirements.txt` is often the simplest environment file. Put one package requirement per line.

```text
numpy
pandas
matplotlib
scikit-learn
```

repo2docker will install these packages when building the environment to run the Jupyter Notebook.

## Pinning versions

A package name alone does not say which release should be installed. If dependencies change, a notebook that works today may behave differently later.

For teaching material or a reproducible example, you can pin versions:

```text
numpy==2.0.1
pandas==2.2.2
matplotlib==3.9.1
scikit-learn==1.5.1
```

Exact pins improve repeatability, but they also need maintenance. A practical approach is to test the environment regularly and update pins deliberately rather than leaving them unchanged indefinitely.

When using `requirements.txt`, repo2docker can read a Python version from `runtime.txt`. The current syntax is:

```text
python-3.11
```

Use `runtime.txt` only when the main environment specification cannot already express the runtime version. If you use `environment.yml`, put the Python version there instead.


## Exercise

We will use this [sample repository](https://github.com/NFDI-Jupyter/jupyter4nfdi-ready-template) to create a `requirements.txt` file which will then allow you to launch the repository in Jupyter4NFDI using repo2docker.

1. Create your own copy of the repository using this template: <img width="1315" height="211" alt="image" src="https://github.com/user-attachments/assets/c6ad8c80-c9ee-43fa-8f8e-84a9f56c2c20" />
2. Working in your own copy of the repository add  a `requirements.txt` file which specifies the Python packages needed to run the code in the [sample Jupyter Notebook](dining_out_survey_analysis.ipynb) in this repository.
3. The contents of the `requirements.txt` should be
```
pandas==3.0.5
altair==6.2.2
```
4. Once you added the `requirements.txt` file, log into Jupyter4NFDI and in the Dashboard select `repo2docker` option.
<img width="1412" height="335" alt="image" src="https://github.com/user-attachments/assets/f0a18232-b230-4c41-8a2a-775473968ab8" />

## Further reading

- [repo2docker: Python configuration](https://repo2docker.readthedocs.io/en/stable/configuration/development/)
- [repo2docker: system-wide configuration and `runtime.txt`](https://repo2docker.readthedocs.io/en/stable/configuration/system/)
