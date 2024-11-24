# Matrice AI Object Detection

### Data:
For our experiments, we utilized the VinBigData Chest X-ray Abnormalities Detection dataset, which comprises 18,000 high-quality chest radiographs collected from two Vietnamese hospitals: Hospital 108 and Hanoi Medical University Hospital. While the original dataset annotates 14 thoracic abnormalities, we focused on the five most frequent classes: Aortic enlargement, Cardiomegaly, Nodule/Mass, Pleural thickening, and Pulmonary fibrosis. This selection was done as mentioned in the assigment. The dataset was annotated by experienced radiologists through VinBigData's VinLab platform, and model evaluation followed the PASCAL VOC 2010 protocol using mean Average Precision (mAP) at IoU > 0.4

## Repo Structure

- `augmentation-config`: This folder contains the augmentation configuration we defined while training the model.The augmentation techniques have been taken from [here](https://github.com/WongKinYiu/PyTorch_YOLOv4/tree/master)

- `experiment-output`: We conduct two set of experiments, based on the two above configurations, i.e. without and with augmentation.

    - I find that the mean average precision is less for augmentation training, as compared to without augmentation.

    ### Reason for decrease in performance due to augmentation
    I hypothesize that the performance decay with augmentation is due to the introduction of unrealistic anatomical variations through aggressive data augmentation techniques (mosaic, mixup, and geometric transformations), which may disrupt the natural density patterns and anatomical relationships characteristic of X-ray image.

- `src`: This folder contains the actual code that was used for training the model.