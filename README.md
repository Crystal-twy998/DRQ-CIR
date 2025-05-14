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
### Shoes
We noticed that the images of the Shoes dataset are currently unavailable from the [original source](https://github.com/XiaoxiaoGuo/fashion-retrieval/tree/master/dataset), so we download it from [Google Drive](https://drive.google.com/file/d/18DEWXvuyp2vXHv4tAw6fcD2ehEtrvyIL/view?usp=sharing). Unzip the file and make the images by their names inside the
```
./data/Shoes/womens_*
```
### Fashion200K
Download the Fashion200K dataset following the instructions in the [official repository](https://github.com/xthan/fashion-200k). Download the generated test_queries.txt from [here](https://storage.googleapis.com/image_retrieval_css/test_queries.txt). After downloading the dataset, ensure that the folder struture matches the following:
```
├── Fashion200K
│   ├── labels
|   |   ├── [dress | jacket | pants | skirt | top]_[train | test]_detect_all.txt

│   ├── women
|   |   ├── [<category> | <caption> | <id>]*.jpeg

│   ├── test_queries.txt
```
