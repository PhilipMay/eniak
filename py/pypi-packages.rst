PyPI Packages
=============

Python Pakete erstellen (PyPI)
------------------------------

-  Python Packaging User Guide: https://packaging.python.org/
-  Packaging Python Projects:
   https://packaging.python.org/tutorials/packaging-projects/
-  Writing the Setup Script:
   https://docs.python.org/3.6/distutils/setupscript.html
-  Classifiers: https://pypi.org/classifiers/
-  PEP 440 - Version Identification and Dependency Specification:
   https://www.python.org/dev/peps/pep-0440/
-  twine’s documentation: https://twine.readthedocs.io/en/latest/
-  install_requires:
   https://setuptools.readthedocs.io/en/latest/setuptools.html?highlight=python_requires#declaring-dependencies
-  python_requires:
   https://setuptools.readthedocs.io/en/latest/setuptools.html?highlight=python_requires#new-and-changed-setup-keywords
-  setup.py Beispiele:

   -  Tensorflow:
      https://github.com/tensorflow/tensorflow/blob/6729cd7d1c07e547298fa2a02d1e36390dc62f0a/tensorflow/tools/pip_package/setup.py
   -  NumPy: https://github.com/numpy/numpy/blob/master/setup.py
   -  pandas: https://github.com/pandas-dev/pandas/blob/master/setup.py

##mKurzanleitung pip Paket erstellen und zu PyPI hochladen -
``python3 setup.py sdist bdist_wheel`` - ``twine upload dist/*``
