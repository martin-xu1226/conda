# Miniforge

## Download
- https://github.com/conda-forge/miniforge

## Install and Usage

### Install Version

```shell
$ conda -V
conda 24.11.3

```

### Usage

- **Conda Help**

```shell
$ conda -h
usage: conda-script.py [-h] [-v] [--no-plugins] [-V] COMMAND ...

conda is a tool for managing and deploying applications, environments and packages.

options:
  -h, --help            Show this help message and exit.
  -v, --verbose         Can be used multiple times. Once for detailed output,
                        twice for INFO logging, thrice for DEBUG logging, four
                        times for TRACE logging.
  --no-plugins          Disable all plugins that are not built into conda.
  -V, --version         Show the conda version number and exit.

commands:
  The following built-in and plugins subcommands are available.

  COMMAND
    activate            Activate a conda environment.
    clean               Remove unused packages and caches.
    commands            List all available conda subcommands (including those
                        from plugins). Generally only used by tab-completion.
    compare             Compare packages between conda environments.
    config              Modify configuration values in .condarc.
    create              Create a new conda environment from a list of
                        specified packages.
    deactivate          Deactivate the current active conda environment.
    doctor              Display a health report for your environment.
    export              Export a given environment
    info                Display information about current conda install.
    init                Initialize conda for shell interaction.
    install             Install a list of packages into a specified conda
                        environment.
    list                List installed packages in a conda environment.
    notices             Retrieve latest channel notifications.
    package             Create low-level conda packages. (EXPERIMENTAL)
    remove (uninstall)  Remove a list of packages from a specified conda
                        environment.
    rename              Rename an existing environment.
    repoquery           Advanced search for repodata.
    run                 Run an executable in a conda environment.
    search              Search for packages and display associated information
                        using the MatchSpec format.
    update (upgrade)    Update conda packages to the latest compatible
                        version.


```

```bash
$ conda env -h
usage: conda-script.py env [-h] command ...

positional arguments:
  command
    config    Configure a conda environment.
    create    Create an environment based on an environment definition file.
    export    Export a given environment
    list      An alias for `conda info --envs`. Lists all conda environments.
    remove    Remove an environment.
    update    Update the current environment based on environment file.

options:
  -h, --help  Show this help message and exit.


```

- **配置国内镜像源**

```shell
$ conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --set show_channel_urls yes
```

```shell
$ conda config --show channels
channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
  - conda-forge

```

- **清理缓存**

```shell
conda clean -i # 清除索引缓存 
conda clean -t # 删除下载的临时包

```

- **列出当前系统中所有已创建的 Conda 虚拟环境**

```shell
$ conda env list

# conda environments:
#
base                   C:\miniforge3

```

- **搜索可用版本**

```shell
$ conda search python=3.12
Loading channels: done
# Name                       Version           Build  Channel
python                        3.12.0 h2628c8c_0_cpython  conda-forge       
python                        3.12.1 h2628c8c_0_cpython  conda-forge       
python                        3.12.1 h2628c8c_1_cpython  conda-forge       
python                        3.12.2 h2628c8c_0_cpython  conda-forge       
python                        3.12.3 h2628c8c_0_cpython  conda-forge       
python                        3.12.4 h889d299_0_cpython  conda-forge       
python                        3.12.5 h889d299_0_cpython  conda-forge       
python                        3.12.6 hce54a09_0_cpython  conda-forge       
python                        3.12.6 hce54a09_1_cpython  conda-forge       
python                        3.12.6 hce54a09_2_cpython  conda-forge       
python                        3.12.7 hce54a09_0_cpython  conda-forge       
python                        3.12.8 h3f84c4b_1_cpython  conda-forge       
python                        3.12.9 h3f84c4b_0_cpython  conda-forge       
python                        3.12.9 h3f84c4b_1_cpython  conda-forge       
python                       3.12.10 h3f84c4b_0_cpython  conda-forge       

```

- **创建虚拟环境**

```shell
$ conda create -n langchain_py312 python=3.12.10
Channels:
 - conda-forge
Platform: win-64
Collecting package metadata (repodata.json): ...working... done
Solving environment: ...working... done

...

#
# To activate this environment, use
#
#     $ conda activate langchain_py312
#
# To deactivate an active environment, use
#
#     $ conda deactivate

```

- **激活**

```shell
$ conda activate langchain_py312

$ conda env list

# conda environments:
#
langchain_py312      * C:\Users\Administrator\.conda\envs\langchain_py312
base                   C:\miniforge3

```

**安装指定版本**

```shell
$ conda install langchain=0.3.20
Channels:
 - conda-forge
Platform: win-64
Collecting package metadata (repodata.json): done
Solving environment: done


==> WARNING: A newer version of conda exists. <==
    current version: 24.11.3
    latest version: 25.3.1

...

```

