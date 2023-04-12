# cs6910-Assignment2
I have used Resnet50 Model

a. To match the standard ImageNet image size of (224x224), I resized all the images in our dataset. This process can be achieved by utilizing APIs provided by various libraries. These APIs implement different interpolation techniques to perform image resizing.



b.As ImageNet has 1000 classes, every pre-trained model's last layer typically contains 1000 nodes. However, we can train models with any number of classes by removing the last layer of the pre-trained model. Then, we can add a dense layer of any desired size, such as 10, with a softmax activation function.

To obtain the desired output, I plan to retrain specific layers of the model while freezing others. Initially, I will modify the last layer to match the number of classes in our new dataset while freezing all layers except the last one. Afterward, I will begin retraining the fully connected layer.


The optimal approach to address this problem is to freeze certain layers, ideally the initial ones in the CNN, while fine-tuning other layers. This will restrict backpropagation to modify the weights of only the neurons responsible for learning complex features, without altering those that learn fundamental features.

To leverage pre-trained models, we can freeze specific stages during training, such as freezing all layers of the base convolutional layer except the last one. Alternatively, we can freeze the first k layers and train the remaining ones from scratch, or freeze the first k layers and initialize the remaining layers with pre-trained weights.

We can add more layers at the end because since model is trained on a general dataset in the initial layers we can assume that it captures the broad features of the dataset by adding layers at the end we can make it learn more specific features.

I have chosen Resnet50 model.And I modified it in two ways.



Freezing all the layers except the last layers
# 1.Freezing all the layers except the last layers
In the first variation I have freeze all the layers except the last layer. I have removed the last layer and in the place of it i have implanted a fully connected layer of 10 neurons corresponding to 10 neurons each. Even though Resnet50 is a simpler model as compared to other pretrained model but it still performs better than my 5 layer CNNModel even after just 5 epochs where as my CNNModel gave a validation accuracy of 38%. 

## 2.Freezing first 100 layers and fine tuning the other layers


 In the second variant I have freezed the first 100 layers and finetuning the rest of the layers and by running it is observed that it perform much better. In the first epoch itself it is giving validation accuracy 71.28% .It is because my pretrained model captures the broader features on the datset . By fine tuning the last layers i am learning the specific features resulting in a very good accuracy.













