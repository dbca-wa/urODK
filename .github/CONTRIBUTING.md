# Contributing to urODK

This outlines how to propose a change to urODK. 

urODK contains the configuration files for BinderHub to build a Docker image
running RStudio Server with pre-installed ruODK and its dependencies.

The underlying technology is [repo2docker](https://repo2docker.readthedocs.io/en/latest/).

ruODK is configures through:

* `runtime.txt` defines an R snapshot available through [MRAN](https://mran.microsoft.com/documents/rro/reproducibility)
* `apt.txt` lists system libraries to be installed via `apt-get`
* `install.R` lists R package installation commands

## Development
If you run urODK on BinderHub and find something missing, then fork the repo and
send a pull request with the following changes. If that seems daunting, create
a GitHub issue instead and tell us what's missing.

If you find that an R package is missing, which you'd like to see included by default,
add the successful installation command to `install.R`.

If the package installation fails on a missing system library, add the library
to `apt.txt`.

If the R version is out of date, update `runtime.txt`.


