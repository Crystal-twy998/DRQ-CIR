# Dual Retrieval Queries Fine-Tuning for Composed Image Retrieval (DRQ-CIR)
Our code and model weights are coming soon 🚀

## Data Preparation
### FashionIQ
Download the FashionIQ dataset following the instructions in the [official repository](https://github.com/XiaoxiaoGuo/fashion-iq). After downloading the dataset, ensure that the folder structure matches the following:
```
├── FASHIONIQ
│   ├── captions
|   |   ├── cap.dress.[train | val | test].json
|   |   ├── cap.toptee.[train | val | test].json
|   |   ├── cap.shirt.[train | val | test].json

│   ├── image_splits
|   |   ├── split.dress.[train | val | test].json
|   |   ├── split.toptee.[train | val | test].json
|   |   ├── split.shirt.[train | val | test].json

│   ├── images
|   |   ├── [B00006M009.jpg | B00006M00B.jpg | B00006M6IH.jpg | ...]
```
### CIRR
Download the CIRR dataset following the instructions in the [official repository](https://github.com/Cuberick-Orion/CIRR). After downloading the dataset, ensure that the folder structure matches the following:
```
├── CIRR
│   ├── cirr
|   |   ├── captions
|   |   |   ├── cap.rc2.[train | val | test1].json
|   |   ├── image_splits
|   |   |   ├── split.rc2.[train | val | test1].json

│   ├── dev
|   |   ├── [dev-0-0-img0.png | dev-0-0-img1.png | ...]

│   ├── train
|   |   ├── [0 | 1 | 2 | ...]
|   |   |   ├── [train-10108-0-img0.png | train-10108-0-img1.png | ...]

│   ├── test1
|   |   ├── [test1-0-0-img0.png | test1-0-0-img1.png | ...]
```
### Fashion200K
Download the Fashion200K dataset following the instructions in the [official repository](https://github.com/xthan/fashion-200k). Download the generated test_queries.txt from [here](https://storage.googleapis.com/image_retrieval_css/test_queries.txt). After downloading the dataset, ensure that the folder struture matches the following:
```
├── Fashion200K
│   ├── labels
|   |   ├── [<catgory>]_<catgory>_detect_all.txt

│   ├── women
|   |   ├── [<category> | <sub_category> | <id>]*.jpeg

│   ├── test_queries.txt
```
and `[<catgory>]` includes `[dress | jacket | pants | skirt | top]`.
### Shoes
We noticed that the images of the Shoes dataset are currently unavailable from the [original source](https://github.com/XiaoxiaoGuo/fashion-retrieval/tree/master/dataset), so we download it from Google Drive and will publish them later.

## Training
```
python src/train.py \
   --dataset {'FashionIQ' or 'CIRR' or 'Shoes' or 'Fashion200K'} \
   --blip-model-name 'blip2_cir_dqu' \
   --num-epochs {'10' for FashionIQ, '15' for other datasets} \
   --num-workers 4 \
   --learning-rate {'1e-5' for CIRR, '2e-5' for FashionIQ and Fashion200K, '3e-5' for Shoes} \
   --batch-size {'128' for FashionIQ, '96' for other datasets} \
   --transform targetpad \
   --target-ratio 1.25  \
   --save-training \
   --save-best \
   --validation-frequency 1 
```

## Evaluation
```
python src/validate.py \
   --dataset {'FashionIQ' or 'CIRR' or 'Shoes' or 'Fashion200K'} \
   --blip-model-name 'blip2_cir_dqu' \
   --model-path {Path to the fine-tuned model} 
```

## Checkpoints
Google Drive: The model weights will be released soon.
