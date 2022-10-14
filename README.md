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

## If you have <a href="https://github.com/liblouis/liblouis/issues/990">this problem(issue #990)</a>(cython OSError), follow these steps:
(I got this error when I tried deploying web server, nginx & gunicorn on Ubuntu)

<ol>
  <li>Go to <code>~/python/louis/__init__.py</code></li>
  <li>Add function <code>CDLL</code> inside <code>from ctypes import ~</code></li>
  <li>Fix line 61:</li>
 
  ``` python
  import os
  path_f = os.path.abspath( os.path.join(os.path.dirname(__file__), "liblouis.so.20"))
  liblouis = CDLL(path_f)
  
  ```
  <li>RUN <code>python setup.py install</code> again</li>
  <li>Go to <code>/usr/local/lib</code>(your library file) and check if <code>liblouis.so.20</code> and <code>liblouis.a</code> exist</li>
  <li> Copy those files to your python <code>louis</code> package folder. For example, my conda environments are: <code>/home/ubuntu/anaconda3/envs/pytorch_latest_p37/lib/python3.7/site-packages/louis/</code>. So I used <code>cp</code> commands to copy.</li><br>
  
  ``` shell
  
  cp -a liblouis* /home/ubuntu/anaconda3/envs/pytorch_latest_p37/lib/python3.7/site-packages/louis/
  
  ```
  
  <li>Now it should work! :)</li>
</ol>
