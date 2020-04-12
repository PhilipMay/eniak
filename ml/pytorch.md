# PyTorch

## Links
- [PyTorch](https://pytorch.org/)
  - Get Started / Installation: <https://pytorch.org/get-started/locally/>
  - Tutorials: <https://pytorch.org/tutorials/>
  - Docs: <https://pytorch.org/docs/stable/index.html>
  - Message Board: <https://discuss.pytorch.org/>
- Ignite - Ignite is a high-level library to help with training neural networks in PyTorch.
  - GitHub: <https://github.com/pytorch/ignite>
  - Doc: <https://pytorch.org/ignite/>
- Detectron2 - Detectron2 is Facebook AI Research's next generation software system that implements state-of-the-art object detection algorithms.
  - GitHub: <https://github.com/facebookresearch/detectron2>
  - Doc: <https://detectron2.readthedocs.io/index.html>

## Learn
- PyTorch Examples: <https://github.com/pytorch/examples>
- Books
  - Deep Learning with PyTorch <https://www.manning.com/books/deep-learning-with-pytorch>
  - Programming PyTorch for Deep Learning: <https://www.oreilly.com/library/view/programming-pytorch-for/9781492045342/>

## Detectron2

### Train Network on COCO Dataset
- download the data
  - change into `detectron2/datasets`
  - download the dataset from [COCO page](http://cocodataset.org/)
    - 2017 Train images [118K/18GB]
    - 2017 Val images [5K/1GB]
    - 2017 Train/Val annotations [241MB]
    - also see: <https://github.com/facebookresearch/detectron2/tree/master/datasets#expected-dataset-structure-for-coco-instancekeypoint-detection>
    
### Example for Validation Result
```
[04/12 17:27:26] d2.evaluation.evaluator INFO: Total inference time: 0:12:10.168191 (0.146180 s / img per device, on 1 devices)
[04/12 17:27:26] d2.evaluation.evaluator INFO: Total inference pure compute time: 0:11:55 (0.143279 s / img per device, on 1 devices)
[04/12 17:27:28] d2.evaluation.coco_evaluation INFO: Preparing results for COCO format ...
[04/12 17:27:28] d2.evaluation.coco_evaluation INFO: Saving results to ./output/inference/coco_instances_results.json
[04/12 17:27:29] d2.evaluation.coco_evaluation INFO: Evaluating predictions ...
[04/12 17:28:10] d2.evaluation.coco_evaluation INFO: Evaluation results for bbox:
|  AP   |  AP50  |  AP75  |  APs  |  APm  |  APl   |
|:-----:|:------:|:------:|:-----:|:-----:|:------:|
| 6.224 | 17.112 | 2.671  | 1.908 | 8.463 | 10.063 |
[04/12 17:28:10] d2.evaluation.coco_evaluation INFO: Per-category bbox AP:
| category      | AP     | category     | AP     | category       | AP     |
|:--------------|:-------|:-------------|:-------|:---------------|:-------|
| person        | 21.752 | bicycle      | 5.029  | car            | 8.336  |
| motorcycle    | 7.553  | airplane     | 7.638  | bus            | 10.205 |
| train         | 8.841  | truck        | 6.183  | boat           | 1.785  |
| traffic light | 1.867  | fire hydrant | 13.825 | stop sign      | 23.748 |
| parking meter | 10.520 | bench        | 2.606  | bird           | 5.844  |
| cat           | 19.445 | dog          | 15.281 | horse          | 12.195 |
| sheep         | 5.204  | cow          | 8.961  | elephant       | 11.703 |
| bear          | 17.412 | zebra        | 16.418 | giraffe        | 15.771 |
| backpack      | 1.553  | umbrella     | 2.970  | handbag        | 1.079  |
| tie           | 1.854  | suitcase     | 2.423  | frisbee        | 5.034  |
| skis          | 0.790  | snowboard    | 1.113  | sports ball    | 6.271  |
| kite          | 3.630  | baseball bat | 0.496  | baseball glove | 1.420  |
| skateboard    | 2.685  | surfboard    | 2.557  | tennis racket  | 6.732  |
| bottle        | 6.475  | wine glass   | 4.497  | cup            | 8.797  |
| fork          | 0.541  | knife        | 0.087  | spoon          | 0.149  |
| bowl          | 8.560  | banana       | 1.346  | apple          | 2.580  |
| sandwich      | 6.983  | orange       | 1.728  | broccoli       | 3.241  |
| carrot        | 0.652  | hot dog      | 1.976  | pizza          | 10.966 |
| donut         | 2.907  | cake         | 5.823  | chair          | 2.700  |
| couch         | 8.387  | potted plant | 3.179  | bed            | 8.761  |
| dining table  | 8.909  | toilet       | 14.390 | tv             | 10.176 |
| laptop        | 8.815  | mouse        | 11.722 | remote         | 1.433  |
| keyboard      | 4.127  | cell phone   | 3.925  | microwave      | 3.987  |
| oven          | 3.029  | toaster      | 0.000  | sink           | 5.725  |
| refrigerator  | 3.449  | book         | 1.505  | clock          | 11.352 |
| vase          | 5.395  | scissors     | 0.297  | teddy bear     | 10.586 |
| hair drier    | 0.000  | toothbrush   | 0.000  |                |        |
[04/12 17:28:11] d2.engine.defaults INFO: Evaluation results for coco_2017_val in csv format:
[04/12 17:28:11] d2.evaluation.testing INFO: copypaste: Task: bbox
[04/12 17:28:11] d2.evaluation.testing INFO: copypaste: AP,AP50,AP75,APs,APm,APl
[04/12 17:28:11] d2.evaluation.testing INFO: copypaste: 6.2236,17.1123,2.6713,1.9080,8.4628,10.0626
```
