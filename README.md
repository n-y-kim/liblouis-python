# Liblouis Python ctypes bindings

These bindings allow you to use liblouis from within Python. The
package is called "louis". See the documentation included in the
module for usage instructions.

These bindings use ctypes to access the liblouis shared library. The
liblouis shared library needs to be located in the library search
path. In most cases, if liblouis has been installed in a standard
location on your system, this is already the case and the bindings
will work without any additional steps.

A standard distutils setup.py script is provided for installation
tasks. To install this package for system wide use, run (as root):

``` python
python setup.py install
```
Some tests are located in `tests`. Run them with

``` console
pytest
```

# How to use: Added by @n-y-kim
<ol>
  <li>Download the most recent release version from <a href="https://github.com/liblouis/liblouis">liblouis</a> repo.(zip file)</li>
  <li>Check your environment. <code>import louis</code> is not supportable at <code>arm64</code> architecture(v 3.21.0). Only <code>x86_64</code> would be able to get the correct path.</li>
  <li>Unzip your installed file.</li>
  <li>RUN <code>./configure</code></li>
  <li>RUN <code>make</code></li>
  <li>RUN <code>sudo make install</code></li>
  <li>Move to python file and RUN <code>python setup.py install</code></li>
  <li>You would be able to <code>import louis</code> and test. </li>
  <br>EXAMPLE:
  
  ``` python
  import louis
  
  print(louis.translateString(["braille-patterns.cti", "en-us-g2.ctb"], "Hello, World!"))
  #⠠⠓⠑⠇⠇⠕⠂⠀⠠⠸⠺⠖
  
  print(louis.backTranslateString(["braille-patterns.cti", "en-us-g2.ctb"], "⠓⠑⠇⠇⠕"))
  #hello
  
  ```
</ol>

If you have <a href="https://github.com/liblouis/liblouis/issues/990">this problem(issue #990)</a>, please try ```sudo apt update``` & ```sudo apt upgrade```
  
