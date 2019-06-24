# PyInstaller Overview

PyInstaller bundles a Python application and all its dependencies into a single package. The user can run the packaged app without installing a Python interpreter or any modules.

:Documentation: https://pyinstaller.readthedocs.io/ :Website: http://www.pyinstaller.org/ :Code: https://github.com/pyinstaller/pyinstaller :Donate: | https://www.bountysource.com/teams/pyinstaller | Bitcoin: @abstr_number JUFjawzWDR @abstr_number Tc @abstr_number z @abstr_number TKXstVFdjkDY @abstr_number FbtK | `more ways to donate … <http://www.pyinstaller.org/donate.html>`_

PyInstaller reads a Python script written by you. It analyzes your code to discover every other module and library your script needs in order to execute. Then it collects copies of all those files -- including the active Python interpreter! -- and puts them with your script in a single folder, or optionally in a single executable file.

PyInstaller is tested against Windows, Mac OS X, and GNU/Linux. However, it is not a cross-compiler: to make a Windows app you run PyInstaller in Windows; to make a GNU/Linux app you run it in GNU/Linux, etc. PyInstaller has been used successfully with AIX, Solaris, and FreeBSD, but is not tested against them.

## Main Advantages

  * Works out-of-the-box with any Python version @abstr_number . @abstr_number / @abstr_number . @abstr_number - @abstr_number . @abstr_number .
  * Fully multi-platform, and uses the OS support to load the dynamic libraries, thus ensuring full compatibility.
  * Correctly bundles the major Python packages such as numpy, PyQt @abstr_number , PyQt @abstr_number , PySide, Django, wxPython, matplotlib and others out-of-the-box.
  * Compatible with many @abstr_number rd-party packages out-of-the-box. (All the required tricks to make external packages work are already integrated.)
  * Libraries like PyQt @abstr_number , PyQt @abstr_number , PySide, wxPython, matplotlib or Django are fully supported, without having to handle plugins or external data files manually.
  * Working code signing on OS X.
  * Bundles MS Visual C++ DLLs on Windows.



## Installation

PyInstaller is available on PyPI. You can install it through `pip`::
    
    
      pip install pyinstaller
    

## Requirements and Tested Platforms

  * Python: 

    * @abstr_number . @abstr_number or @abstr_number . @abstr_number - @abstr_number . @abstr_number 
    * PyCrypto_ @abstr_number . @abstr_number + (only if using bytecode encryption)
  * Windows ( @abstr_number bit/ @abstr_number bit):

    * Windows XP or newer.
  * GNU/Linux ( @abstr_number bit/ @abstr_number bit)

    * ldd: Console application to print the shared libraries required by each program or shared library. This typically can be found in the distribution-package `glibc` or `libc-bin`.
    * objdump: Console application to display information from object files. This typically can be found in the distribution-package `binutils`.
    * objcopy: Console application to copy and translate object files. This typically can be found in the distribution-package `binutils`, too.
  * Mac OS X ( @abstr_number bit):

    * Mac OS X @abstr_number . @abstr_number (Lion) or newer.



## Usage

Basic usage is very simple, just run it against your main script::
    
    
      pyinstaller /path/to/yourscript.py
    

For more details, see the `manual`_.

## Untested Platforms

The following platforms have been contributed and any feedback or enhancements on these are welcome.

  * FreeBSD

    * ldd
  * Solaris

    * ldd
    * objdump
  * AIX

    * AIX @abstr_number . @abstr_number or newer. PyInstaller will not work with statically linked Python libraries.
    * ldd
  * PowerPC GNU/Linux (Debian)




Before using any contributed platform, you need to build the PyInstaller bootloader, as we do not ship binary packages. Download PyInstaller source, and build the bootloader::
    
    
        cd bootloader
        python ./waf distclean all
    

Then install PyInstaller::
    
    
        python setup.py install
    

or simply use it directly from the source (pyinstaller.py).

.. _PyCrypto: https://www.dlitz.net/software/pycrypto/ .. _`manual`: https://pyinstaller.readthedocs.io/en/latest/