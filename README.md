# Dual Retrieval Queries Fine-Tuning for Composed Image Retrieval (DRQ-CIR)
Our code and model weights are coming soon 🚀

## Data Preparation
### FashionIQ
Download the FashionIQ dataset following the instructions in the [official repository](https://github.com/XiaoxiaoGuo/fashion-iq). After downloading the dataset, ensure that the folder structure matches the following:
├── FASHIONIQ
│   ├── captions
│   │   ├── cap.dress.[train | val | test].json
│   │   ├── cap.toptee.[train | val | test].json
│   │   ├── cap.shirt.[train | val | test].json
│
│   ├── image_splits
│   │   ├── split.dress.[train | val | test].json
│   │   ├── split.toptee.[train | val | test].json
│   │   ├── split.shirt.[train | val | test].json
│
│   ├── images
│   │   ├── [B00006M009.jpg | B00006M00B.jpg | B00006M6IH.jpg | ...]
