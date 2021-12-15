# CSE-518 Artificial Intelligence Project

## Topic-Brain Tumour Segmentation 

## Introduction
Gliomas are the most common primary brain malignancies, with different degrees of aggressiveness, variable prognosis and various heterogeneous histological sub-regions. Ample
multi-institutional routine clinically-acquired multi-parametric MRI (mpMRI) scans of glioma, with pathologically confirmed diagnosis are used as the training, validation, and testing data for BraTS challenge 2021. Ground truth annotations of the tumor sub-regions are created and approved by expert neuroradiologists for every subject included in the training, validation, and testing data sets to quantitatively evaluate the predicted tumor segmentation’s. The dataset of BraTS 2020 contains data of 660 cases that is like 2640 mpMRI images.The present method for diagnosis of tumor is reactive, so once the patients show symptoms they get MRI and CT scans done. The scans are looked into by doctor and the tumor is confirmed but sometimes due to human error or tumor being small in size is not visible by naked eyes[Refer Fig. 1]. Thus in that case the role of Artificial Intelligence comes into picture. By using this approach the accuracy of prediction could be increased. This approach introduced the use of an ensemble classifier composed of different deep convolutional neural networks (CNN) architectures. The paper expects the accuracy to be higher in terms of prediction so as to get better accuracy so the tumor can be predicted in better way that is not even visible to naked eye.

## Approach
The images from the data will be fed as input to the model,
the images has to be prepossessed due to certain abnormalities
like, presence of writing, excess black part or inversion of
image, etc. As per decided the process done on image will
be contouring, cropping, resizing, normalisation and on some
images HoG (Histogram of oriented Gradient).
The image converted to size of 240X240X1 matrix will be
passed through CNN model consisting of 27 convolutional
layers. The first half of the model will be used to narrow
down the image to 15X15X256 and then the image will
again be concatenated in 240X240X1 by using biases from
the narrowing down order and by using total of 2,158,417
parameters to train the model. The MRI image are scanned
that contains 5 types of images so if we take 20 images it
scans a total of 100 images, these images are stored in for
matrix, the image is normalized, the data is then processed,
All the images are then concatenated into a single matrix
and convolution is performed on it. Various other features
like sensitivity, precision, specificity and dice coefficient are
calculated based on the values; this represents the performance
of the model.

![image](https://user-images.githubusercontent.com/76774020/143190858-7903baab-da78-46f1-82d2-7cc20eed0f9b.png)

## Results

Segmented Part of Tumour
<br />
<br />
![image](https://user-images.githubusercontent.com/76774020/143190963-6ce2ba39-2972-424e-acfd-287048b44b58.png)

Loss Vs Epoch Graph
<br />
<br />
![image](https://user-images.githubusercontent.com/76774020/143190992-53873fdb-1f07-4aa9-ae6e-ada2c3e94028.png)

Dice-Coefficient Vs Epoch Graph
<br />
<br />
![image](https://user-images.githubusercontent.com/76774020/143191000-a2e0a422-7347-4a99-bba7-32f8c290f238.png)

Accuracy Vs Epoch Graph
<br />
<br />
![image](https://user-images.githubusercontent.com/76774020/143191006-1add9840-148e-41ce-bfe3-a804faa1b10f.png)


## Platform details 
As the data was available on kaggle we chose to use kaggle notebook as the data file was too large. Kaggle provides CPU and GPU as per requirement to test and train you model. Similar to other online compiler kaggle notebook is efficient and data is saved automatically.

## References with necessary hyperlinks

[1] U.Baid, et al., "The RSNA-ASNR-MICCAI BraTS 2021 Benchmark on Brain Tumor Segmentation and Radiogenomic Classification", arXiv:2107.02314, 2021.

[2] B. H. Menze, A. Jakab, S. Bauer, J. Kalpathy-Cramer, K. Farahani, J. Kirby, et al. "The Multimodal Brain Tumor Image Segmentation Benchmark (BRATS)", IEEE Transactions on Medical Imaging 34(10), 1993-2024 (2015) DOI: 10.1109/TMI.2014.2377694

[3] S. Bakas, H. Akbari, A. Sotiras, M. Bilello, M. Rozycki, J.S. Kirby, et al., "Advancing The Cancer Genome Atlas glioma MRI collections with expert segmentation labels and radiomic features", Nature Scientific Data, 4:170117 (2017) DOI: 10.1038/sdata.2017.117

### 
