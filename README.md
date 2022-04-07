# How to use: Added by @n-y-kim
<ol>
  <li>Download the most recent release version from <a href="https://github.com/liblouis/liblouis">liblouis</a> repo.(zip file)</li>
  <li>Check your environment. <code>import louis</code> is not supportable at <code>arm64</code> architecture(v 3.21.0). Only <code>x86_64</code> would be able to get the correct path.</li>
  <li>Unzip your installed file.</li>
  <li>RUN <code>./configure</code></li>
  <li>RUN <code>make</code></li>
  <li>RUN <code>sudo make install</code></li>
  <li>Move to python folder and RUN <code>python setup.py install</code></li>
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
  
