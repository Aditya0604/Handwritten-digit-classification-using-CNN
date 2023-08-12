# Handwritten-digit-classification-using-CNN

This was as an exercise for my understandings of CNN and computer vision based on my research in the SOS program.

Initially I Imported Crucial libraries like numpy, matplotlib and tensorflow.
The next step was importing the 60,000 mnist handwritten digits dataset using Keras API from Tensorflow
The mnist is a standard dataset for image recognition for handwritten digits
Then it was time for Splitting it into 60,000 training data and 10,000 test data
The model would be train on 60,000 images and we would then predict its accuracy on the unseen 10,000 images as evaluation part
But before moving onto training, it was important to convert all of the images into the form which could be fed into the model
The steps were normalizing and reshaping
As all of the image pixel values range between 0 to 255, so we normalize all of it to be in range (0 to 1) before passing it into our CNN model
After normalizing , the next resizing step includes adding an extra dimension to the input image for convolution purposes.
Now the preprocessing work is done, we can now succesfully build our CNN model
The model consisted of the following layers:

_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d (Conv2D)             (None, 26, 26, 64)        640       
                                                                 
 activation (Activation)     (None, 26, 26, 64)        0         
                                                                 
 max_pooling2d (MaxPooling2D  (None, 13, 13, 64)       0         
 )                                                               
                                                                 
 conv2d_1 (Conv2D)           (None, 11, 11, 64)        36928     
                                                                 
 activation_1 (Activation)   (None, 11, 11, 64)        0         
                                                                 
 max_pooling2d_1 (MaxPooling  (None, 5, 5, 64)         0         
 2D)                                                             
                                                                 
 conv2d_2 (Conv2D)           (None, 3, 3, 64)          36928     
                                                                 
 activation_2 (Activation)   (None, 3, 3, 64)          0         
                                                                 
 max_pooling2d_2 (MaxPooling  (None, 1, 1, 64)         0         
 2D)                                                             
                                                                 
 flatten (Flatten)           (None, 64)                0         
                                                                 
 dense (Dense)               (None, 64)                4160      
                                                                 
 activation_3 (Activation)   (None, 64)                0         
                                                                 
 dense_1 (Dense)             (None, 32)                2080      
                                                                 
 activation_4 (Activation)   (None, 32)                0         
                                                                 
 dense_2 (Dense)             (None, 10)                330       
                                                                 
 activation_5 (Activation)   (None, 10)                0         
                                                                 
=================================================================
Total params: 81,066
Trainable params: 81,066
Non-trainable params: 0

We decide to train the model on colab GPU for faster training just using 5 epochs.
AFter training the model , the evaluations were as follows:
Test loss on 10,000 test samples 0.0569012314081192
Test accuracy on 10,000 test samples 0.9837999939918518

We can see the model did very very good with around 98.3% accuracy training it with 5 epochs. woohooo!!!
