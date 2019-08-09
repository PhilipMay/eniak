Besonderheiten bei unausgewogenen Trainingsdaten
================================================

Fragestellungen
---------------

-  Wie sind die Auswirkungen von unsausgewogenen Trainingsdaten und
   Validierungsdaten auf das trainierte Modell bzw. die Metrik?
-  Wie muss man das Lernen gestalten um gute Ergebnisse zu bekommen (bei
   Keras)?
-  Wie messen wir am besten die Güte von Modellen?
-  Wie äußert sich die Anpassung von ``class_weight`` bei Keras auf die
   Lernergebnisse?
-  Sind die Werte von ``class_weight`` egal und es spielt nur das
   Verhältnis eine Rolle?
-  Ist ROC-AUC proportional zu der besten jeweiligen F1 Score?
-  Sind die Validation-Accuracy Werte beim Trainieren proportional zu
   ROC-AUC und F1 Score? Das ist eine relevante Frage für die Frage wann
   man das Trainieren stoppen sollte.
-  Welche Auswirkungen hat es wenn die Validierungsdaten unausgewogen
   bzw. ausgewogen sind?
-  Gibt es unterschiede ob ich nur eine Epoche Trainiere und daran
   vergleiche, mehrere Epochen traniere, so lange trainiere bis ich das
   "beste" modell bekomme oder große und kleinere Netze habe?
-  Gibt es Unterschiede bei plain, CNN oder RNN Netzen?

Was habe ich bisher? - Bestandsaufnahme
---------------------------------------

-  Tool funktionen

   -  An ein Dictionary items hängen.

-  Metrik best_f1_score für beste f1 score mit zugehörigem threshold
-  Keras Callback für Validation und Metriken

Links / Blogs / Literatur
-------------------------

-  `Accuracy paradox <https://en.wikipedia.org/wiki/Accuracy_paradox>`__
-  `Eigene Frage und Antwort zu dem Thema auf
   Stackexchange <https://stats.stackexchange.com/questions/367849/keras-how-do-i-train-a-binary-classification-net-where-one-class-is-much-more-f>`__
-  `python package offering a number of re-sampling
   techniques <https://github.com/scikit-learn-contrib/imbalanced-learn>`__
-  Using SMOTEBoost and RUSBoost to deal with class imbalance:
   https://medium.com/urbint-engineering/using-smoteboost-and-rusboost-to-deal-with-class-imbalance-c18f8bf5b805

Paper
~~~~~

-  `Beyond Accuracy, F-score and
   ROC <https://www.researchgate.net/profile/Stan_Szpakowicz/publication/225215404_Beyond_Accuracy_F-Score_and_ROC_A_Family_of_Discriminant_Measures_for_Performance_Evaluation/links/0a85e53944a8ea9bc5000000/Beyond-Accuracy-F-Score-and-ROC-A-Family-of-Discriminant-Measures-for-Performance-Evaluation.pdf?origin=publication_detail>`__
-  `The Relationship Between Precision-Recall and ROC
   Curves <https://www.biostat.wisc.edu/~page/rocpr.pdf>`__
-  `Classification assessment
   methods <https://ac.els-cdn.com/S2210832718301546/1-s2.0-S2210832718301546-main.pdf?_tid=86f4ca08-a9e9-4108-b02d-a3575d6fe43d&acdnat=1538046410_78163bc936d6f9483366928e101dda81>`__
-  SMOTEBoost: Improving Prediction of the Minority Class in Boosting:
   https://www-users.cs.umn.edu/~lazar027/papers/pkdd03.pdf
-  VOS: a Method for Variational Oversampling of Imbalanced Data:
   https://arxiv.org/pdf/1809.02596.pdf

Keras metrics
~~~~~~~~~~~~~

-  https://github.com/keras-team/keras/commit/a56b1a55182acf061b1eb2e2c86b48193a0e88f7
-  https://www.kaggle.com/teasherm/keras-metric-for-f-score-tf-only
-  https://medium.com/@thongonary/how-to-compute-f1-score-for-each-epoch-in-keras-a1acd17715a2
-  https://github.com/keras-team/keras/issues/5794#issuecomment-303683985

Tools
~~~~~

-  imbalanced-learn: https://imbalanced-learn.readthedocs.io/en/stable/

Bisherige Experimente
~~~~~~~~~~~~~~~~~~~~~

-  Simple-MNIST-1-1.ipynb - Vergleich von Verlauf von Metriken bei einem
   Trainingsdurchgang -
   https://colab.research.google.com/drive/1cHk2CH9xF7sAXN0FJYOWBmKsnVytp2Bn
-  Simple-MNIST-1-9.ipynb - Vergleich von Verlauf von Metriken bei einem
   Trainingsdurchgang -
   https://colab.research.google.com/drive/11abWbOKAyHDKPw4770JFmSdqPDIyaGrp
-  #Bal-01.ipynb - Boxplot Vergleich von F1 bei mehreren Durchgängen
   unbalanced und class_weight Nutzung -
   https://colab.research.google.com/drive/1wmx3W1HtoXZygCm5_L5cv-hAeNm735hZ
-  #Bal-02.ipynb - Boxplot Vergleich von roc_auc bei mehreren
   Durchgängen unbalanced und class_weight Nutzung
   -https://colab.research.google.com/drive/1Dvph5Rq8jdgTXGMJhkph0GbwNN8RaKsV
-  MNIST-ROC-01.ipynb - Roc Curve Plots -
   https://colab.research.google.com/drive/1kk5uX_RoXfhOQma3DuIxhpO8hd6iRZlc
-  MNIST-ROC-03.ipynb - Boxplot Vergleich von mehreren Metriken bei
   mehreren Durchgängen unbalanced und class_weight Nutzung -
   https://colab.research.google.com/drive/1m_dQuDJp1Ra2OiL82wW7kQ_EX0JNnHoT
-  Copy of MNIST-plain-callback-3.ipynb - Performance Callback für
   Training -
   https://colab.research.google.com/drive/1eSDQGmP5yzvPXcc30Qz9-MQQzi_oABHv#scrollTo=t40DET4dSLVj
