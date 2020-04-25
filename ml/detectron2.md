# Detectron2

## Train Network on COCO Dataset
- download the data
  - change into `detectron2/datasets`
  - download the dataset from [COCO page](http://cocodataset.org/)
    - 2017 Train images [118K/18GB]
    - 2017 Val images [5K/1GB]
    - 2017 Train/Val annotations [241MB]
    - also see: <https://github.com/facebookresearch/detectron2/tree/master/datasets#expected-dataset-structure-for-coco-instancekeypoint-detection>
    
## C4 Net
```
GeneralizedRCNN(
  (backbone): ResNet(
    (stem): BasicStem(
      (conv1): Conv2d(
        3, 64, kernel_size=(7, 7), stride=(2, 2), padding=(3, 3), bias=False
        (norm): FrozenBatchNorm2d(num_features=64, eps=1e-05)
      )
    )
    (res2): Sequential(
    [...]
    (res3): Sequential(
    [...]
    (res4): Sequential(
    [...]
  )
  (proposal_generator): RPN(
    (anchor_generator): DefaultAnchorGenerator(
      (cell_anchors): BufferList()
    )
    (rpn_head): StandardRPNHead(
      (conv): Conv2d(1024, 1024, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
      (objectness_logits): Conv2d(1024, 15, kernel_size=(1, 1), stride=(1, 1))
      (anchor_deltas): Conv2d(1024, 60, kernel_size=(1, 1), stride=(1, 1))
    )
  )
  (roi_heads): Res5ROIHeads(
    (pooler): ROIPooler(
      (level_poolers): ModuleList(
        (0): ROIAlign(output_size=(14, 14), spatial_scale=0.0625, sampling_ratio=0, aligned=True)
      )
    )
    (res5): Sequential(
    [...]
    (box_predictor): FastRCNNOutputLayers(
      (cls_score): Linear(in_features=2048, out_features=81, bias=True)
      (bbox_pred): Linear(in_features=2048, out_features=320, bias=True)
    )
  )
)
```

## FPN Net
```
GeneralizedRCNN(
  (backbone): FPN(
    (fpn_lateral2): Conv2d(256, 256, kernel_size=(1, 1), stride=(1, 1))
    (fpn_output2): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
    (fpn_lateral3): Conv2d(512, 256, kernel_size=(1, 1), stride=(1, 1))
    (fpn_output3): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
    (fpn_lateral4): Conv2d(1024, 256, kernel_size=(1, 1), stride=(1, 1))
    (fpn_output4): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
    (fpn_lateral5): Conv2d(2048, 256, kernel_size=(1, 1), stride=(1, 1))
    (fpn_output5): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
    (top_block): LastLevelMaxPool()
    (bottom_up): ResNet(
      (stem): BasicStem(
        (conv1): Conv2d(
          3, 64, kernel_size=(7, 7), stride=(2, 2), padding=(3, 3), bias=False
          (norm): FrozenBatchNorm2d(num_features=64, eps=1e-05)
        )
      )
      (res2): Sequential(
      [...]
      (res3): Sequential(
      [...]
      (res4): Sequential(
      [...]
      (res5): Sequential(
      [...]
    )
  )
  (proposal_generator): RPN(
    (anchor_generator): DefaultAnchorGenerator(
      (cell_anchors): BufferList()
    )
    (rpn_head): StandardRPNHead(
      (conv): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
      (objectness_logits): Conv2d(256, 3, kernel_size=(1, 1), stride=(1, 1))
      (anchor_deltas): Conv2d(256, 12, kernel_size=(1, 1), stride=(1, 1))
    )
  )
  (roi_heads): StandardROIHeads(
    (box_pooler): ROIPooler(
      (level_poolers): ModuleList(
        (0): ROIAlign(output_size=(7, 7), spatial_scale=0.25, sampling_ratio=0, aligned=True)
        (1): ROIAlign(output_size=(7, 7), spatial_scale=0.125, sampling_ratio=0, aligned=True)
        (2): ROIAlign(output_size=(7, 7), spatial_scale=0.0625, sampling_ratio=0, aligned=True)
        (3): ROIAlign(output_size=(7, 7), spatial_scale=0.03125, sampling_ratio=0, aligned=True)
      )
    )
    (box_head): FastRCNNConvFCHead(
      (fc1): Linear(in_features=12544, out_features=1024, bias=True)
      (fc2): Linear(in_features=1024, out_features=1024, bias=True)
    )
    (box_predictor): FastRCNNOutputLayers(
      (cls_score): Linear(in_features=1024, out_features=81, bias=True)
      (bbox_pred): Linear(in_features=1024, out_features=320, bias=True)
    )
  )
)
```

## FPN Net with GN
```
GeneralizedRCNN(
  (backbone): FPN(
    (fpn_lateral2): Conv2d(
      256, 256, kernel_size=(1, 1), stride=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_output2): Conv2d(
      256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_lateral3): Conv2d(
      512, 256, kernel_size=(1, 1), stride=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_output3): Conv2d(
      256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_lateral4): Conv2d(
      1024, 256, kernel_size=(1, 1), stride=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_output4): Conv2d(
      256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_lateral5): Conv2d(
      2048, 256, kernel_size=(1, 1), stride=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (fpn_output5): Conv2d(
      256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
      (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
    )
    (top_block): LastLevelMaxPool()
    (bottom_up): ResNet(
      (stem): BasicStem(
        (conv1): Conv2d(
          3, 64, kernel_size=(7, 7), stride=(2, 2), padding=(3, 3), bias=False
          (norm): GroupNorm(32, 64, eps=1e-05, affine=True)
        )
      )
      (res2): Sequential(
      [...]
      (res3): Sequential(
      [...]
      (res4): Sequential(
      [...]
      (res5): Sequential(
      [...]
    )
  )
  (proposal_generator): RPN(
    (anchor_generator): DefaultAnchorGenerator(
      (cell_anchors): BufferList()
    )
    (rpn_head): StandardRPNHead(
      (conv): Conv2d(256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1))
      (objectness_logits): Conv2d(256, 3, kernel_size=(1, 1), stride=(1, 1))
      (anchor_deltas): Conv2d(256, 12, kernel_size=(1, 1), stride=(1, 1))
    )
  )
  (roi_heads): StandardROIHeads(
    (box_pooler): ROIPooler(
      (level_poolers): ModuleList(
        (0): ROIAlign(output_size=(7, 7), spatial_scale=0.25, sampling_ratio=0, aligned=True)
        (1): ROIAlign(output_size=(7, 7), spatial_scale=0.125, sampling_ratio=0, aligned=True)
        (2): ROIAlign(output_size=(7, 7), spatial_scale=0.0625, sampling_ratio=0, aligned=True)
        (3): ROIAlign(output_size=(7, 7), spatial_scale=0.03125, sampling_ratio=0, aligned=True)
      )
    )
    (box_head): FastRCNNConvFCHead(
      (conv1): Conv2d(
        256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
        (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
      )
      (conv2): Conv2d(
        256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
        (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
      )
      (conv3): Conv2d(
        256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
        (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
      )
      (conv4): Conv2d(
        256, 256, kernel_size=(3, 3), stride=(1, 1), padding=(1, 1), bias=False
        (norm): GroupNorm(32, 256, eps=1e-05, affine=True)
      )
      (fc1): Linear(in_features=12544, out_features=1024, bias=True)
    )
    (box_predictor): FastRCNNOutputLayers(
      (cls_score): Linear(in_features=1024, out_features=81, bias=True)
      (bbox_pred): Linear(in_features=1024, out_features=320, bias=True)
    )
  )
)
```
 
## build_resnet_backbone output_shape

`Misc/rcnn_R_50_FPN_3x_gn.yaml`:
```
[04/25 07:10:19 d2.modeling.backbone.resnet]: build_resnet_backbone output_shape: {
'res2': ShapeSpec(channels=256, height=None, width=None, stride=4), 
'res3': ShapeSpec(channels=512, height=None, width=None, stride=8), 
'res4': ShapeSpec(channels=1024, height=None, width=None, stride=16), 
'res5': ShapeSpec(channels=2048, height=None, width=None, stride=32)}
```

`COCO-Detection/faster_rcnn_R_50_C4_3x.yaml`:
```
[04/25 07:12:54 d2.modeling.backbone.resnet]: build_resnet_backbone output_shape: {
'res4': ShapeSpec(channels=1024, height=None, width=None, stride=16)}
```
 
## Example for Validation Result
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
