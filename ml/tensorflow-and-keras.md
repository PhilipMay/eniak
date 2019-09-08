# Tensorflow and Keras

# Tensorflow:
- [TensorFlow Developers (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/developers)
- [SIG Addons (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/addons)
- [Tensorflow Addons (GitHub)](https://github.com/tensorflow/addons)
  - [Issue: Testing Jupyter / Colab Notebooks](https://github.com/tensorflow/addons/issues/485)

# Keras:
- [SIG Keras Meetings (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/keras-meetings)
- [Keras-users (Google Groups)](https://groups.google.com/forum/#!forum/keras-users)
- [Keras API Special Interest Group (SIG)](https://github.com/keras-team/governance)
  - [RFC for Keras Preprocessing redesign](https://github.com/keras-team/governance/pull/6)

## Turn off GPU usage
GPU usage can be turned off this way:

``` python
import os
os.environ["CUDA_VISIBLE_DEVICES"]="-1" 
```
