# 114-ML-Group37 : Advanced Method & Model: 
This is a **Advanced Method** source code of our ML Final Project - Captcha Recognition by CNN  
Here is the tutorial to use.  

# Dataset:  
## Option 1: Download the dataset   
Kaggle link: https://www.kaggle.com/datasets/hoson09/overlap-dataset  
Here we have 3 folder on this dataset.  
### (1) Test: 5000 images  
### (2) Validate: 5000 images -> Separated to 20000 single character images  
### (3) Train: 25000 images -> Separated to 100000 single character images    
  
## Option 2: Generate the dataset by "data_generate.ipynb"  
You can also generate the dataset by yourself. Here the tutorial  
### (1) Module install  
For module import. You have to ensure you have installed all the module you needed.  
Run "pip install -r requirements.txt" to install all the modules. Also make sure you have download the "DroidSansMono.ttf" and "yolov9_2" to the directory.  

### (2) Module (library) import  
Run the following cell **(0) Library Import** to import the modules  
![image](https://github.com/user-attachments/assets/9f659b4c-40d4-4127-981b-a3d585089590)  

### (3) Self-made ImageCaptcha  
Run the following cell **(1.1) ImageCaptcha Generator** to initialize the "Self-made ImageCaptcha"  
![image](https://github.com/user-attachments/assets/db9d3630-fa59-4ae7-b304-1cbdc5e2b53f)  
Then you can run the following cell **(1.2) ImageCaptcha Testing** to test the function  
![image](https://github.com/user-attachments/assets/57728907-9ba3-47f8-9364-2ab61e12fc43)  
Example generated image:  
![image](https://github.com/user-attachments/assets/87575edb-f895-469f-9791-06b0aeb5edd3)  

### (4) Data Preprocessing  
Run the following cell **(3.1) Data Preprocess Function** to initialize the "Data Preprocessing" functions.  
![image](https://github.com/user-attachments/assets/4edb7dc9-8ff4-459d-b60b-1be86d212c3e)  
Then you can run the following cell **(3.2) Data Preprocess Testing** to test the function  
Note: Remember to change the image's path at <line 11> for testing purpose.  
![image](https://github.com/user-attachments/assets/a485e93a-1f20-4fbe-93d3-dbdd60725273)
Example preprocessed images:  
1. To black/white scale:  
![image](https://github.com/user-attachments/assets/adbe52fe-7d35-49de-8a13-a9bd33b2b4da)  
2. Denoising:  
![image](https://github.com/user-attachments/assets/930e8eb1-84a2-433f-8337-25a63b4fcc6e)  

### (5) Four characters Captcha Images Generate (Together with Preprocessing and Segementation)  
Run the following cells to initialize the "Four characters Captcha Images Generateor".  

#### **1. Yolo Bounding Creator**  
For Segementation Purpose.  
Remember to change the testing images path at <line 64> for testing purpose.
![image](https://github.com/user-attachments/assets/3f9ac955-e0dc-4405-9139-5f5f20e84d9d)  

#### **2. Get Char Region**  
For Segementation Purpose.   
![image](https://github.com/user-attachments/assets/80db5eb5-397a-4e5c-8a9a-9a6fed47d78d)  

#### **3. Four Char Combine**  
Dataset generate.  
Remember to change the path at <line 120> to save your dataset.  
![image](https://github.com/user-attachments/assets/b24c247d-8b89-4dc5-aa87-f3ad5e5d962e)  
  
# Advanced Model Training & Testing (model_v2.ipynb):  
### (1) Module install  
For module import. You have to ensure you have installed all the module you needed.  
Run "pip install -r requirement_model.txt" to install all the modules. Also make sure you have download the "yolov9_2" to the directory.  

### (2) Module (library) import  
Run the following cell **(0) Import Library** to import the modules  
![image](https://github.com/user-attachments/assets/0acadcdb-ae2b-471c-87c7-ae6374477b44)  
  
### (3) Dataset Setup  
Run the following cells to setup the datasets.  
#### **(1.1) Helper Function**  
get_char_index: Convert a letter or digit to its corresponding index.  
![image](https://github.com/user-attachments/assets/ea1fb076-4cd6-48ca-80b8-2e08c9218003)  
#### **(1.2) Load data**   
To load the datasets  
![image](https://github.com/user-attachments/assets/061765e1-cb06-42ef-8f83-7ef9eb776923)  
#### **(1.3) Load Labels csv**   
To load the labels from csv of labels.   
![image](https://github.com/user-attachments/assets/9d25b263-0da3-475e-bbf9-d9741985eaca)   
#### **(1.4) Caller & Separation**   
Load the training datasets as (X_train, y_train), validating datasets as (X_yal, y_val).  
Remember to change the <line 4> ~ <line 7> to the corresponding data path.  
![image](https://github.com/user-attachments/assets/8c50ae3f-d14d-4e4a-a800-6c61985f8b39)  


### (4) Model Training  & Testing
Run the following cells to train & test the model.  
#### **(2.0) Datasets and GPU Checking**  
To check whether your GPU is working, and the shape of datasets is correct.  
![image](https://github.com/user-attachments/assets/0b0b7363-54e5-4909-8285-09b9ccd4b52d)  
#### **(2.1) Training**  
Train the model! Remember to change the save path of model at <line 42>.  
![image](https://github.com/user-attachments/assets/f54002d1-49f5-479a-8f74-3c06bf14a995)  
Example training progress:  
![image](https://github.com/user-attachments/assets/7dfb0d0f-2db0-44a0-82cc-1c13a1b9d9ea)  
#### **(2.2.1) Data Preprocess Function**  
To initialize the data preprocess function. Use these function before testing & predicting.  
![image](https://github.com/user-attachments/assets/f2011003-1130-45b2-8ce5-77c7578363f1)  
#### **(2.2.2) Yolo Bounding Creator**  
To initialize the YOLO model for characters segmentation purpose. Use these function before testing & predicting.  Also, make sure you have download the "yolov9_2" to the working directory, then change the path of testing images at <line 65> for testing purpose before you use this model in prediction progress.    
![image](https://github.com/user-attachments/assets/b2232c4a-72d0-4f26-bf5c-a162e84c0b1e)  
Example result of bounding:  
![image](https://github.com/user-attachments/assets/507ce2f1-d580-41fe-866a-3ff166e38a82)  
#### **(2.2.3) Prediction Function**  
To initialize the prediction function. Use these function for testing & predicting.  
![image](https://github.com/user-attachments/assets/a4e25f33-f847-47aa-8366-2595f56ded5c)  
#### **(2.2.4) Prediction**  
Testing & predicting using the model and function we defined. The result will save to a file named "prediction.txt"  
![image](https://github.com/user-attachments/assets/3fb306dc-0ccb-47cb-97c7-e71af91041d1)  
Remember to use the corresponding path of testing datasets(which should be an original NON-PREPROCESSING dataset, a.k.a original four characters Captcha Images)  
Example of input testing images:  
![image](https://github.com/user-attachments/assets/7514e4de-cc0f-4501-840b-2c97cb6d0d8e)  
Example result of data predicting progress:  
![image](https://github.com/user-attachments/assets/6dc8dcde-7c28-4cf8-81b1-8c6f004e989f)  
![image](https://github.com/user-attachments/assets/bcaf566d-2cff-4749-8523-2007260f0d24)  
#### **(2.2.5) Evaluation**
Evaluate the performance by the following cell.  
![image](https://github.com/user-attachments/assets/f84ef710-0d60-4fea-807c-8b8e1b3ca282)
Example result of evaluation:  
![image](https://github.com/user-attachments/assets/07c406a4-ac29-4b36-b34a-f72eb50aa252)  

# 114-ML-Group37 : Baseline Method & Model: 
This is a **baseline** source code of our ML Final Project - Captcha Recognition by CNN  
Here is the tutorial to use.  
  
# Dataset:  
## Option 1: Download the dataset   
Kaggle link: https://www.kaggle.com/datasets/hoson09/overlap-dataset  
Here we have 3 folder on this dataset.  
### (1) Test: 5000 images  
### (2) Validate: 5000 images -> Separated to 20000 single character images  
### (3) Train: 25000 images -> Separated to 100000 single character images    
  
## Option 2: Generate the dataset by "data_generate.ipynb"  
You can also generate the dataset by yourself. Here the tutorial  
### (1) Module install  
For module import. You have to ensure you have installed all the module you needed.  
Run "pip install -r requirements.txt" to install all the modules. Also make sure you have download the "DroidSansMono.ttf" and "yolov9_2" to the directory.  

### (2) Module (library) import  
Run the following cell **(0) Library Import** to import the modules  
![image](https://github.com/user-attachments/assets/9f659b4c-40d4-4127-981b-a3d585089590)  

### (3) Self-made ImageCaptcha  
Run the following cell **(1.1) ImageCaptcha Generator** to initialize the "Self-made ImageCaptcha"  
![image](https://github.com/user-attachments/assets/db9d3630-fa59-4ae7-b304-1cbdc5e2b53f)  
Then you can run the following cell **(1.2) ImageCaptcha Testing** to test the function  
![image](https://github.com/user-attachments/assets/57728907-9ba3-47f8-9364-2ab61e12fc43)  
Example generated image:  
![image](https://github.com/user-attachments/assets/87575edb-f895-469f-9791-06b0aeb5edd3)  

### (4) Data Preprocessing  
Run the following cell **(3.1) Data Preprocess Function** to initialize the "Data Preprocessing" functions.  
![image](https://github.com/user-attachments/assets/4edb7dc9-8ff4-459d-b60b-1be86d212c3e)  
Then you can run the following cell **(3.2) Data Preprocess Testing** to test the function  
Note: Remember to change the image's path at <line 11> for testing purpose.  
![image](https://github.com/user-attachments/assets/a485e93a-1f20-4fbe-93d3-dbdd60725273)
Example preprocessed images:  
1. To black/white scale:  
![image](https://github.com/user-attachments/assets/adbe52fe-7d35-49de-8a13-a9bd33b2b4da)  
2. Denoising:  
![image](https://github.com/user-attachments/assets/930e8eb1-84a2-433f-8337-25a63b4fcc6e)  

### (5) Four characters Captcha Images Generate (Together with Preprocessing and Segementation)  
Run the following cells to initialize the "Four characters Captcha Images Generateor".  

#### **1. Yolo Bounding Creator**  
For Segementation Purpose.  
Remember to change the testing images path at <line 64> for testing purpose.
![image](https://github.com/user-attachments/assets/3f9ac955-e0dc-4405-9139-5f5f20e84d9d)  

#### **2. Get Char Region**  
For Segementation Purpose.   
![image](https://github.com/user-attachments/assets/80db5eb5-397a-4e5c-8a9a-9a6fed47d78d)  

#### **3. Four Char Combine**  
Dataset generate.  
Remember to change the path at <line 120> to save your dataset.  
![image](https://github.com/user-attachments/assets/b24c247d-8b89-4dc5-aa87-f3ad5e5d962e)  
  
# Baseline Model Training & Testing (baseline.ipynb):  
### (1) Module install  
For module import. You have to ensure you have installed all the module you needed.  
Run "pip install -r requirement_model.txt" to install all the modules. Also make sure you have download the "yolov9_2" to the directory.  

### (2) Module (library) import  
Run the following cell **Import Library** to import the modules  
![image](https://github.com/user-attachments/assets/91b2558b-5c79-49ff-b37f-03e745269ea6)

### (3) Dataset Setup  
Run the following cells to setup the datasets.  
#### **Path of Dataset**  
Set up your own dataset path for both training and testing datasets.
![image](https://github.com/user-attachments/assets/38547cb4-5b4f-456a-8dca-fb7f8616f2ae)
#### **Load Data and Labels**   
Run the 4 cells after "Load Data and Labels". Be sure to change the target_size to your CAPTCHA image size.
Also, change the parameters at the image_list to consistent with your character size.
![image](https://github.com/user-attachments/assets/a0c6f51e-d419-4743-9252-5f9a2fe37660)
![image](https://github.com/user-attachments/assets/7fe52461-6856-4739-859e-554ee75e25bc)
![image](https://github.com/user-attachments/assets/aaa5d75a-53bb-4393-afdb-eebddce9dc1b)
![image](https://github.com/user-attachments/assets/2897145a-1ecc-4607-9347-f9bc211f8941)

### (4) Model Training  & Testing
Run the following cells to train & test the model.  
#### **Model Creation**  
To create the model with certain layers.
![image](https://github.com/user-attachments/assets/7647cce5-ef46-4d32-9b5e-ee8da88324c0)
#### **Model Training**  
Run the model training with the cells after "Model Training".
![image](https://github.com/user-attachments/assets/d334e802-c1b6-4710-9565-e27e03459689)
#### **Prediction**  
Run the cells after "Prediction" and you can get the accuracy of the baseline model.
![image](https://github.com/user-attachments/assets/b8e031b5-810b-4329-9a8a-d9a0eb0264c2)


