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
next, these images are transformed in gray pictures because the colorful images are 3 buses (R,G,B) for example (187, 222, 87) when we get a gray image in RGB will be for example(187, 187, 187)
we have gray in the RGB base when all values is the same the color is gray this enables us use 1 buse because the number is the same that is the 3 buses(RGB)
