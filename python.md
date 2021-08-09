*

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
