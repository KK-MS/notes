
## Books
* Great Python Cheat Sheet I found:
https://www.linkedin.com/posts/mengyaowang11_python-cheat-sheet-activity-6876776856129937408-gaUl?utm_source=linkedin_share&utm_medium=member_desktop_web

### Installed files
* Installed files are at `path_to_virtualenv>/lib/python<version>/site-packages/` or ` /usr/local/lib/python<version>/site-packages/`
* To know location of the `site-packages`, use command `python -m site`
* Also see section [site-packages](#site-packages)
<details> <summary> click for more info on installed files </summary>

When you run `pip install .` in a directory containing a Python package (usually with a `setup.py` file), the package is installed into the Python environment's site-packages directory. Here's a breakdown of what happens:

1. **Local Environment**: If you are using a virtual environment, the package will be installed in the `site-packages` directory of that virtual environment. This is typically located at:
   ```
   <path_to_virtualenv>/lib/python<version>/site-packages/
   ```

2. **Global Environment**: If you are not using a virtual environment, the package will be installed in the global Python environment's `site-packages` directory. This is typically located at:
   - On Linux and macOS:
     ```
     /usr/local/lib/python<version>/site-packages/
     ```
   - On Windows:
     ```
     C:\Python<version>\Lib\site-packages\
     ```

You can find the exact location of the `site-packages` directory by running the following Python command:
```sh
python -m site
```
This command will list all the site directories, including the `site-packages` directory where the installed packages are stored.

</details>

## site-packages
* https://stackoverflow.com/questions/31384639/what-is-pythons-site-packages-directory
* site-packages
site-packages is the target directory of manually built Python packages. When you build and install Python packages from source (using distutils, probably by executing python setup.py install), you will find the installed modules in site-packages by default.

There are standard locations:

Unix (pure)1: prefix/lib/pythonX.Y/site-packages
Unix (non-pure): exec-prefix/lib/pythonX.Y/site-packages
Windows: prefix\Lib\site-packages
1 Pure means that the module uses only Python code. Non-pure can contain C/C++ code as well.

site-packages is by default part of the Python search path, so modules installed there can be imported easily afterwards.

Useful reading
* [Installing Python Modules (for Python 2)](https://docs.python.org/2/install/)
* [Installing Python Modules (for Python 3)](https://docs.python.org/3/install/)

#### Package version
* To know version of package via command line
* Use command `pip list` and look for package
  ```
  pip list 
  Package                   Version
  ------------------------- -----------
  certifi                   2024.12.14
  charset-normalizer        3.4.1
  contourpy                 1.3.0
  cycler                    0.12.1
  ...
  matplotlib                3.7.1
  numpy                     1.26.4
  open-simulation-interface 3.7.0
  ...
  ```
* Helpful to run code via command line, or when we get errors like: `ERROR: No matching distribution found for numpy<3.0.0,>=2.1.1`
  ```py
  PS C:\hsk\01_fasim\osi3test> python -c "import numpy; print(numpy.version.version)"
  1.26.4
  ```

### Package creation
* Error: only dist-info is created and not the module itself?
When `pip install .` only creates a `.dist-info` folder and not the actual package folder, it usually indicates an issue with the package setup. Here are some common reasons and solutions:

1. **Missing `__init__.py`**: Ensure that your package directory contains an `__init__.py` file. This file is necessary for Python to recognize the directory as a package.

2. **Incorrect `setup.py` Configuration**: Check your `setup.py` file to ensure it is correctly configured. The `packages` argument in `setup()` should include the package directory. For example:
   ```python
   from setuptools import setup, find_packages

   setup(
       name='Test',
       version='1.0',
       packages=find_packages(),
   )
   ```

3. **Using `pyproject.toml`**: If you are using a `pyproject.toml` file instead of `setup.py`, make sure it is correctly configured. For example:
   ```toml
   [build-system]
   requires = ["setuptools", "wheel"]
   build-backend = "setuptools.build_meta"

   [project]
   name = "Test"
   version = "1.0"
   ```

4. **Editable Install**: If you are developing the package, consider using an editable install with `pip install -e .`. This allows you to make changes to the code without reinstalling the package.

5. **Check for Errors**: Run the installation command with the `-v` (verbose) flag to see detailed output and check for any errors:
   ```sh
   pip install -v .
   ```

By ensuring your package setup is correct and all necessary files are in place, you should be able to resolve the issue and have the package folder created in `site-packages`.

## venv

Virtual environment

C:\prj\Training\210809-Daniel\Daniel>C:\ins\Python\Python39\python.exe -m venv ds

C:\prj\Training\210809-Daniel\Daniel>source ds\Scripts\activate
'source' is not recognized as an internal or external command,
operable program or batch file.

C:\prj\Training\210809-Daniel\Daniel>ds\Scripts\activate        

(ds) C:\prj\Training\210809-Daniel\Daniel>python --version
Python 3.9.2

(ds) C:\prj\Training\210809-Daniel\Daniel>


## Links

**Book**: Python Data Science Handbook, Jake Vander Plas  
* **PDF**: https://jakevdp.github.io/PythonDataScienceHandbook/  
* **Github**: https://github.com/jakevdp/PythonDataScienceHandbook  

**faster**: https://numba.pydata.org/  
**coding style**: https://www.python.org/dev/peps/pep-0008/#id37  

## Unittest

https://docs.python.org/3/library/unittest.html

## ryven github

https://github.com/leon-thomm/Ryven

## Remove python2
sudo apt purge -y python2.7-minimal

#### You already have Python3 but 
#### don't care about the version 
sudo ln -s /usr/bin/python3 /usr/bin/python

#### Same for pip
sudo apt install -y python3-pip
sudo ln -s /usr/bin/pip3 /usr/bin/pip

#### Confirm the new version of Python: 3
python --version


## Online Tutor


### VISUALIZE CODE EXECUTION
Learn Python, Java, C, C++, JavaScript, and Ruby

http://pythontutor.com/


## Installation

* By Windows app store
PS C:\prj\cromaps\cromaps_search\code> & C:/Users/Krishnakumar.Mayanna/AppData/Local/Microsoft/WindowsApps/python.exe
App install 3.9.x

* Mingw also installed 3.8.x
Maybe I should have used, Mingw, we will see.

## using MinGW pacman
$ history | grep "pacman"
  194  pacman -S cmake
  215  pacman -S make
  287  pacman -S netcat
  312  pacman -S mingw-w64-x86_64-python-pyqt5
  313  pacman -S mingw-w64-x86_64-python-pip
  324  pacman -S mingw-w64-x86_64-python-pandas
  327  pacman -S mingw-w64-x86_64-python-scipy
  333  pacman -S mingw-w64-x86_64-cython
  334  pacman -S mingw-w64-x86_64-pylint
  335  pacman -S mingw-w64-x86_64-python-pylint
  344  pacman -S mingw-w64-x86_64-git
  345  pacman -S git
  367  pacman -S pip
  368  pacman -S python3-pip
  647  pacman -S mingw-w64-x86_64-python-matplotlib
  662  history | grep "pacman"
