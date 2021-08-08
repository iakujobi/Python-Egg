# How to set up a Python Egg File

1. For this example, first create a folder called Python-Egg
2. Inside the Python-Egg folder, create a setup.py file and a folder called mymath
3. Inside the mymath folder, create a file called add.py and add some content to it
4. In the setup.py file, add the following content:

```python
from setuptools import setup, find_packages

setup(
name="mymath",
version="0.1",
packages=find_packages()
)
```

5. Note that instead of using Python’s distutils’ setup function, we’re using setuptools’ setup. We’re also using setuptools’ find_packages function which will automatically look for any packages in the current directory and add them to the egg.
6. To create said egg, you’ll need to do the following from the command line:

```command line
python setup.py bdist_egg
```

7. This will generate a lot of output, but when it’s done you’ll see that you have three new folders: build, dist, and mymath.egg-info.
8. The only one we care about is the dist folder in which you fill find your egg file, mymath-0.1-py2.6.egg.
9. Note that on my machine, it picked up my default Python, which was 3.9 and created the egg against that version of Python. The egg file itself is basically a zip file. If you change the extension to “zip”, you can look inside it and see that it has two folders: mymath and EGG-INFO.
