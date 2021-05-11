# Skin-Cancer-CNN-Assignment

# Problem statement: 
To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution which can evaluate images and alert the dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

# Data Understanding:
This assignment uses a dataset of about 2357 images of skin cancer types. The dataset contains 9 sub-directories in each train and test subdirectories. The 9 sub-directories contains the images of 9 skin cancer types respectively.

# Data Pre-Processing:
1. Used 80% of the images for training, and 20% for validation.
2. Used layers.experimental.preprocessing.Rescaling to normalize pixel values between (0,1). As,the RGB channel values are in the [0, 255] range. This is not ideal for a neural network. Here, it is good to standardize values to be in the [0, 1]
3. Data augmentation to fight overfitting in training process. It helps to expose the model to more aspects of the data and generalize better. We used the layers from tf.keras.layers.experimental.preprocessing.
4. Class Imbalance was rectified using python package known as Augmentor (https://augmentor.readthedocs.io/en/master/) to add more samples across all classes so that none of the classes have very few samples.

# Model Building:
Created a 3-layers CNN model, which can accurately detect 9 classes present in the dataset. We have also used Dropout, a form of regularization, to handle overfitting. Adding Dropout to a layer randomly drops out (by setting the activation to zero) a number of output units from the layer during the training process.

# Metrics Chosen:
1. Selected Adam optimizer because it achieves good results fast. This algorithm is an extension to stochastic gradient descent that has recently seen broader adoption for deep learning applications in computer vision. It combines the advantages of two other extensions of stochastic gradient descent : AdaGrad and RMSProp.
2. CrossEntropyLoss is the appropriate loss function for a classification model that outputs raw scores for each class.
3. Accuracy is chosen as the metric to determine the model performance.

# Model Evaluation:
Model evaluated against Test image gave 10.98 prediction score for pigmented benign keratosis
