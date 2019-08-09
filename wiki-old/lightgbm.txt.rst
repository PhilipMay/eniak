LightGBM
========

Advantages
----------

LightGBM loads the best model after early stopping (in contrast to
XGBoost). See here:
https://lightgbm.readthedocs.io/en/latest/Python-Intro.html#early-stopping

Hyperparameter
--------------

Useful hyperopt search space:

.. code:: python

   space = {
       'num_leaves' : hp.quniform('num_leaves', 100, 600, 10),
       'min_data_in_leaf' : hp.quniform('min_data_in_leaf', 10, 30, 1),
       'max_bin' : hp.quniform('max_bin', 200, 2000, 10),
       'bagging_fraction' : hp.uniform('bagging_fraction', 0.01, 1.0),
       'bagging_freq' : hp.quniform('bagging_freq', 0, 10, 1),
       'feature_fraction' :  hp.uniform('feature_fraction', 0.5, 1.0),
       'lambda_l2' : hp.uniform('lambda_l2', 0.0, 70.0),
       'min_gain_to_split' : hp.uniform('min_gain_to_split', 0.0, 2.0),
   }

Links
-----

-  Root Documentation:
   https://lightgbm.readthedocs.io/en/latest/index.html

   -  Python API:
      https://lightgbm.readthedocs.io/en/latest/Python-API.html
   -  Parameters:
      https://lightgbm.readthedocs.io/en/latest/Parameters.html
   -  Parameters Tuning:
      https://lightgbm.readthedocs.io/en/latest/Parameters-Tuning.html
   -  Early Stopping:
      https://lightgbm.readthedocs.io/en/latest/Python-Intro.html#early-stopping
   -  Load and save the booster:
      https://lightgbm.readthedocs.io/en/latest/Python-Intro.html#training
   -  Regression Example:
      https://github.com/Microsoft/LightGBM/tree/master/examples/regression
   -  Binary Classification Example:
      https://github.com/Microsoft/LightGBM/tree/master/examples/binary_classification
   -  Multiclass Classification Example:
      https://github.com/Microsoft/LightGBM/tree/master/examples/multiclass_classification

On GPU
------

-  https://lightgbm.readthedocs.io/en/latest/GPU-Tutorial.html

Error:

.. code:: bash

   $ cmake -DUSE_GPU=1 ..
   -- The C compiler identification is GNU 7.4.0
   -- The CXX compiler identification is GNU 7.4.0
   -- Check for working C compiler: /usr/bin/cc
   -- Check for working C compiler: /usr/bin/cc -- works
   -- Detecting C compiler ABI info
   -- Detecting C compiler ABI info - done
   -- Detecting C compile features
   -- Detecting C compile features - done
   -- Check for working CXX compiler: /usr/bin/c++
   -- Check for working CXX compiler: /usr/bin/c++ -- works
   -- Detecting CXX compiler ABI info
   -- Detecting CXX compiler ABI info - done
   -- Detecting CXX compile features
   -- Detecting CXX compile features - done
   -- Found OpenMP_C: -fopenmp (found version "4.5")
   -- Found OpenMP_CXX: -fopenmp (found version "4.5")
   -- Found OpenMP: TRUE (found version "4.5")
   -- Looking for CL_VERSION_2_2
   -- Looking for CL_VERSION_2_2 - not found
   -- Looking for CL_VERSION_2_1
   -- Looking for CL_VERSION_2_1 - not found
   -- Looking for CL_VERSION_2_0
   -- Looking for CL_VERSION_2_0 - not found
   -- Looking for CL_VERSION_1_2
   -- Looking for CL_VERSION_1_2 - not found
   -- Looking for CL_VERSION_1_1
   -- Looking for CL_VERSION_1_1 - not found
   -- Looking for CL_VERSION_1_0
   -- Looking for CL_VERSION_1_0 - not found
   CMake Error at /usr/share/cmake-3.10/Modules/FindPackageHandleStandardArgs.cmake:137 (message):
     Could NOT find OpenCL (missing: OpenCL_LIBRARY OpenCL_INCLUDE_DIR)
   Call Stack (most recent call first):
     /usr/share/cmake-3.10/Modules/FindPackageHandleStandardArgs.cmake:378 (_FPHSA_FAILURE_MESSAGE)
     /usr/share/cmake-3.10/Modules/FindOpenCL.cmake:132 (find_package_handle_standard_args)
     CMakeLists.txt:94 (find_package)


   -- Configuring incomplete, errors occurred!
   See also "/home/phmay/dev/fork/LightGBM/build/CMakeFiles/CMakeOutput.log".
   See also "/home/phmay/dev/fork/LightGBM/build/CMakeFiles/CMakeError.log".


