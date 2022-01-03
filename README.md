# Mandibular Canal Segmentation
Yolla's Thesis. The python library used in this research are numpy, PIL, opencv, scikit-learn, pydicom, matplotlib, kerasnd, and tensorflow. You can find the paper publication in here : https://inass.org/wp-content/uploads/2021/10/2021123120.pdf

## Method
For this research we used residual fully convolutional network (RFCN) with dual auxiliary loss (DAL) which considered the loss value in the region and boundary of mandibular canal. the RFCN + DAL model's architecture is shown below.

![image](https://user-images.githubusercontent.com/37945491/145174923-d43d59fc-6565-46fa-8cf0-6f43bfd4d088.png)

## Segmentation Process
There are 5 steps for this project :
1. [Slicing CBCT image along the sagittal plane using pydicom](Slicing.ipnyb)
![image](https://user-images.githubusercontent.com/37945491/145208686-84869c8d-d346-4a1e-91c6-245d356e1dd5.png)

2. [Augmented it by horizontally flip the images](Augmentation.ipnyb)
3. [Resize and normalize the images](Preprocess.ipnyb)
4. [Train the images with their region and boundary groundtruth unsing RFCN + DAL and don't forget to change the weight of DAL to find it best weight](Training_RFCN_DAL.ipnyb)
5. [Test the image to get the region and boundary output then combine it to get the result.](Testing_RFCN_DAL.ipynb). The example of the result is shown below 
![image](https://user-images.githubusercontent.com/37945491/145209486-da904c08-0e3c-4555-b068-d21e56ae8660.png)



