# Semantic Segmentation
### Introduction
The goal of this project is to implement a fully connected neural network using a pre-trained VGG-16 classifier to perform semantic segmentation in identifying the drivable portion from images taken from a car's dash cam. 

### Approach
This project employed a pre-trained VGG-16 image classifier and convert it to a fully connected neural network (FCN). The output of the original VGG-16 classifier was converted to a 1x1 convolution with a depth of 2 to signify the number of classes (road or non road). Then the 1x1 convolution is upsampled by multiple transposed convolutions to get the output back to the original image input size. To improved the overall performance, this network utilizes skip connections where output of earlier layers in the encoder portion is added element-wise to layers in the decoder portion. Prior to training, all of the convolution and transposed convolutions are initialized with a random normal initializer. 

### Architecture details
This network utilized cross entropy as the loss function and used an Adam Optimizer. After tuning the hyper parameters, the following values were able to achieve great results.
##### learning rate - 0.001
##### keep_prob - 0.5
##### epochs - 50
##### batch_size - 10

### Results examples
Here included a few pictures that show the performance of the FCN where the drivable area are marked as green.


### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```

### Submission
1. Ensure you've passed all the unit tests.
2. Ensure you pass all points on [the rubric](https://review.udacity.com/#!/rubrics/989/view).
3. Submit the following in a zip file.
 - `helper.py`
 - `main.py`
 - `project_tests.py`
 - Newest inference images from `runs` folder
