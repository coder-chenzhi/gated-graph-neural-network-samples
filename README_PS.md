To run `get_data.py`, we need to install `rdkit` package first. However, it is not trivial to install rdkit packages in Windows. There are two ways to install this package as the [official documents](https://github.com/rdkit/rdkit/blob/master/Docs/Book/Install.md) say. One is Installation of the pre-built binaries, another is Installation from source. We choose the former, as the latter need to install lots of other packages. However, the official site doesn't provide pre-built binaries. Fortunately, we find binaries from [unofficial site](https://github.com/ZhangJunQCC/RDKit-Python36-Windows-Binary).

Here is the process:
### Prerequisites

-   3.6+ (from http://www.python.org/)
-   numpy (from http://numpy.scipy.org/ or use `pip install numpy`). Binaries for win64 are available here: http://www.lfd.uci.edu/~gohlke/pythonlibs/#numpy
-   Pillow: (from https://python-pillow.github.io/> or use `pip install Pillow`)

#### Recommended extras

-   aggdraw: a library for high-quality drawing in Python. Instructions for downloading are here: <http://effbot.org/zone/aggdraw-index.htm> The new (as of May 2008) drawing code has been tested with v1.2a3 of aggdraw. Despite the alpha label, the code is stable and functional.
-   matplotlib: a library for scientific plotting from Python. <http://matplotlib.sourceforge.net/>
-   ipython : a very useful interactive shell (and much more) for Python. <http://ipython.scipy.org/dist/>
> -   win32all: Windows extensions for Python. <http://sourceforge.net/projects/pywin32/>

### Installation of RDKit binaries

-   Get the appropriate windows binary build from: https://github.com/rdkit/rdkit/releases
-   Extract the zip file somewhere without a space in the name, i.e. `C:\`
-   The rest of this will assume that the installation is in `C:\RDKit_2015_09_2`
-   Set the following environment variables:
   -   RDBASE: `C:\RDKit_2015_09_2`
   -   PYTHONPATH: `%RDBASE%` if there is already a PYTHONPATH, put `;%RDBASE%` at the end.
   -   PATH: add `;%RDBASE%\lib` to the end


Note that `get_data.py` can only be run at Linux, because it depends on some commands in linux-utils.