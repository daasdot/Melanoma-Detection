# Melanoma-Detection
To build a CNN based model which can accurately detect melanoma
# Problem statement: 
> To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts 
  for 75% of skin cancer deaths. A solution that can evaluate images and alert dermatologists about the presence of melanoma has the potential to 
  reduce a lot of manual effort needed in diagnosis.
# Overview
> The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging   
  Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of 
  images, with the exception of melanomas and moles, whose images are slightly dominant.


The data set contains the following diseases:

- Actinic keratosis
- Basal cell carcinoma
- Dermatofibroma
- Melanoma
- Nevus
- Pigmented benign keratosis
- Seborrheic keratosis
- Squamous cell carcinoma
- Vascular lesion

NOTE: You don't have to use any pre-trained model using Transfer learning. All the model building process should be based on a custom model.
The model is trained and tested using Jupyter notebook. Please store the image directory local to the notebook , in order to set the path to run the 
model.

# Tools and Technology
- Python
- tensorflow , keras
- numpy
- pandas
- Jupyter Notebook
  

# Project Pipeline
- Data Reading/Data Understanding - 
  - Data has been stores in the current directory in uncompresse format , so that jupyter notebook can read and processed.
  - This assignment uses a dataset of about 2357 images of skin cancer types. The dataset contains 9 sub-directories in each train and test 
    subdirectories. The 9 sub-directories contains the images of 9 skin cancer types respectively.
- Data Set Creation
  - Batch size , image height and image weidth has been defined
  - Data set has been created with train & validation dataset from the train directory with a batch size of 32. Also, make sure you resize your images     to 180*180.
- Data Visualization
  - Plot has been created with matplotlib library
  - The image_batch is a tensor of the shape (32, 180, 180, 3). This is a batch of 32 images of shape 180x180x3 (the last dimension refers to color   
     channels RGB). The label_batch is a tensor of the shape (32,), these are corresponding labels to the 32 images.
- Model Building & training
  - Created a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel 
     values between (0,1).
  - adam optimiser and cross entrpy loss function for model training has been selected
  - Model has been trained the model with ~20 epochs
  - Post building we could observed the following
    - High Training Accuracy and Low Validation Accuracy
    - This indicates overfitting—the model is memorizing the training data but isn’t generalizing well to unseen data.
    - We can add regularization technique e.g dropout to reduce model complexity
    - Training loss is decreasing with increase in validation loss , whihc signifies overfitt
  - Model has been rebuild using dropout and tained with 30 epoch
    - Overall accuracy got decrease but we can see a balance between training and validation accuracy.There is a decrease in both tarining and 
      validation loss , looks like the model is learning well
- Class distribution
  - 'dermatofibroma' and 'seborrheic keratosis' least number of samples
  - 'pigmented benign keratosis' dominates data in terms proportionate number of samples
- Handling class imbalances - Imbalances has been handled using augmentor library.
- Model Building & training on the rectified class imbalance data
  - CNN model has been created, which can accurately detect 9 classes present in the dataset.Rescale of images has been done to normalize 
    pixel values between (0,1).
  - adam optimiser and cross entrpy loss function for model training has been selected
  - Model has been trained the model with ~20 epochs
