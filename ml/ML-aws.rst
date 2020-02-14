Machine Learning at AWS
=======================

AWS Service Overview
--------------------

General Purpose Machine Learning Services
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  **Amazon Elastic Inference** - attach GPU acceleration to Amazon
   instances: https://aws.amazon.com/machine-learning/elastic-inference/
-  **Amazon SageMaker** - general purpose machine learning:
   https://aws.amazon.com/sagemaker/
-  **AWS Deep Learning AMI (DLAMI)** - Linux with Deep Learning Hardware
   (AMI = Amazon Machine Image)

   -  https://aws.amazon.com/machine-learning/amis/
   -  https://docs.aws.amazon.com/dlami/latest/devguide/what-is-dlami.html

Text and Speech Services
^^^^^^^^^^^^^^^^^^^^^^^^

-  **Amazon Polly** - text to speech service (blackbox):
   https://aws.amazon.com/polly/
-  **Amazon Comprehend** - natural language processing (NLP) service
   (blackbox): https://aws.amazon.com/comprehend/
-  **Amazon Lex** - Chat like Alexa (speech recognition and natural
   language understanding): https://aws.amazon.com/lex/
-  **Amazon Textract** - extract text and data from scanned documents
   (blackbox): https://aws.amazon.com/textract/
-  **Amazon Transcribe** - speech to text (blackbox):
   https://aws.amazon.com/transcribe/
-  **Amazon Translate** - neural machine translation service (blackbox):
   https://aws.amazon.com/translate/

Image and Video Services
^^^^^^^^^^^^^^^^^^^^^^^^

-  **Amazon Rekognition** - image and video analysis (blackbox):
   https://aws.amazon.com/rekognition/

Toy Services
^^^^^^^^^^^^

-  **AWS DeepLens** - deep learning video camera (toy):
   https://aws.amazon.com/deeplens/
-  **AWS DeepRacer** - autonomous deep learning 1/18th scale car (toy):
   https://aws.amazon.com/deepracer/

Other Services
^^^^^^^^^^^^^^

-  **Amazon Forecast** - time-series forecasting service (blackbox):
   https://aws.amazon.com/forecast/
-  **Amazon Personalize** - personalization and recommendation
   (blackbox): https://aws.amazon.com/personalize/
-  **Amazon SageMaker Ground Truth** - manual labeling tools:
   https://aws.amazon.com/sagemaker/groundtruth/
-  **Amazon SageMaker Neo** - compile models for speed and low memory
   footprint: https://aws.amazon.com/sagemaker/neo/

SageMaker Links
---------------

- `Amazon SageMaker 10-Minute Tutorial <https://aws.amazon.com/blogs/machine-learning/category/artificial-intelligence/sagemaker/?sc_icampaign=pac-sagemaker-blogpost&sc_ichannel=ha&sc_icontent=awssm-2276&sc_iplace=console-right&trk=ha_awssm-2276>`_
- `Amazon SageMaker Technical deep-dive <https://aws.amazon.com/getting-started/tutorials/build-train-deploy-machine-learning-model-sagemaker/?sc_icampaign=pac-sagemaker-console-tutorial&sc_ichannel=ha&sc_icontent=awssm-2276&sc_iplace=console-body&trk=ha_awssm-2276>`_
- `Learn fundamentals and deep dive into Amazon SageMaker algorithmsLearn more <https://www.youtube.com/playlist?list=PLhr1KZpdzukcOr_6j_zmSrvYnLUtgqsZz&sc_icampaign=YT_deep-dive&sc_icontent=awssm-2747&sc_iplace=console-sagemaker-learning>`_
- `SageMaker - Developer Guide - Get Started  <https://docs.aws.amazon.com/sagemaker/latest/dg/gs.html>`_

Python API
----------

- `Boto 3 Documentation <https://boto3.readthedocs.io>`_

Services
--------

There are some services but just a couple with GPU support: https://aws.amazon.com/sagemaker/pricing/instance-types

- ml.p3.2xlarge - 1 x V100 GPU
- ml.p3.8xlarge - 4 x V100 GPU
- ml.p3.16xlarge - 8 x V100 GPU
- ml.p2.xlarge - 1 x K80 GPU
- ml.p2.8xlarge - 8 x K80 GPU
- ml.p2.16xlarge - 16 x K80 GPU

Performance Experiment with EC2
-------------------------------

Given:

- LightGBM Classification
- x_train.shape (13788428, 30)
- x_val.shape (2433253, 30)
- y_train.shape (13788428,)
- y_val.shape (2433253,)
- num_classes: 401
- ``num_boost_round = 4``

Results:

- m5.8xlarge, 32 vCPUs, Intel Xeon Platinum 8175, 3.1 GHz Clock Speed, 128 GiB RAM, time: 574s
- r5.4xlarge, 16 vCPUs, Intel Xeon Platinum 8175, 3.1 GHz Clock Speed, 128 GiB RAM, time: 763s
- c5.24xlarge,96 vCPUs, 2nd Gen Intel Xeon Platinum 8275CL, 3.6 GHz Clock Speed, 192 GiB RAM, time: s
