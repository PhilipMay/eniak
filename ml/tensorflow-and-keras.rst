Tensorflow and Keras
====================

Links
----------

- Tensorflow:

  - TensorFlow Developers: https://groups.google.com/a/tensorflow.org/forum/#!forum/developers
  - SIG Addons: https://groups.google.com/a/tensorflow.org/forum/#!forum/addons
  - Tensorflow Addons: https://github.com/tensorflow/addons

- Keras:

  - SIG Keras Meetings: https://groups.google.com/a/tensorflow.org/forum/#!forum/keras-meetings
  - Keras-users: https://groups.google.com/forum/#!forum/keras-users
  - Keras API Special Interest Group (SIG):

    - RFC for Keras Preprocessing redesign: https://github.com/keras-team/governance/pull/6

Turn off GPU usage
------------------

GPU usage can be turned off this way:

.. code:: python

   import os
   os.environ["CUDA_VISIBLE_DEVICES"]="-1" 
