Tensorflow How-To
=================

Turn off GPU usage
------------------

GPU usage can be turned off this way:

.. code:: python

   import os
   os.environ["CUDA_VISIBLE_DEVICES"]="-1" 

