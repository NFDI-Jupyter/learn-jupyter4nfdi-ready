# Configuration files for repo2docker

## Learning objectives

After this section, you will be able to:

- explain how repo2docker knows what software is needed;
- choose a suitable configuration file for a simple Python or R project.

repo2docker looks through a repository for configuration files which include information in the required software to run the code. In most cases, these are ordinary files already used by package managers .

Common examples include:

| File | Typical use |
| --- | --- |
| `requirements.txt` | Python packages installed with `pip` |
| `install.R` | R package installation |
| `apt.txt` | Ubuntu system packages |
| `runtime.txt` | Runtime version when the main environment file cannot express it |
| `postBuild` | Commands to run after the environment has been installed |

You normally do **not** need all of these files. You can start with the simplest minimal description that can reproduce your project.

For a small teaching repository, putting the configuration files at the top level keeps the structure easy to understand. repo2docker also supports a `.binder/` directory for Binder-specific configuration.

A minimal Python repository might look like this:

```text
my-project/
├── README.md
├── analysis.ipynb
└── requirements.txt
```

## One environment definition is usually enough

More configuration is not automatically better. Some supported files take priority over others, and some combinations can cause one file to be ignored. For example, if the Python version is already specified in `environment.yml`, a Python version in `runtime.txt` is ignored.

When in doubt, check the current repo2docker documentation rather than combining several environment definitions.

## Quick exercise


## Further reading
- [repo2docker: configuration files](https://repo2docker.readthedocs.io/en/stable/configuration/)
