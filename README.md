# Time-Series-Analysis
Times Series Analysis with various examples

## Installation in R

Prophet is a [CRAN package](https://cran.r-project.org/package=prophet) so you can use `install.packages`.

```R
install.packages('prophet')
```

After installation, you can [get started!](https://facebook.github.io/prophet/docs/quick_start.html#r-api)

### Windows

On Windows, R requires a compiler so you'll need to [follow the instructions](https://github.com/stan-dev/rstan/wiki/RStan-Getting-Started) provided by `rstan`. The key step is installing [Rtools](http://cran.r-project.org/bin/windows/Rtools/) before attempting to install the package.

If you have custom Stan compiler settings, install from source rather than the CRAN binary.

## Installation in Python

Prophet is on PyPI, so you can use `pip` to install it. From v0.6 onwards, Python 2 is no longer supported.

```bash
pip install fbprophet
```

The default dependency that Prophet has is `pystan`. PyStan has its own [installation instructions](http://pystan.readthedocs.io/en/latest/installation_beginner.html). Install pystan with pip before using pip to install fbprophet.

You can also choose a (more experimental) alternative stan backend called `cmdstanpy`. It requires the [CmdStan](https://mc-stan.org/users/interfaces/cmdstan) command line interface and you will have to specify the environment variable `STAN_BACKEND` pointing to it, for example:

```
# bash
$ CMDSTAN=/tmp/cmdstan-2.22.1 STAN_BACKEND=CMDSTANPY pip install fbprophet
```

Note that the `CMDSTAN` variable is directly related to `cmdstanpy` module and can be omitted if your CmdStan binaries are in your `$PATH`.

It is also possible to install Prophet with two backends:

```
# bash
$ CMDSTAN=/tmp/cmdstan-2.22.1 STAN_BACKEND=PYSTAN,CMDSTANPY pip install fbprophet
```

After installation, you can [get started!](https://facebook.github.io/prophet/docs/quick_start.html#python-api)

If you upgrade the version of PyStan installed on your system, you may need to reinstall fbprophet ([see here](https://github.com/facebook/prophet/issues/324)).

### Anaconda

Use `conda install gcc` to set up gcc. The easiest way to install Prophet is through conda-forge: `conda install -c conda-forge fbprophet`.

### Windows

On Windows, PyStan requires a compiler so you'll need to [follow the instructions](http://pystan.readthedocs.io/en/latest/windows.html). The easiest way to install Prophet in Windows is in Anaconda.

### Linux

Make sure compilers (gcc, g++, build-essential) and Python development tools (python-dev, python3-dev) are installed. In Red Hat systems, install the packages gcc64 and gcc64-c++. If you are using a VM, be aware that you will need at least 4GB of memory to install fbprophet, and at least 2GB of memory to use fbprophet.

## Changelog

### Version 0.6 (2020.03.03)

- Fix bugs related to upstream changes in `holidays` and `pandas` packages.
- Compile model during first use, not during install (to comply with CRAN policy)
- `cmdstanpy` backend now available in Python
- Python 2 no longer supported

