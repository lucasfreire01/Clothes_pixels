# Clothes_pixels
Hello Guys I'm here to show you my new project. The Clothes_pixels project will forecast the cloth based on several pixels provided to the model.
## Pre_Process
Next, the train and test dataset was reshaped in the database to float32, which became the most commonality cheap.<br>

array([[2., 0., 0., ..., 0., 0., 0.],<br>
       [9., 0., 0., ..., 0., 0., 0.],<br>
       [6., 0., 0., ..., 0., 0., 0.],<br>
       ...,<br>
       [8., 0., 0., ..., 0., 0., 0.],<br>
       [8., 0., 0., ..., 0., 0., 0.],<br>
       [7., 0., 0., ..., 0., 0., 0.]], dtype=float32)<br>
this is a representation of the dataset this case a frame of a training dataset, this mind we have a kind of coordinate plane where each place in the image is represented by a number 
next, these images are transformed into gray pictures because the colorful images are 3 buses (R, G, B) for example (187, 222, 87) when we get a gray image in RGB will be for example(187, 187, 187)
we have gray in the RGB base when all values are the same the color is gray this enables us to use 1 buse because the number is the same that is the 3 buses(R G B), bellow is an example in the gray.<br>
![cloth_gray](https://github.com/lucasfreire01/Clothes_pixels/blob/f04a0014fe5c316eceb55e180529ce8a2ecf68f5/download.png)<br>

Bellow we get a range COLORFUL of clothes.<br>

![colorful_range](https://github.com/lucasfreire01/Clothes_pixels/blob/main/download1.png)<br>
after splitting the train and test dataset in x_train, x_test, y_train, y_test. the train database, for example, x_train we take all values of the second pixel ahead and split to 255(value of white in the R G B) and test the database for example x_test takes the first pixel this rule is applied to the split dataset.
## Model
In this model, we use the Keras.Sequential and interlinking the layers is the Conv2d because we don't have depth but the output we use the dense bacause the process of images is done with Conv2d in the images and also use MaxPooling2D to reduce the dimension take a square in pixels and transform into a square lower with the max value in the square behind. This is the summary of the model.<br>
| Layer (type)             | Output Shape       | Param #  |
|--------------------------|--------------------|----------|
| conv2d                   | (None, 26, 26, 32)  | 320      |
| max_pooling2d            | (None, 13, 13, 32)  | 0        |
| conv2d_1                 | (None, 11, 11, 64)  | 18,496   |
| max_pooling2d_1          | (None, 5, 5, 64)    | 0        |
| conv2d_2                 | (None, 3, 3, 64)    | 36,928   |
| flatten                  | (None, 576)        | 0        |
| dense                    | (None, 64)         | 36,928   |
| dense_1                  | (None, 10)         | 650      |

=================================================================<br>
Total params: 93322 (364.54 KB)<br>
Trainable params: 93322 (364.54 KB)<br>
Non-trainable params: 0 (0.00 Byte)<br>
### Result
This is a representation of the result of predicts The image below is a frame with pictures of the final forecast.<br>
![result](https://github.com/lucasfreire01/Clothes_pixels/blob/main/download2.png)<br>
Did a confusion matrix to show us a better vision.<br>
![confusion matrix](https://github.com/lucasfreire01/Clothes_pixels/blob/main/download3.png)<br>
Finally overall with all classes and those accuracies.
|   Class   | Precision | Recall | F1-Score | Support |
|:---------:|:---------:|:------:|:--------:|:-------:|
|  class 0  |   0.85    |  0.87  |   0.86   |  1000   |
|  class 1  |   0.99    |  0.99  |   0.99   |  1000   |
|  class 2  |   0.89    |  0.88  |   0.88   |  1000   |
|  class 3  |   0.92    |  0.93  |   0.92   |  1000   |
|  class 4  |   0.88    |  0.87  |   0.88   |  1000   |
|  class 5  |   0.98    |  0.98  |   0.98   |  1000   |
|  class 6  |   0.78    |  0.76  |   0.77   |  1000   |
|  class 7  |   0.96    |  0.96  |   0.96   |  1000   |
|  class 8  |   0.97    |  0.98  |   0.98   |  1000   |
|  class 9  |   0.96    |  0.97  |   0.96   |  1000   |
| Accuracy  |           |        |   0.92   | 10000   |
| Macro Avg |   0.92    |  0.92  |   0.92   | 10000   |
|Weighted Avg|  0.92    |  0.92  |   0.92   | 10000   |

