# Project: Object Detection

## Context

- Task: Object Detection
- Model: SSD
- Dataset: COCO (https://cocodataset.org/)

## Files provided

- model.py, VGG.py and files from model_utils: definition of the model architecture
- coco_loader.py: script to handle the COCO dataset
- transforms.py: the preprocessing operations that were used during training
- classes.json: classes with associated indices
- detection_weights.pth: the weights after training the model on the COCO dataset
  - can be downloaded here: https://people.irisa.fr/Denis.Coquenet/courses/content/M2-DLV/detection_weights.pth


## Additional information

- The dataset is accessible through the ```get_coco``` function of the coco_loader file.
  - The annotations must be downloaded from http://images.cocodataset.org/annotations/annotations_trainval2017.zip
  - The images must be downloaded from http://images.cocodataset.org/zips/val2017.zip
- The coco_eval.py script can be used to compute the metrics more easily

## COCO evaluator usage

### Agregate results through training
```
coco_evaluator.update(...)
```

### After processing all the set
```
coco_evaluator.synchronize_between_processes()
coco_evaluator.accumulate()
coco_evaluator.summarize()
```

## Reference paper
Liu et al., "SSD: Single Shot MultiBox Detector", ECCV 2016.

Paper: https://arxiv.org/abs/1512.02325