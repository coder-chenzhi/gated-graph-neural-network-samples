To run `get_data.py`, we need to install `rdkit` package first. However, it is not trivial to install rdkit packages in Windows. There are two ways to install this package as the [official documents](https://github.com/rdkit/rdkit/blob/master/Docs/Book/Install.md) say. One is Installation of the pre-built binaries, another is Installation from source. We choose the former, as the latter need to install lots of other packages. However, the official site doesn't provide pre-built binaries. Fortunately, we find binaries from [unofficial site](https://github.com/ZhangJunQCC/RDKit-Python36-Windows-Binary).

Here is the process:
- Get the appropriate windows binary build from: https://github.com/rdkit/rdkit/releases
- Extract the zip file somewhere without a space in the name, i.e. C:\
- The rest of this will assume that the installation is in C:\RDKit_2015_09_2
- Set the following environment variables:
- RDBASE: C:\RDKit_2015_09_2
- PYTHONPATH: %RDBASE% if there is already a PYTHONPATH, put ;%RDBASE% at the end.
- PATH: add ;%RDBASE%\lib to the end

Note that `get_data.py` can only be run at Linux, because it depends on some commands in linux-utils.