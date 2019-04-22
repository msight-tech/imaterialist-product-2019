## [iMaterialist Challenge on Product Recognition at FGVC6, CVPR 2019](https://www.kaggle.com/c/imaterialist-product-2019/)


![banner](banner.jpg)


As online shopping and retail AI become ubiquitous in our daily life,  it is imperative for computer vision systems to automatically and accurately recognize products based on images at the stock keeping unit (SKU) level. However, this still remains a challenging problem since there is a large number of SKU-level categories, many of which are fine-grained, with very subtle differences that cannot be easily distinguished. At the same time, images of the same product or SKU can often look different under different conditions (*e.g.*, user generated content v.s. professional generated content).

This competition is part of the fine-grained visual-categorization workshop ([FGVC6 workshop](https://sites.google.com/view/fgvc6/home)) at [CVPR 2019](http://cvpr2019.thecvf.com/). By providing a large scale dataset and hosting a competition, [Malong Technologies](https://www.malong.com/en/home) and FGVC workshop organizers encourage computer vision researchers to develop novel algorithms to tackle this interesting problem. Individuals/teams with top submissions will present their work at the FGVC6 workshop and win cash prizes:

 - 1st place: $ 1,500
 - 2nd place: $ 1,000
 - 3rd place: $ 500

## Kaggle
We use Kaggle to hold our competiton: https://www.kaggle.com/c/imaterialist-product-2019/

## Important Dates

- **April 1, 2019** - Competition starts.

- ~~May 19, 2019~~ **May 26, 2019** - Entry deadline. You must accept the competition rules before this date in order to compete.

- ~~May 19, 2019~~ **May 26, 2019** - Team Merger deadline. This is the last day participants may join or merge teams.

-  ~~May 26, 2019~~ **June 2, 2019** - Final submission deadline.

The original deadline has been extended for one week to be consistent with other FGVC6 challenges. All deadlines are at 11:59 PM UTC on the corresponding day unless otherwise noted. The competition organizers reserve the right to update the contest timeline if they deem it necessary.


## Dataset Format and Download

This dataset has a total number of 2,019 product categories, which are organized into a hierarchical structure with four levels. This category tree can be found in [product_tree.json](product_tree.json) and visualized with [product_tree.pdf](product_tree.pdf). Each leaf node corresponds to a category id and categories share the same ancestor belong to a same hyper-class. The tree structure is not involved in the evaluation but could be potentially used during model training.

### Files

The competition data can be download on [**Google Drive**](https://drive.google.com/open?id=18xGkrb0pzgPw7l931r87029W0ORaVzP_) or [**Baidu Pan**](https://pan.baidu.com/s/1u0XeLu30_5zkMCJ2imnmCw) (password: qecd).

The filename of each image is its ```id```.

- [**train.json**](https://drive.google.com/open?id=1b6RyQTaAlQYKhvc-OfnfZjtVJ_XFV8a7) contains ```id,class,url``` of each training image, where you can use the ```url``` to download the corresponding image with filename ```id``` and class label ```class```. The training data consists of 1,011,532 images from 2,019 categories (range from 158 to 1050 images for each category). The training data is collected from the Internet and contrains some noise. Only image content is allowed for training (e.g., URLs in the provided dataset are not allowed for training).


- [**val.json**](https://drive.google.com/open?id=1o7JlT6E5ffyUUKWsED0XiSXCCfASmlaU) contains ```id,class,url``` of images in the validation set. The validation data has 10,095 images (around 5 for each category). The validation data is collected from the Internet and has been cleaned by human annotators. In this competition, validation data should only be used for validation and is not allowed for training.

- [**test.json**](https://drive.google.com/open?id=1MF50hOqfYVga0f0uXd5w-5cqCqnreLS5) contains ```id,url``` of images in the test set. The test data has 90,834 images (around 45 for each category). The test data is collected from the Internet and has been cleaned by human annotators.



- Train and validation sets have the same format as shown below:

```
{   
    "images": [   
        {   
            "id" : string,   
            "url": string,
            "class": int   
        },
        ...   
    ]
} 
```

Note that for each image, we only provide URL instead of the image content. Users need to download the images by themselves. Note that the image URLs may become unavailable over time. Therefore we suggest that the participants start downloading the images as early as possible. We are considering image hosting service in order to handle unavailable URLs. We'll update here if that could be finalized.

This year, we omit the names of the labels to avoid hand labeling the test images.

- The test data only has image id and url as shown below:

```
{   
    "images": [   
        {   
            "id" : string,   
            "url": string
        },
        ...   
    ]
} 

```




## Evaluation

The challenge is hosted and evaluated on [Kaggle](https://www.kaggle.com/c/imaterialist-product-2019/). Each image has one ground truth label. We use **top-3 classification error** for evaluation: An algorithm to be evaluated will produce top 3 labels per image. If the predicted labels contain the groundtruth label, then the error for that image is 0, otherwise, it is 1. The final score is the top-3 error across all images.

A sample submission file looks like:

```
id,predicted 
20dc3e9e6ca73cfa3ad4d13d1d7526b8.jpg,11 23 58 
c0ff6e315816bb1b27b48687924d41c9.jpg,123 456 789 
221100dc2fd465098a5a7bdd148c7b14.jpg,2 3 5
```

Please include the header as shown above for correct parsing. Each line corresponds to one test image and the predicted class labels. We provide a sample submission file [**sample_submission.csv**](https://drive.google.com/open?id=1v-vF6841uWN5Emn72t0pDSZL3Z4KQRl-) .

## Rules and Terms of Use

Participants should follow the rules and terms of use of this competition as described [here](https://www.kaggle.com/c/imaterialist-product-2019/rules).


- Pre-trained models are allowed in the competition.
- Participants are restricted to train their algorithms on iMaterialist 2019 on Product Recognition training images. Validation data should only be used for validation. Collecting additional data for the target labels is not allowed. Collecting additional unlabeled data for pretraining is ok. Please specify any and all external data used for training when uploading results.
- Only image content is allowed for training (e.g., URLs in the provided dataset are not allowed for training).
Additional annotation on the provided train and validation data is fine (e.g., bounding boxes, keypoints, etc.). Teams should specify that they collected additional annotations when submitting results.
- We ask that you respect the spirit of the competition and do not cheat. Hand-labeling is forbidden.

## Organizers

Xintong Han, Malong Technologies

Sheng Guo, Malong Technologies

Weilin Huang, Malong Technologies

Lingshu Kong, Malong Technologies

Matt Scott, Malong Technologies

For any questions please contact iproduct2019@malong.com
