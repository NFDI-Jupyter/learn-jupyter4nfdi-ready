# R and system dependencies

## Learning objectives

After this section, you will be able to:

- use `install.R` to describe R package installation;
- distinguish language packages from operating-system packages;
- choose between `apt.txt` and `postBuild` for common setup tasks.

## R projects

For an project using R, repo2docker needs an `install.R` file. This is an R script, so it can contain normal R installation commands (note the difference to `requirements.txt` which isn't a script but a plain text file). For example, this is how `install.R`  could look:

```r
install.packages(c("ggplot2", "dplyr", "tidyr"))
```

To specify R version, you need to use a separate file called `runtime.txt`. In other words, `install.R` can specify the packages to install, but not the R version itself. For example, `runtime.txt` could contain:

```r
r-4.2
```
Note that only R versions supported by repo2docker can be selected this way (to know which these are, consult the most recent documentation for repo2docker).

## System-level dependencies

Some Python or R packages rely on software supplied by the operating system. These could be, for example, command-line programs and system libraries. These need to be specificed in different files than the ones described above. It is best to check which operating system image Jupyter4NFDI uses at a given time for repo2docker build. For example, for an Ubuntu 24.04-based repo2docker setup you would need to use `apt.txt` (packages available from Ubuntu's package repositories):

```text
git
curl
```

## What `postBuild` is for

`postBuild` is a script run after the environment and its packages have been installed. It is useful for one-time build tasks such as preparing files, downloading small resources or compiling project assets. For example:

```bash
#!/bin/bash
set -e

python scripts/prepare_example_data.py
```

Do not use `postBuild` as a substitute for `apt.txt` when you simply need an Ubuntu package. Keeping dependency declarations in their intended files makes the environment easier to understand and maintain.



## Further reading

- [repo2docker: research and data-science configuration](https://repo2docker.readthedocs.io/en/stable/configuration/research/)
- [repo2docker: system-wide configuration](https://repo2docker.readthedocs.io/en/stable/configuration/system/)
- [repo2docker: post-build actions](https://repo2docker.readthedocs.io/en/stable/configuration/actions/)
