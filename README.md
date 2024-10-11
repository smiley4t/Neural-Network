# Neural-Network
Use Neural network for classification
This is the project I did for my assignment of the course Deep Learning I took in my Master. I want to summarize basic knowledge of Neural Network for people to understand and show my project step by step so that everybody can understand how to fit a Neural Network to a classification problem.
* Data was taken from (https://zenodo.org/records/7711412). This dataset was acquired in a retrospective study from a cohort of pediatric patients admitted with abdominal pain to Children’s Hospital St. Hedwig in Regensburg, Germany
* The model used is Neural Network with 2 hidden layers with 64 and 32 nodes respectively, and the activation function is reLU activation
Now I will summarize basic knowledge of using Deep Learning (specifically Neural Network) for classfication problems.
## Deep learning layers
Firstly, I want to introduce the overview of the deep learning process. Most deep learning architectures are variations of this simple structure. The difference lies in customisation made for different components. In particular, we will focus on three components: transformation layers, encoding for target , and loss function.
![image](https://github.com/user-attachments/assets/b960abde-2866-4216-a690-75597ed454ef)

![image](https://github.com/user-attachments/assets/75b75b91-9f56-4677-a69c-31833d676ba2)
As you should know, a deep learning model consists of weighted layers.

Although all layers transform the input data into the output, it is helpful to classify commonly used deep learning layers according to their roles in the model.

Preprocessing layers: These are used for input normalisation or data augmentation.
Feature extraction layers: These include convolution layers for image data and recurrent layers for sequential data. They are generally considered where “learning” happens. These will be covered in later weeks as well.
Task layers or decision layers. These are normally densely connected layers. They map features from the feature extraction layers to outputs that are specific to the task.
## Densely connected layers
Task layers are usually realised through densely connected layers (dense layers). Dense layers are the most expressive (in terms of the functions that can be approximated), but they involve more parameters. Therefore they are generally used only in the last couple of layers of a network.
 ## The right activation function
The output of the last task layer should be in the form that fits the task.

For **regression**, the layer outputs should be real numbers representing predicted responses.
For **two-class classification**, the layer output is one number between 0 and 1, representing the probability of the target class.
For **multi-class classification**, the layer outputs should be a vector of positive numbers that add up to 1, representing the probabilities for all classes.
To produce the desired output, we use the right activation function with the suitable value range.

For regression (with unbounded output), we use a dense layer without explicitly using a activation function.
For two-class classification, we usually use a dense layer with a single output followed by the **sigmoid function (aka logistic sigmoid function)**, which squashes the output to a number between 0 and 1.
For multiple-class classification, we usually use a dense layer with outputs followed by the **softmax function**. Both sigmoid and softmax generate numbers between 0 and 1 that can be used to represent probabilities. But the softmax function takes a vector as input and outputs a normalised vector, ensuring that the outputs sum to 1.

Some common activation functions used in deep learning include

- Sigmoid function:
  ![image](https://github.com/user-attachments/assets/f8dc3d19-ed8a-4e74-8cfd-2980c998fbb2)
  This function is commonly used in the output node of a classification model involving two classes. It is also used as the “gate” function in deep learning models to emulate Boolean logic gates.
- Softmax
  ![image](https://github.com/user-attachments/assets/156595b5-0977-4b60-a376-05552e773973)

For multi-class classification, the Softmax function is often used as it ensures that all output values sum to 1.
- ReLU
This is a very popular activation function. It help address the vanishing gradient problem in networks with many layers.
![image](https://github.com/user-attachments/assets/a614a85f-fd91-4902-9fa7-2ecf8ec3302d)

 ## The loss function
 The loss function is a real-valued function that measures the discrepancy between the model output and the target output. The convention is to minimise the discrepancy (as opposed to maximise the similarity); therefore the smaller the loss function the better
There are some default choices of loss function for different task.
For **two-class classification** problem use **binary cross-entropy (negative log-likelihood)**
For **many-class classification problem**, use **categorical cross-entropy problems**
For **regression problems**, use **the mean squared error**





  

