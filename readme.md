## CVPR2022 - Anomaly Detection via Reverse Distillation from One-Class Embedding

1. Environment
	python=3.8 \
    torch1.10.0+cu113 \
    torchvision0.11.0+cu113 \
    scikit-learn \
    opencv-python \
    scikit-image \
    pandas
<br />
2. Dataset
    MVTec_AD \
    DATASET_HUAWEI
<br />
3. Download pretain weights

autodl: https://download.pytorch.org/models/wide_resnet50_2-95faca4d.pth => /root/.cache/torch/hub/checkpoints/
<br />
4. Train and Test the Model    
    > python main.py
<br />
5. results:
    1. make first conv1 (which achieves downsample from 224 to 112) of pretrained wide_Resnet50 (feature extracter) from Conv2d(k7x7,s2,p3) to row_Conv【Conv2d(k1x7,s(1,2),p(0,3))】 & col_Conv【Conv2d(k7x1,s(2,1),p(3,0))】 => fiber auroc:0.67 (epoch=250) => bad
    
