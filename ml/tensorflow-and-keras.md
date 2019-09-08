# Tensorflow and Keras

# Tensorflow:
- [TensorFlow Developers (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/developers)
- [SIG Addons (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/addons)
- [SIG Addons Notes](https://docs.google.com/document/d/1kxg5xIHWLY7EMdOJCdSGgaPu27a9YKpupUz2VTXqTJg/edit#heading=h.7ck4k2782ggg)
- [Tensorflow Addons (GitHub)](https://github.com/tensorflow/addons)
  - [Issue: Testing Jupyter / Colab Notebooks](https://github.com/tensorflow/addons/issues/485)

# Keras:
- [SIG Keras Meetings (Google Groups)](https://groups.google.com/a/tensorflow.org/forum/#!forum/keras-meetings)
- [Keras-users (Google Groups)](https://groups.google.com/forum/#!forum/keras-users)
- [SIG Keras Meeting Agenda and Notes](https://docs.google.com/document/d/1yz2kwWsZ3wx-cObodb84a-LgHuxbTbxo53VI5yFqms8/edit#heading=h.xh0kqonf2i20)
- [Keras API Special Interest Group (SIG)](https://github.com/keras-team/governance)
  - [RFC for Keras Preprocessing redesign](https://github.com/keras-team/governance/pull/6)

## Turn off GPU usage
GPU usage can be turned off this way:

``` python
import os
os.environ["CUDA_VISIBLE_DEVICES"]="-1" 
```
