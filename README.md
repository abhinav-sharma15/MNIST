# MNIST Stress Test

MNIST image dataset is 'Hello World!' data for image classification. However, we will do MNIST images classfication with a twist - We will train the models on MNIST dataset but will 
try to test these models on some newly introduced 'noisy' images. These images are intentionally semi-processed compared to actual MNIST images. 

MNIST Images

![MNIST Images](https://github.com/abhinav-sharma15/MNIST/blob/ac1891151d8dbec55783ec1e15fb82b05bbb0fd9/MNIST%20images.png)

Noisy Images

![Noisy Images](https://github.com/abhinav-sharma15/MNIST/blob/f3b2915d42e8d3af04d8c91607800d99ba97b9cd/Noisy%20images.png)

The numbers here are not exactly preprocessed like the actual dataset numbers. For example, the background color is not uniform and the digits are not necessarily center of image. This is precisely the reason why these iamges will stress test the models for accuracy.

We will train 3 classification models on MNIST dataset:
- k Nearest Neighbour (kNN)
- Support Vector Machine (SVM)
- Convolutional Neural Network (CNN)

Post training, we will verify following hypothesis about these models:
- The test accuracy should be highest for CNN, folowed by SVM and kNN. This is because CNN uses additional convolutional layer and the spatial awareness through kernals should add further accuracy to the tradional distance based classifcation models like kNN and SVM.
- Accuracy on noisy and outlier images should be highest again for CNN however, SVM should be the worst performer in this category since the inherent nature of SVM to build hyperplanes means that it is bound to misclassify outliers.

We used sklearn for kNN and SVM and tendorflow for CNN. The outcome was preety much as expected - 
- KNN: test classification accuracy: 97.05%, Noisy digits classification accuracy: 77.78%
- SVM: test classification accuracy: 97.74%, Noisy digits classification accuracy: 22.22%
- CNN: test classification accuracy: 99.2%, Noisy digits classification accuracy: 100.0%
