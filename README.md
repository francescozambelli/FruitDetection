# FruitDetection

This repo contains the code related to the article linked:
https://www.academia.edu/97731474/Automated_Fruit_Detection_and_Counting_for_Precision_Agriculture_A_Deep_Learning_Approach_for_2D_High_Resolution_Orchard_Images?source=swp_share


## Authors:
- [Francesco Zambelli](https://github.com/francescozambelli)
- [Gaetano Ricucci](https://github.com/gae-ric)
- [Pietro Miglioranza]()

### Abstract:

The article proposes a pipeline for detecting yield on fruit orchards using 2D images instead of 3D reconstruction tools. The pipeline includes segmentation, depth estimation, and object detection, and aims to address the difficulties of detecting apples on trees, as well as those represented in multiple images. Different methods are applied, including Bayesian optimization and matching keypoints, to optimize the overlap between images and obtain better results. The article also includes experiments on the MinneApple dataset, with comparisons between pre-trained and custom models and different augmentation techniques. Overall, the study highlights the challenges of yield detection in fruit orchards and proposes a potential solution to improve the accuracy of the task.

![processo](https://user-images.githubusercontent.com/92037721/223220855-d1068f06-60ce-4b7c-ae91-3196f42d6610.png)

This workflow outlines the process for counting the number of apples on a tree. To segment the apples from the tree, a U-Net model that was pretrained on a dataset was used. Additionally, the training set was augmented by adjusting the brightness and flipping the images. A depth mask was applied to the images to exclude apples on the ground and on background trees. The resulting mask from the U-Net segmenter was then cropped and patched around the connected areas (i.e., the apples) to count them using a counter based on a Resnet-18 model previously trained on the patch-based dataset of the apples. Finally, the total number of apples on a single tree was obtained by summing the counts of all the apples in a patch.

The dataset used is the Mineapple:
https://github.com/MinneApple
